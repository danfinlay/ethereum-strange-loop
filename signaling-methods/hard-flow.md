# Hard Flow

### A coordination strategy for the Strange Loop hard fork framework.

An extension of [./soft-flow.md](Soft Flow) that includes on-chain enforcement.

Beyond signaling, hard economic commitments could allow accounts to unambiguously define their commitment to a particular fork.

This could be implemented by encoding `wouldSupportIf` logic in a smart contract that controls some collateral or asset. This asset could be a small deposit, or it could be a commitment for a contract to self destruct on one side of a fork.

For other accounts implementing `wouldSupportIf` flows that depend on this hard-signaling account, the account may weigh this commitment more heavily than a normal `true` from  `wouldSupportIf`, since this dependency is now more grave.

This would require a revised version of the `wouldSupportIf` method that defines the different weight the account would give a dependency if it hard-commits in different ways to that fork proposal. Since there are different ways to hard-commit, this could be a bit complicated to implement, and would benefit from some standardization.

