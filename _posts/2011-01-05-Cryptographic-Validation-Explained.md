---
layout: post
title: Cryptographic Validation Explained
tags: 
category: General
---
We have been using LogicNP’s CryptoLicensing for some of our software and I was battling to understand how exactly the whole process worked. I was sent the following document which really helped explain it – so if you ever use the same tool it is well worth a read.

Licensing Basics

LogicNP CryptoLicensing For .Net is the most advanced and state-of-the art licensing and copy protection system you can use for your software. LogicNP CryptoLicensing System uses the latest cryptographic technology to generate and validate licenses. The cryptographic algorithm used is the RSA algorithm which consists of a pair of keys called as the generation key and the validation key. Data encrypted using the generation key can only be decrypted using the corresponding validation key.

How does cryptographic validation work?
When a new license project is created, a unique validation-generation key pair is created for the project. When LogicNP CryptoLicensing For .Net generates licenses, it encrypts the license settings using the generation key. The validation key can be safely distributed with your software and is used during validation. During license validation, LogicNP CryptoLicensing For .Net attempts to decrypt the encrypted license code using the validation key. If the decryption is successful, this means that the data was encrypted using the generation key, since only the corresponding validation key can decrypt data encrypted with the generation key. This further means that not only is the license valid but that it was generated by you and only you since nobody else has access to the generation key.

Generation Key 
This key is used by CryptoLicensing Generator to generate encrypted license codes. This key is stored in the license project file, so the license project file must be kept secure and confidential and must be accorded the same care as any other critical asset such as source code.

Validation Key 
This key is used for validating generated license codes. It is the same key displayed in the 'Get Validation Key And Code' dialog (Ctrl+K) and is used by your software when validating license codes (using LogicNP.CryptoLicensing.dll). Unlike the generation key, it is not necessary to keep this key secure and confidential.

Note that the generation key pair is stored in the project file created by LogicNP CryptoLicensing For .Net, so it is very important to backup this file and to keep it secure. Once the file is lost, it is not possible to retrieve the key pair.

FAQ

Do I use the same validation key to validate all license codes? 
Yes, the validation key (and generation key) for the project remains the same; you use the same key to validate all license codes generated using the project. 
You can retrieve the validation key using the "Project" menu --> "Get Validation Key & Code" menu item.
Can license codes generated using generation key from one project be validated using validation key of another project? 
No!
Q. Is every generated license code unique?

A. Yes, every license code generated by CryptoLicensing is guaranteed to be unique, even if you generate thousands of codes at a time.

Q. What makes CryptoLicensing so secure?

A. CryptoLicensing uses the latest cryptographic technology to generate and validate licenses. The cryptographic algorithm used is the RSA asymmetric key algorithm which can use upto 3072-bit keys. Given current computing power, it takes years to break a 3072-bit key.

Q. Is is possible for a hacker to develop a keygen for my software?

A. Impossible. The cryptographic algorithm used by CryptoLicensing consists of a pair of keys called as the generation key and the validation key. Data encrypted with one key can only be decrypted by the other key and vice versa. Licenses are generated using the generation key and validated using the validation key. Without the generation key, it is impossible to generate valid licenses.

Q. What is the difference between validation key and generation key?

Generation Key 
This key is used by CryptoLicensing Generator to generate encrypted license codes. This key is stored in the license project file, so the license project file must be kept secure and confidential and must be accorded the same care as any other critical asset such as source code.

Validation Key 
This key is used for validating generated license codes. It is the same key displayed in the 'Get Validation Key And Code' dialog (Ctrl+K) and is used by your software when validating license codes (using LogicNP.CryptoLicensing.dll). Unlike the generation key, it is not necessary to keep this key secure and confidential.

Q. Do I have to include the license project file (.licproj) with my software?

A. No!!! This goes against the very essence of the security of the asymmetric cryptographic scheme because the project file contains both the validation and generation key. With your software, you only need to include the validation key which will be used to validate licenses generated by CryptoLicensing using the generation key. The license project file should be treated as any other valuable and confidential asset such as your source code.

Q. Does the license service need the license project file?

A. Yes. The license project file is needed whenever new licenses are generated (via the UI, via the API or via the license service). As just one example, the license service generates new machine-locked licenses when activated licenses are presented to it for activation, therefore the license service needs the license project file.

Q. Is it possible to embed my own data in the generated licenses?

A. Yes. You can embed any amount of additional data in the licenses. This data will have the same amount of security as the license code itself and will be tamper-proof. The embedded user data can be retrieved from your software.

Q. What additional steps can I take to ensure that my software does not get cracked?

A. There are many methods and techniques which can make it extremely difficult for a hacker to crack your software. See Writing Effective License Checking Code And Designing Effective Licenses for more information.

Q. Why is the license service not working?

A. The most common cause is not setting the CryptoLicense.LicenseServiceURL property before trying to validate a license. Make sure that this property is set to the correct URL where your license service is hosted.

The most common cause after this is that the license project file on the web server where your license service is hosted is not the latest. This happens if you make changes to the license project (for example, set the 'Enable With Serials' setting for a profile), but don't upload the updated project file to your web server.

Q. Why are my serials not working?

Serial codes require the user of a license service. See Using Serial Codes for more details. Also see the earlier question 'Why is the license service not working?'

Q. Is the same validation key used to validate license codes generated from different profiles.

A. Yes. Profiles are just pre specified license settings for quickly generating licenses having those settings. The actual license code is still generated using the license project's cryptographic generation key and thus, can be validated using the project's validation key.

Q. Why are changes made to a profile not getting saved?

A. Simply changing license settings via UI and saving the license project does not save those license settings to the active profile. You must first save the license settings to a profile using the Save/Save As command from the Profiles menu (see above).

Q. Why is validation of activated licenses failing from CryptoLicensing Generator, but works from my software?

A. Make sure that you have specified the URL of the license service using the Project Properties Dialog. Also see the earlier question 'Why is the license service not working?'

Q. How can I extend the trial period of my customer?

A. To extend the evaluation period of the customer, simply send him a new license code specifying the desired evaluation limits. Evaluation information such as the current used days, executions, etc are stored in garbled form in a registry location which is derived from the license code. Therefore, when a new license code is used, the old evaluation information will not be used and a new evaluation period will be started.