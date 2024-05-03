# Unity Crypto Library
<img src="https://github.com/DevsDaddy/UnityCrypto/blob/main/DevsDaddy/Shared/CryptoLibrary/Preview.png?raw=true" alt="Unity Crypto Library" style="width: 100%" /><br/>
**Unity Crypto Library** is a set of free and open source **cross-platform tools** for using **cryptographic and hash functions** in your games. 
It also contains helper classes for handling files and web requests for your convenience.

I periodically update possible algorithms based on the latest research in crypto-graphy.

> **Note!** This library supports only Unity 2021+ versions

## Get Started
**Unity Crypto Library** is designed for your application and games security and using only default API's like **System** and **UnityEngine**.

**Installation process:**
- Download and import <a href="https://github.com/DevsDaddy/UnityCrypto/releases">latest release from this page</a>;
- See <a href="#usage">usage examples below</a>;

## Usage
**You can use a simple controller for fast encryption/decryption:**
```csharp
// Setup Default Crypto-Provider
CryptoController.SetDefaultProvider(new AESProvider(new AESEncryptionOptions {
    cryptoKey = "myCryptoKey"
}));

// Simple Plain-Text Encryption-Decryption 
string encryptedText = CryptoController.Encrypt("MyTextToEncrypt");
string decryptedText = CryptoController.Decrypt(encryptedText);

// Or with in-line crypto-provider
string encryptedText2 = CryptoController.Encrypt("TextToEncrypt", new AESProvider(new AESEncryptionOptions {
    cryptoKey = "myCryptoKey"
}));
```

**Or initial crypto providers manually:***
```csharp
// Create your provider
AESProvider provider = new AESProvider(new AESEncryptionOptions {
    cryptoKey = "myCryptoKey"
});

// Work with provider
string encryptedText = provider.EncryptString("MyTextToEncrypt");
string decryptedText = provider.DecryptString(encryptedText);
```

**Also you can read/write files using util class (similar like CryptoController just for files):***
```csharp
// Setup Default Crypto-provider for Files
CryptoFile.SetDefaultProvider(new AESProvider(new AESEncryptionOptions {
    cryptoKey = "key"
}));

// Read and Decrypt File
string decryptedText = CryptoFile.ReadText("path_to_encrypted_file");

// Encrypt plain-text and save to file
bool writtenFile = CryptoFile.WriteText("path_to_encrypted_file", decryptedText);
```

## Crypto-Algorithms
**Library contains popular crypto modules:**
- **AES** (Recommended);
- **Triple DES** (Recommended);
- **BlowFish** (Recommended);
- **Twofish** (Recommended);
- **RSA** (Recommended for Web);
- **DES**;
- **Base64**;
- **XOR** (Only strings support, no byte array);

**Code Sample:**
```csharp
string encrypted = CryptoController.Encrypt("TextToEncrypt", new AESProvider(new AESEncryptionOptions {
    cryptoKey = "myCryptoKey"
}));

// Return Encrypted
Debug.Log(encrypted);
```

## Hashing
**Library contains popular hashing functions:**
- **SHA1** / **SHA256** / **SHA512** (Recommended);
- **PBKDF2** (Recommended);
- **MD5**;
- **xxHash**;
- **RIPEMD-160**;
- **CRC32**;

**Code Sample:**
```csharp
string hashed = CryptoController.Encrypt("TextToEncrypt", new MD5Provider(new MD5EncryptionOptions { }));

// Return Hashed
Debug.Log(hashed);
```

## Examples
See framework usage examples in other projects:
* <a href="https://github.com/DevsDaddy/GameShield">Game Shield - Unity Game Security and Anti-Cheat Toolkit</a>;

## Coming Soon (TO-DO)
**I plan to add the following functionality in the near future:**
- Sending and accepting encrypted HTTP requests and working with encrypted data on sockets with server examples on NodeJS / CSharp;
- Read / Write files using chunks for large amounts of data;
- New Hashing Modules: Argon2, BCrypt, SCrypt, Whirlpool;
- New Encryption Modules like SPHINCS+;

## Join Community
- <a href="https://discord.gg/xuNTKRDebx">Discord Community</a>
- <a href="https://boosty.to/devsdaddy">Buy me a Beer (Boosty)</a>
