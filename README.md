# Foundry DAO F23

This repository is designed for a Decentralized Autonomous Organization (DAO). These contracts facilitate governance, token management, and data storage within the DAO ecosystem.

## Table of Contents

- [Box Contract](#box-contract)
- [GovToken Contract](#govtoken-contract)
- [TimeLock Contract](#timelock-contract)
- [MyGovernorTest Contract](#mygovernortest-contract)
- [Development Environment](#development-environment)

---

## Box Contract

**Overview**
The `Box` contract is a simple example contract that stores an unsigned integer value. It inherits from the `Ownable` contract provided by OpenZeppelin, allowing only the owner to update the stored value.

**Functions**

- `store(uint256 newNumber)`: Allows the owner to update the stored value.
- `getNumber()`: Allows anyone to retrieve the current stored value.

---

## GovToken Contract

**Overview**
The `GovToken` contract is an ERC-20 token with additional features such as permit functionality and support for governance votes. It inherits from OpenZeppelin's `ERC20`, `ERC20Permit`, and `ERC20Votes` contracts.

**Functions**

- `mint(address to, uint256 amount)`: Allows minting new tokens.
- `_afterTokenTransfer(address from, address to, uint256 amount)`: Internal function for handling token transfers.
- `_mint(address to, uint256 amount)`: Internal function for minting tokens.
- `_burn(address account, uint256 amount)`: Internal function for burning tokens.

---

## TimeLock Contract

**Overview**
The `TimeLock` contract is a governance timelock controller provided by OpenZeppelin. It sets a minimum delay before executing proposals and defines roles for proposers and executors.

**Constructor Parameters**

- `minDelay`: Minimum time delay before proposal execution.
- `proposers`: List of addresses that can propose.
- `executors`: List of addresses that can execute proposals.

---

## MyGovernorTest Contract

**Overview**
The `MyGovernorTest` contract is a test suite for a governance system. It demonstrates how to create and execute proposals using the `MyGovernor` contract, and it interacts with the `Box` contract for testing purposes.

**Functions**

- `setUp()`: Initializes contracts and roles for testing.
- `testCantUpdateBoxWithoutGovernance()`: Tests that the `Box` contract cannot be updated without governance.
- `testGovernanceUpdatesBox()`: Tests the governance process by proposing and executing a change to the `Box` contract.

---

## Development Environment

**Overview**
This repository includes development environment setup and automation using `make` commands. It also includes a `.env` file for configuration.

**Make Commands**

- `make clean`: Clean the repository.
- `make remove`: Remove Git modules and reset `.gitmodules`.
- `make install`: Install necessary dependencies.
- `make update`: Update dependencies.
- `make build`: Build the project.
- `make test`: Run tests.
- `make snapshot`: Create a snapshot.
- `make format`: Format code.
- `make anvil`: Run Anvil for code quality analysis.

**Deployment**

- `make deploy [ARGS=...]`: Deploy contracts to a specific network. Example: `make deploy ARGS="--network sepolia"`.

**Create Subscription**

- `make createSubscription`: Create a subscription using the deployed contracts.

---

Feel free to explore each contract's source code for more details and documentation. You can also refer to the provided `make` commands for common development and deployment tasks.

## Contributing

Contributions to the Beans Staking Dapp are welcome! If you have any ideas, improvements, or bug fixes, please create a pull request. Make sure to include a detailed description of your changes.

## License

The Beans Staking Dapp is open source and available under the [MIT License](LICENSE). Feel free to use, modify, and distribute it as per your needs.nse

These contracts are licensed by: MIT.
