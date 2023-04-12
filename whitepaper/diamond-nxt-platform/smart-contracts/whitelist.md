# Whitelist

The `Whitelist` smart contract provided here is an implementation of a basic whitelist system using the AccessControl contract from the OpenZeppelin library. The purpose of this contract is to maintain a list of approved addresses that can interact with specific features or functions in the associated platform. The smart contract has the following main features:

1. **Roles**: The contract defines two distinct roles: the `DEFAULT_ADMIN_ROLE` and the `WHITELISTER_ROLE`. The admin can add or remove whitelister role from other accounts, while the whitelister can add or remove addresses from the whitelist.
2. **Constructor**: The constructor function takes two arguments: `_admin` and `_whitelister`. These arguments are used to set up the initial admin and whitelister roles when the contract is deployed.
3. **isWhitelisted**: This view function checks if a given account is in the whitelist. It takes an address as an argument and returns a boolean value indicating whether the account is whitelisted.
4. **whitelistAccount**: This function adds an address to the whitelist. It takes an address as an argument, and only a whitelister can call this function. Upon successful execution, it emits a `Whitelisted` event with the account address.
5. **blacklistAccount**: This function removes an address from the whitelist. It takes an address as an argument, and only a whitelister can call this function. Upon successful execution, it emits a `Blacklisted` event with the account address.
6. **batchWhitelist**: This function allows a whitelister to add multiple addresses to the whitelist in a single transaction. It takes an array of addresses as an argument and iterates through the array, calling the `whitelistAccount` function for each address.
7. **addWhitelister** and **removeWhitelister**: These functions allow the admin to grant or revoke the whitelister role to/from other accounts. They take an address as an argument and can only be called by an account with the admin role.

In summary, this smart contract serves as a simple yet effective implementation of a whitelist system with role-based access control. The contract allows admins and whitelisters to manage the whitelist and control which accounts can interact with specific functions within the associated platform.
