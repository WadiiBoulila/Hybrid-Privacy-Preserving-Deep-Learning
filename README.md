# A Hybrid Privacy-Preserving Deep Learning Approach for Object Classification in Very High-Resolution Satellite Images
This repository contains the code for the following publication "A Hybrid Privacy-Preserving Deep Learning Approach for Object Classification in Very High-Resolution Satellite Images". Link: https://www.mdpi.com/2072-4292/14/18/4631

### Description
This repository is the approach designed to encrypt high resolution remote sensing imagery.
<br />
Hybrid Privacy-Preserving Deep Learning is an encryption method that secures the information in the image. This method is based on Homomorphic Encryption(HE), specifically Partially Homomorphic Encryption(PHE) and Somewhat Homomorphic Encryption(SHE). It does not rely on all the functions and properties of these two approaches but the construction of this technique depends on the extraction of certain properties of each according to its needs.

As the encryption approach is a trade-off between data privacy and model accuracy, DLaaS can run on encrypted images without knowing the context of the images and due to Hybrid_PPDL's ability to preserve the feature of images, DL Models can train on this type of images and show an accuracy result(good).

The main advantage of the Hybrid approach is to resolve the limitation of PHE and preserves the feature of images which is the role of the Homomorphic Encryption technique.

### Principal Functions Explanation 
| Function | Input | Output | Explanation |
| -------- | ----- | ------ | ----------- |
| public_key | |  | public_key is an object of class PublicKey |
| public_keyS | _lambda(security parameter of SHE that is modified by the user) and secret key | Public key list | Function can generate the public key list that is dependent on _lambda and secret key. it is included in SHE scheme. |
| Hybrid_encryption | _lambda(security parameter of SHE that is modified by the user),public_keyS(function call to generate the public key list. It includes in SHE approach) , plaintext( the pixel value is to encrypt) , public_key(the object include in PHE scheme).  |Encrypted pixel value | Function uses four different inputs to generate the new pixel value which is encrypted.
| ImgEncrypt | Same input of Hybrid_encryption but it differs on plaintext. In this function the plaintext is an images. | Encrypted image | Function calls the function Hybrid_encryption function to encrypt each image pixel and generate a new image that is encrypted and has the same size as the plain image.

Hybrid_PPDL has two steps: 
<br />
The first steps is to generate the public keys based on two different algorithms each one belongs to an approach (PHE and SHE): the first key (PHE: k1) is gererated using two large prime(p and q) and the second key(SHE: k2) is generated using _lambda. 
<br />
The second steps is to generate an encrypted value.

![tree](Steps.jpg)

The purpose of this method is to encrypt an image so that it is incomprehensible to the user and when used in the DL process, the untrusted environment cannot know its context. Then, the user can upload their dataset to a remote computer/environment without fear of knowing the context of the image by the enemy user or hacker. 
<br />
The output of this approach is a new image generated as follows: 

![tree](ImgEcrypt.jpg)

# Demo
You can test the whole process of image encryption, and training on plain and encrypted images, on a sample dataset, using this [Colab notebook](https://colab.research.google.com/drive/14iYEfy6Tj27n7_QHy-rSakY2ANYmNRrv?usp=sharing) (save a copy of the notebook if you want to modify it).
