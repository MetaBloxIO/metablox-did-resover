## MetaBlox DID

### Default DID Document （Ethereum Mainnet）

```json
{
  '@context': [
    'https://www.w3.org/ns/did/v1',
    'https://w3id.org/security/suites/secp256k1recovery-2020/v2'
  ],
  id: 'did:metablox:0x1234567890ABCDEFGHIJ1234567890ABCDEFGHIJ',
  verificationMethod: [
    {
      id: 'did:metablox:0x1234567890ABCDEFGHIJ1234567890ABCDEFGHIJ#controller',
      type: 'EcdsaSecp256k1RecoveryMethod2020',
      controller: 'did:metablox:0x1234567890ABCDEFGHIJ1234567890ABCDEFGHIJ',
      blockchainAccountId: 'eip155:1:0x1234567890ABCDEFGHIJ1234567890ABCDEFGHIJ'
    }
  ],
  authentication: [
    'did:metablox:0x1234567890ABCDEFGHIJ1234567890ABCDEFGHIJ#controller'
  ]，
  assertionMethod: [
    "did:metablox:0x1234567890ABCDEFGHIJ1234567890ABCDEFGHIJ#controller"
  ]
}
```

备注： 以太坊主网的did也可以表示为
`did:metablox:mainnet:0x1234567890ABCDEFGHIJ1234567890ABCDEFGHIJ` `did:metablox:0x1:0x1234567890ABCDEFGHIJ1234567890ABCDEFGHIJ`



### Default DID Document （Harmony Mainnet）

```json
{
  '@context': [
    'https://www.w3.org/ns/did/v1',
    'https://w3id.org/security/suites/secp256k1recovery-2020/v2'
  ],
  id: 'did:metablox:harmony:0x1234567890ABCDEFGHIJ1234567890ABCDEFGHIJ',
  verificationMethod: [
    {
      id: 'did:metablox:harmony:0x1234567890ABCDEFGHIJ1234567890ABCDEFGHIJ#controller',
      type: 'EcdsaSecp256k1RecoveryMethod2020',
      controller: 'did:metablox:harmony:0x1234567890ABCDEFGHIJ1234567890ABCDEFGHIJ',
      blockchainAccountId: 'eip155:0x63768244:0x1234567890ABCDEFGHIJ1234567890ABCDEFGHIJ'
    }
  ],
  authentication: [ 'did:metablox:harmony:0x1234567890ABCDEFGHIJ1234567890ABCDEFGHIJ#controller'
  ]，
  assertionMethod: [ "did:metablox:harmony:0x1234567890ABCDEFGHIJ1234567890ABCDEFGHIJ#controller"
  ]
}
```

备注： Harmony主网的did也可以表示为:
`did:metablox:0x63768244:0x1234567890ABCDEFGHIJ1234567890ABCDEFGHIJ`
0x63768244是其chainID 1666600000的十六进制表示方式

### VC Demo (Harmony Mainnet) (如果VC是由第三方权威机构颁发的，通常需要proof字段)

```JSON
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1"
  ],
   "id": "http://metablox.io/credentials/123", //VC唯一标识（可选）
  "type": [
    "VerifiableCredential","WifiAccessCredential"
  ],
  "issuer":"did:metablox:harmony:0xABCDEFGHIJABCDEFGHIJ12345678901234567890", // 权威机构标识，可以是DID，也可以是URI。
  "issuanceDate": "2023-01-01T19:73:24Z",
  "expirationDate": "2025-01-01T19:73:24Z",
  "credentialSubject": {
    "id": "did:metablox:harmony:0x1234567890ABCDEFGHIJ1234567890ABCDEFGHIJ",
    "type": "Validator" // Validator,Miner
  },
    "proof": {
        "type": "EcdsaSecp256k1RecoverySignature2020",
        "created": "2023-10-19T03:29:57Z",
        "proofPurpose": "assertionMethod",
        "verificationMethod": "did:metablox:harmony:0x1234567890ABCDEFGHIJ1234567890ABCDEFGHIJ#controller",
        "jws": "eyJhbGciOiJFUzI1NksiLCJraWQiOiJkaWQ6ZXhhb..."
    },
     "revoked": false
}
```

### VP Demo (Harmony Mainnet)

```json
{
  "@context": [
    "https://identity.foundation/EcdsaSecp256k1RecoverySignature2020#",
    "https://www.w3.org/2018/credentials/v1"
  ],
  "type": ["VerifiablePresentation"],
  "verifiableCredential": [
    {
      "@context": ["https://www.w3.org/2018/credentials/v1"],
      "id": "http://metablox.io/credentials/123", //VC唯一标识（可选）
      "type": ["VerifiableCredential", "WifiAccessCredential"],
      "issuer": "did:metablox:harmony:0xABCDEFGHIJABCDEFGHIJ12345678901234567890", // 权威机构标识，可以是DID，也可以是URI。
      "issuanceDate": "2023-01-01T19:73:24Z",
      "expirationDate": "2025-01-01T19:73:24Z",
      "credentialSubject": {
        "id": "did:metablox:harmony:0x1234567890ABCDEFGHIJ1234567890ABCDEFGHIJ",
        "type": "Validator" // Validator,Miner
      },
      "proof": {
        "type": "EcdsaSecp256k1RecoverySignature2020",
        "created": "2023-10-19T03:29:57Z",
        "proofPurpose": "assertionMethod",
        "verificationMethod": "did:metablox:harmony:0x1234567890ABCDEFGHIJ1234567890ABCDEFGHIJ#controller",
        "jws": "eyJhbGciOiJFUzI1NksiLCJraWQiOiJkaWQ6ZXhhb..."
      },
      "revoked": false
    }
  ],
  "holder": "did:metablox:harmony:0x1234567890ABCDEFGHIJ1234567890ABCDEFGHIJ",
  "proof": {
    "type": "EcdsaSecp256k1RecoverySignature2020",
    "created": "2023-10-19T05:29:57Z",
    "proofPurpose": "assertionMethod",
    "verificationMethod": "did:metablox:harmony:0x1234567890ABCDEFGHIJ1234567890ABCDEFGHIJ#controller",
    "jws": "sssseyJhbGciOiJFUzI1NksiLCJraWQiOiJkaWQ6ZXhhb..."
  }
}
```





