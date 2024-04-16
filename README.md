# Seaport Conduit Smart Contract Review

Prepared by: David Dada

## Scope
- **Conduit.sol** - https://github.com/ProjectOpenSea/seaport/blob/main/contracts/conduit/Conduit.sol
    https://github.com/ProjectOpenSea/seaport-core/blob/main/src/conduit/Conduit.sol

- **ConduitInterface.sol** - https://github.com/ProjectOpenSea/seaport-types/blob/main/src/interfaces/ConduitInterface.sol

- **ConduitEnums.sol** - https://github.com/ProjectOpenSea/seaport-types/blob/main/src/conduit/lib/ConduitEnums.sol

- **TokenTransferrer.sol** - https://github.com/ProjectOpenSea/seaport-core/blob/main/src/lib/TokenTransferrer.sol

- **ConduitStructs.sol** - https://github.com/ProjectOpenSea/seaport-types/blob/main/src/conduit/lib/ConduitStructs.sol

- **ConduitConstants.sol** - https://github.com/ProjectOpenSea/seaport-types/blob/main/src/conduit/lib/ConduitConstants.sol

## Inheritance tree
```
└── Conduit.sol
    ├── ConduitInterface.sol
    │   └── ConduitStructs.sol
    │       ├── ConduitTransfer
    │       │   └── ConduitItemType
    │       │
    │       └── ConduitBatch1155Transfer
    │       
    ├── ConduitEnums.sol
    │   └── ConduitItemType
    │
    ├── TokenTransferrer.sol
    │   ├── TokenTransferrerConstants.sol
    │   ├── TokenTransferrerErrors.sol
    │   └── ConduitStructs.sol
    │       └── ConduitBatch1155Transfer
    │
    ├── ConduitStructs.sol
    │   ├── ConduitBatch1155Transfer
    │   └── ConduitTransfer
    │
    └── ConduitConstants.sol
```

## Limitations
No assessment can guarantee the absolute safety or security of a software-based system.
Further, a system can become unsafe or insecure over time as it and/or its environment evolves.
This assessment aimed to discover as many issues and make as many suggestions for
improvement as possible within the specified timeframe. Undiscovered issues, even serious
ones, may remain. Issues may also exist in components and dependencies not included in the
assessment scope.

## Findings
Findings and recommendations are listed in this section, grouped into broad categories. It is up to the team behind the code to ultimately decide whether the items listed here qualify as issues that need to be fixed, and whether any suggested changes are worth adopting. When a
response from the team regarding a finding is available, it is provided.
Findings are given a severity rating based on their likelihood of causing harm in practice and the  potential magnitude of their negative impact. Severity is only a rough guideline as to the risk an issue presents, and all issues should be carefully evaluated.

| **Severity Level Determination** |            |              | **Impact** |        |
|----------------------------------|------------|--------------|------------|--------|
|                                  |            | **High**     | **Medium** | **Low**|
|                                  | **High**   | Critical     | High       | Medium |
| **Likelihood**                   | **Medium** | High         | Medium     | Low    |
|                                  | **Low**    | Medium       | Low        | Low    |

Issues that do not present any quantifiable risk (as is common for issues in the Code Quality category) are given a severity of Informational.

## Contract Review
### `Conduit.sol`

