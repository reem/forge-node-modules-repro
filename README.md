forge error repro with node modules

Forked from https://github.com/paulrberg/solidity-template with contracts/aave.sol and @aave/governance-v2 installed with yarn.

```
> yarn install
...
> forge build -c contracts --lib-paths node_modules
...
/Users/reem/code/forge-node-modules-repro/contracts/aave.sol:3:1: ParserError: Source "@aave/governance-v2/contracts/interfaces/IAaveGovernanceV2.sol" not found: File outside of allowed directories.
import "@aave/governance-v2/contracts/interfaces/IAaveGovernanceV2.sol";
^----------------------------------------------------------------------^


/Users/reem/code/forge-node-modules-repro/contracts/aave.sol:4:1: ParserError: Source "@aave/governance-v2/contracts/governance/Executor.sol" not found: File outside of allowed directories.
import "@aave/governance-v2/contracts/governance/Executor.sol";
^-------------------------------------------------------------^
```

With remappings:

```
> forge build -c contracts --lib-paths contracts --remappings @aave/=node_modules/@aave/
success.
```
