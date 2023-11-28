rsa using html and js 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RSA Encryption and Decryption</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/cryptico/1.0.0/cryptico.min.js"></script>
</head>
<body>
    <script>
        // Function to generate RSA key pair
        function generateRSAKeyPair() {
            var keySize = 2048;
            var key = cryptico.generateRSAKey("randomKey", keySize);
            return key;
        }

        // Function to encrypt using RSA
        function encryptRSA(message, publicKey) {
            var encryptionResult = cryptico.encrypt(message, publicKey);
            return encryptionResult.cipher;
        }

        // Function to decrypt using RSA
        function decryptRSA(ciphertext, privateKey) {
            var decryptionResult = cryptico.decrypt(ciphertext, privateKey);
            return decryptionResult.plaintext;
        }

        // Example usage
        var message = "Hello, RSA Encryption!";
        var keyPair = generateRSAKeyPair();
        var encryptedMessage = encryptRSA(message, keyPair.publicKeyString());
        var decryptedMessage = decryptRSA(encryptedMessage, keyPair);

        console.log("Original Message:", message);
        console.log("Encrypted Message:", encryptedMessage);
        console.log("Decrypted Message:", decryptedMessage);
    </script>
</body>
</html>
