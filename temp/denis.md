
#Examples

## Initialization

```javascript
var keysClient = new Virgil.SDK.KeysClient("{ACCESS_TOKEN}");

var keyPair = Virgil.Crypto.generateKeyPair();
var publicKey = keyPair.publicKey();
var privateKey = keyPair.privateKey();
```

## Sign a Public Key
```javascript
var signature = Virgil.Crypto.sign(publicKey, privateKey);
```

## Verify Public key
```javascript
var isValid = Virgil.Crypto.verify(signature, publicKey);
```

## Public Key revocation 
```javascript
keysClient.PublicKeys.revoke(publicKeyId, privateKey)
    .then(function(publicKeyResult){
      // public key has been revoked successfully 
    });
```

## Public Key revocation check 
```javascript
keysClient.PublicKeys.get(publicKeyId)
    .then(function(publicKeyResult){
      // occurs when public key is found.
    }),
    .catch(Virgil.Error.PublicKeys.Revoked, function() {
      // occurs when requested public key has been revoked.
    });
```


