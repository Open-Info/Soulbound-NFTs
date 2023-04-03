# Soulbound-NFTs
See BSC testnet [OI_Verified](https://testnet.bscscan.com/token/0xd968f13B4b2dD8606Da94F72fC0d10a230722527#balances) & [OI_Flagged](https://testnet.bscscan.com/token/0x53560A19F50fbe55a06418938ffd97428CDDd9Db#balances) NFTs.

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
