Create Aptos Dapp: Token Staking Dapp Template
==============================================

This template provides a comprehensive solution for a Token Staking Dapp, featuring a user-friendly, pre-designed UI. It can be easily customized and deployed to a live server.

Documentation for the Token Staking Dapp Template
-------------------------------------------------

To get started and explore more details about this template, visit the Token Staking Dapp Template Docs.

Overview
--------

*   This template enables the contract deployer to select any fungible asset for staking and rewards.
*   The reward creator, configured in the settings, can create reward schedules based on a reward per second (RPS) rate and duration (in seconds).
    *   Note: Currently, only one reward schedule is supported. For multiple reward schedules, multiple stake pools need to be deployed.
*   Users can stake assets and claim rewards based on the configured reward schedule.

Reward Calculation
------------------

*   The reward index is first calculated as the amount of reward per staked asset.
    
    bash
    
    Copy code
    
    `reward index = old_index + (current_ts - last_update_ts) * rps / total_stake`
    
*   Then, rewards for a user are calculated:
    
    bash
    
    Copy code
    
    `reward = user_stake * (reward_index - user_index_at_last_claim)`
    

Limitations
-----------

For simplicity, this template does not include a function to reclaim orphaned rewards after the schedule's duration has expired. A potential solution is transferring leftover rewards after the duration, but this could prevent users with pending rewards from claiming them.

Key Features of the Token Staking Template
------------------------------------------

*   **Stake Fungible Asset Page** - A dedicated page for token staking.
*   **Claim Staking Rewards** - A component allowing stakers to claim their rewards.
*   **Unstake Fungible Asset** - A component to unstake tokens.
*   **Create Incentivized Pool** - Allows a defined creator to create a rewards pool for a fungible asset.

### Tools Used in the Template

*   React framework
*   Vite development environment
*   shadcn/ui + Tailwind CSS for styling
*   Aptos TS SDK
*   Aptos Wallet Adapter
*   Node-based Move commands

### Available Move Commands

This template utilizes the [aptos-cli npm package](https://github.com/aptos-labs/aptos-cli), enabling Aptos CLI in a Node environment.

Some of the key commands included are:

*   `npm run move:publish` - Publishes the Move contract
*   `npm run move:test` - Runs Move unit tests
*   `npm run move:compile` - Compiles the Move contract
*   `npm run move:upgrade` - Upgrades the Move contract
*   `npm run deploy` - Deploys the dapp to Vercel

For additional CLI commands, run `npx aptos` to see the full list of available commands.