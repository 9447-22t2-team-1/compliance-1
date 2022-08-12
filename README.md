S3 ISM Controls

Controls

Control: ISM-1781;
All data communicated over network infrastructure is encrypted.

Control: ISM-0476; Revision: 7; Updated: Mar-22; Applicability: O, P; Essential Eight: N/A When using RSA for digital signatures, and passing encryption session keys or similar keys, a modulus of at least 2048 bits is used, preferably 3072 bits.


IAM ISM Controls

Control: ISM-1505; Revision: 1; Updated: Sep-21; Applicability: All; Essential Eight: ML3
Multi-factor authentication is used to authenticate users accessing important data repositories.

Control: ISM-1683; Revision: 0; Updated: Sep-21; Applicability: All; Essential Eight: ML2, ML3
Successful and unsuccessful multi-factor authentications are logged.

Control: ISM-1684; Revision: 0; Updated: Sep-21; Applicability: All; Essential Eight: ML3
Multi-factor authentication event logs are centrally stored and protected from unauthorised modification and deletion,
monitored for signs of compromise, and actioned when cyber security events are detected.

Setup
1. Install CLI:  pip3 install cloudformation-cli cloudformation-cli-python-plugin
2. Configure AWS CLI with your credentials:
$ aws configure

3. Permissions needed:
      -register-type
      -list-types
      -deregister-type
      -set-type-configuration

4. Generate the hook. The cloudformation-cli will create empty handler functions. Each handler created corresponds to a hook invocation point. :  $cfn generate

5. Copy the code from repo in handler.py which is located in the src/ directory.

6. Register the hook: $ cfn submit –set-default

7. Check if you can see your hook in the list after you run the command below:
$ aws cloudformation list-types

8.  Copy the hook arn from the response.

9.  Activate hooks from the public registry:
aws cloudformation --region ap-southeast-2 set-type-configuration \
  --configuration "{\"CloudFormationConfiguration\":{\"HookConfiguration\":{\"TargetStacks\":\"ALL\",\"FailureMode\":\"FAIL\",\"Properties\":{}}}}" \
  --type-arn $Hook_ARN


Future Automation 
- Requires user to configure AWS 
      i.e. AWS Secret Key,  
- User ARN

Extra: https://github.com/aws-cloudformation/aws-cloudformation-samples

