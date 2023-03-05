# Soulbound-NFTs
See BSC testnet [OI_Verified](https://testnet.bscscan.com/address/0x8A585c907645e768DAB31f0747d21c35D2Da7953#code) & [OI_Flagged](https://testnet.bscscan.com/token/0x5f4c4f81d8c0cf1e3e1422b831ed2a489cb48ad7#code) NFTs.

## ERC721 Standard with Adjustments:
- Soulbound, i.e. token cannot be transferred.
- Administrated, only contract owner, i.e. Open Info Custodian, may mint/burn any given token.

## Metadata
- Verified: `https://vrfd.info/verified/[token_id]`
- Flagged: `https://vrfd.info/flagged/[token_id]`
- JSON: 
```json
{
  "image": "https://vrfd.info/[ADDRESS]",
  "external_url": "https://vrfd.info/[ADDRESS]",
  "name": "[ADDRESS || ENS-DOMAIN].VRFD",
  "description": "[ADDRESS] has been [verified || flagged] by Open-Info, with a Souldbound-NFT.",
  "Attributes": [
    {
      "trait_type": "VRFD?",
      "value": "['VRFD 🗸' || 'FLAGGED X']"
    },
    {
      "trait_type": "upvotes",
      "value": "22"
    },
    {
      "trait_type": "downvotes",
      "value": "12"
    }
  ]
}
```

## OI custodian Functions

### safeMint & safeMintMultiple
`safeMint` is a public function that allows the contract owner to mint a new OI-verified token. The function increments the `_tokenIdCounter` and emits a `Mint` event when the token is minted.
`safeMintMultiple` is a public function that allows the contract owner to mint multiple OI-verified tokens at once. The function increments the `_tokenIdCounter` for each token and emits a `Mint` event for each token that is minted.

### revoke AKA burn
`revoke` AKA `burn` is an external function that allows the contract owner to burn an OI-verified token. This function removes the token from the owner's account.

### updateBaseUrl
`updateBaseUrl` is an external function that allows the contract owner to update the `baseURI` variable.
