
#Examples
 
## Sign a Public Key
```
var keyPair = Virgil.Crypto.generateKeyPair();
var signature = Virgil.Crypto.sign(keyPair.publicKey, keyPair.privateKey);
```
