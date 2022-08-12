S3 ISM Controls

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

Future Automation 
- Requires user to configure AWS 
      i.e. AWS Secret Key,  
- User ARN

Extra: https://github.com/aws-cloudformation/aws-cloudformation-samples
