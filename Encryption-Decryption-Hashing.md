Tools for all things encryption, decryption and hashing

### Quipqiup
- [Cryptogram solver](quipqiup.com)

### SHA 512 Hash Script
```
hashed_password = hashlib.sha512(password.encode('password') + salt.encode('salt')).hexdigest()
print(hashed_password)
```

### Python AES Decode Script
```
# For this to work, you need to have pycrypto installed via pip, if it doesn't work uninstall 
# crypto/pycrypto or both and then only install pycrypto 

from Crypto.Cipher import AES
from base64 import b64decode

# if both the key and the cipher are base64 encoded, you need to decode them with b64decode 
key = b64decode("key")
ciphertext = b64decode("ciphertext")

# you need to make a new AES object, where you can set the key and the mode(= ECB (electronic Codebook)) 
# as parameters
obj = AES.new(key, AES.MODE_ECB)

# now you can use the decrypt function to get the cleartext message
cleartext = obj.decrypt(ciphertext)

# the output 
print("%s" % cleartext)
```
