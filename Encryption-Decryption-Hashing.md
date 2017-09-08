Tools for all things encryption, decryption and hashing

### [Quipqiup](https://quipqiup.com/)
- Cryptogram solver

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

### Salt Script 
```
<?php
echo crypt('passwd', '$6$rounds=10000$salt$') . "\n";
?>
```
the output the above gives is: 
```
$6$rounds=10000$salt$r/Y9cjdRUn3s.CGSlVx6lTFkS/5VZKXWUWtRdrfxU6T4ldafc0L9B9IfTKo8GNXqlHX5Rd7b8V2Q93wYAFjIq/
```
**'$6$rounds=10000$salt$'** means:
- '$6$' = the SHA 512 algorithm, rounds = 10000 is how many rounds the password should get salted 
- minimum rounds = 1,000
- maximum rounds = 999,999,999

you could replace **'$6$rounds=10000$salt$'** with the following: 
- **'$1$randomstr$'** where the '1' is for the MD5 algorithm and 'randomstr' should be replaced with whatever you want
- **'$2a$07$usesomesillystringforsalt$'** where '$2a$'is for the Blowfish algorithm. You can use any letter out of the alphabet, upper or lower case, as long as it is with 2 cost parameters '$' and the number 2. This one is usually the best, as it is the slowest algorithm. 
> always keep your salt as unique as possible, never use your standard salts. Use some long not so easy to guess string
