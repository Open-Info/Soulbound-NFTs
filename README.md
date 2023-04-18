# 👾 Soulbound Certification
Irrefutable source of truth.

### Modified ERC721 Functions:

#### safeMint

`safeMint` is a public write function that allows users to mint a new OI-verified SNFT, given that they have registered accordingly. In the case of certified or flagged SNFTs, only the contract owner may call this function. The function increments the `_tokenIdCounter` and emits a `Mint` event when the token is minted.&#x20;

#### safeMintMultiple

`safeMintMultiple` is a public function that allows the contract owner to mint multiple OI-verified tokens at once. The function increments the `_tokenIdCounter` for each token and emits a `Mint` event for each token that is minted.

#### revoke AKA burn

`revoke` AKA `burn` is a public write function that allows only the contract owner to burn an OI-verified, certified,  or flagged token. This function transfers the token from the owner's account to the zero address. It is acceptable to burn any given Soulbound NFT only under the following conditions.

1. It was successfully proven through a dispute claim that the given address was falsely flagged.&#x20;
2. The current terms under which the original Soulbound NFT was minted are no longer valid.
3. Under the owner's request to de-register.

### Unique SNFT Functions

#### beforeTokenTransfer

The `beforeTokenTransfer` function is called before any attempt to transfer a token. This function always fails if the sender is not equal to the zero address, which Soulbounds the token to its receiver. If the receiver is equal to the zero address (a burn attempt) the function only passes if it is called by the Open Info Custodian.

## Metadata

By using the ERC-721 standard, Soulbound NFTs can also be easily integrated with other applications and platforms that support ERC-721 tokens, expanding their usefulness and potential applications.&#x20;

The standard metadata JSON for an Open Info Verified, Certified or Flagged Soulbound NFT:

```json
{
  "image": "https://vrfd.info/[ADDRESS]",
  "external_url": "https://vrfd.info/[ADDRESS]",
  "name": "[ADDRESS || ENS-DOMAIN].VRFD",
  "description": "[ADDRESS] has been [verified || flagged] by Open-Info, with a Souldbound-NFT.",
  "Attributes": [
    {
      "trait_type": "VRFD?",
      "value": "['VRFD 🗸' || 'CRTFD $' || 'FLAGGED X']"
    },
    {
      "trait_type": "upvotes",
      "value": "22"
    },
    {
      "trait_type": "downvotes",
      "value": "12"
    },
    {
      "trait_type": "Reported By",
      "value": "[ADDRESS]"
    }
  ]
}
```
