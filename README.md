# Homomorphic-Encryption-During-Facial-Recognition-using-TenSEAL
This project proposes a method for integrating homomorphic encryption into facial recognition systems utilizing the TenSEAL library. Our approach maintains high accuracy and protects the privacy of individuals' facial features by encrypting the data during the recognition process. 

# TenSEAL Library 
TenSEAL is a Python library that facilitates homomorphic encryption operations on data. Homomorphic encryption enables computations to be performed on encrypted data without decrypting it, ensuring sensitive data remains secure.TenSEAL supports high-level homomorphic encryption operations with BFV (Brakerski-Fan-Vercauteren) and CKKS (Cheon, Kim, Kim, and Song) schemes, utilizing Microsoft SEAL, a C++ homomorphic encryption library.

# Architecture of the project
## 1. Import Necessary Libraries:
1. TenSEAL
2. DeepFace
3. base64

## 2. Storing Keys
Context object stores the both private and public key pair. Now, we are going to export it to re-use. We are going to use the following read and write data functions in the following stages. Notice that I prefer to store SEAL objects in base64 encoded instead of bytes.

## 3. Finding facial embeddings
Basically, facial recognition models finds vector representations of facial images. Storing plain vector embeddings in the cloud systems causes privacy problems. Because if an attacker has the facial embedding of an identity, it can apply some adversarial attacks. We have to store facial embeddings in the cloud systems as encrypted.

## 4. Encryption
We are going to encrypt facial embeddings with homomorphic encryption and store homomorphic encrypted tensors in the cloud system. This operation will be done in the client side.

## 5. Calculations
This operation will be done in the server side. Once we have the homomorphic encrypted tensors, we are able to make calculations on the encrypted data. We basically need to find the euclidean distance between two vectors to determine an identity.

## 6. Decryption
We will transfer the homomorphic encrypted euclidean squared value from cloud to client.

## 7. Validation
We handled euclidean distance formula on encrypted data.

# Conclusion
Homomorphic encryption refers to an encryption technique that permits computations to be conducted on encrypted data without requiring decryption. Essentially, homomorphic encryption enables computations to be performed on data in an encrypted format, resulting in encrypted results that can only be decrypted by authorized parties. This encryption technique presents a viable solution to the privacy problem in scenarios where data necessitates processing while maintaining confidentiality. It allows secure computation of data in the cloud without disclosing it to unauthorized entities or the cloud provider. Homomorphic encryption has diverse applications in fields such as finance, healthcare, and data processing where data confidentiality and privacy are crucial.
