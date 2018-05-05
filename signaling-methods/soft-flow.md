# Soft Flow

### A signaling strategy for the Strange Loop hard fork framework.

Signals can take many forms, from soft, off-chain signaling like social media, to more hard commitments, like burning assets in a way that they will only be usable on a resulting chain.

Users can publish the conditions under which they would fork. This could take the form of any smart contract, as implied by the Strange Loop `supportsProposal` method.

The implementation of this method can have policies like "all of us or none of us", with a list of required other accounts that should signal a similar support.

The algorithm might go like this:

The WouldSupportIf procedure:
- If the account has explicitly expressed they would or would not, return that result.
- Define set D, the set of accounts that the current account that requires `wouldSupportIf`.
- Define set W, as the subset of D that either:
  - Would support the fork.
  - WouldSupportIf the caller supported the fork.
  - Returns true for its own wouldSupportIf procedure.
- If D = W, return true.

