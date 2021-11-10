# immortal.audit0
immortal.farm first audit

The share token referenced in eqv.sol is here: https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC20/presets/ERC20PresetMinterPauser.sol

In order to set up the contracts correctly you must do the following:
1. Deploy MultiVault from eqv.sol
2. Deploy CustomERC20PresetMinterPauser from mods.sol
3. call declareShareAddress with the share address
4. grant the MultiVault a Minter Role
5. Deposit exactly 1 FTM into the contract as the initial deposit (in the live version, the wallet that does the initial deposit will have its private key burned so that it can never be withdrawn).
6. Now the contract is ready to go.
7. When withdrawing, you must first approve the spending enough of the share tokens by the vault.

![image](https://user-images.githubusercontent.com/92181746/137048281-48be78e1-2e33-4f74-b546-4e26494ba835.png)
![image](https://user-images.githubusercontent.com/92181746/137048321-dcd86743-d1dd-4855-9aa9-16ce82d7be0b.png)
