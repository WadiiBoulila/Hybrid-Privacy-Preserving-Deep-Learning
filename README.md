# Hybrid-Privacy-Preserving-Deep-Learning
Hybrid Privacy-Preserving Deep Learning is an encryption method that secures the information in the image.

Hybrid Privacy-Preserving Deep Learning is based on Homomorphic Encryption(HE), specifically Partially Homomorphic Encryption(PHE) and Somewhat Homomorphic Encryption(SHE). 

As the encryption approach is a trade-off between data privacy and model accuracy, DLaaS can run on encrypted images without knowing the context of the images and due to Hybrid_PPDL's ability to preserve the feature of images, DL Models can train on this type of images and show an accuracy result(good).

The main advantage of the Hybrid approach is to resolve the limitation of PHE and preserves the feature of images which is the role of the Homomorphic Encryption technique.

### Functions Explanation 
| Function | Input | Output | Explanation |
| -------- | ----- | ------ | ----------- |
| Hybrid_encryption | _lambda(security parameter of SHE that is updated by the user),public_keyS(function call to generate the public key list. it includes in SHE approach) , plaintext( the pixel value is to encrypt) , public_key(the object include in PHE scheme).  |Encrypted pixel value | Function uses four different inputs to generate the new pixel value which is encrypted.
