# -Aave-Vault-Safety
 Aave Vault

An ERC-4626 vault which allows users to deposit/withdraw ERC-20 tokens supported by Aave v3, manages the supply and withdrawal of these assets in Aave, and allows a vault manager to take a fee on yield earned.
Instructions

To compile/build the project, run forge build.

To run the test suite, run forge test.
Tests

Some of the tests rely on an RPC connection for forking network state. Make sure you have an .env file in the root directory of the repo with the following keys and values:

POLYGON_RPC_URL=[Your favourite Polygon RPC URL]
AVALANCHE_RPC_URL=[Your favourite Avalanche RPC URL]

The fork tests all use Polygon, except tests for claiming Aave rewards, which use Avalanche.

This test suite also includes a16z's ERC-4626 Property Tests, which are in the ATokenVaultProperties.t.sol file. These tests do not use a forked network state but rather use mock contracts, found in the test/mocks folder.
Deployment

To deploy the vault contract, first check that the deployment parameters in script/Deploy.s.sol are configured correctly, then check that your .env file contains these keys:

POLYGON_RPC_URL=xxx
MUMBAI_RPC_URL=xxx
ETHERSCAN_API_KEY=xxx
PRIVATE_KEY=xxx

Then run:

source .env

Then run one of the following commands:

Mumbai Testnet:

forge script script/Deploy.s.sol:Deploy --rpc-url $MUMBAI_RPC_URL --broadcast --verify --legacy -vvvv

Polygon Mainnet:

forge script script/Deploy.s.sol:Deploy --rpc-url $POLYGON_RPC_URL --broadcast --verify --legacy -vvvv

Audits

You can find all audit reports under the audits folder

    01-03-2023 OpenZeppelin
    03-03-2023 PeckShield
    18-06-2023 Certora

License
All Rights Reserved © Aave Labs - AaveSAFE edition
