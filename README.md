# CrowdFunding Smart Contract

## Overview

This project consists of a Solidity smart contract named `CrowdFunding` for managing a crowdfunding campaign on the Ethereum blockchain. The contract allows participants to contribute funds towards a fundraising target within a specified deadline. The funds will be managed by a designated manager, and contributors have the ability to vote on requests made by the manager for accessing the funds.

## Smart Contract Details

### Contract Specifications

- **License:** GPL-3.0
- **Solidity Version:** >=0.5.0 <=0.9.0

### State Variables

1. `contributions`: Mapping that tracks the contributions made by each participant.
2. `target`: The fundraising target in Ether.
3. `deadline`: The timestamp representing the deadline for the crowdfunding campaign.
4. `manager`: The Ethereum address of the manager who initiates and controls the campaign.
5. `raisedVal`: The total amount of Ether raised.
6. `contributorsCount`: The number of contributors to the campaign.
7. `minContr`: The minimum contribution amount required from each participant.

### Structs

1. `requestAccess`: Structure defining a request made by the manager to access funds. It includes a description, recipient address, value, grade, completion status, voters count, and a mapping of voters.

### Functions

1. **Constructor**
   - Initializes the crowdfunding campaign with a target, deadline, and minimum contribution amount.

2. **getEther**
   - Allows participants to contribute Ether to the campaign within the deadline.

3. **getBalance**
   - Returns the current balance of the smart contract.

4. **requestRefund**
   - Allows contributors to request a refund if the fundraising target is not met by the deadline.

5. **onlyManager Modifier**
   - Ensures that only the manager can call certain functions.

6. **createRequest**
   - Allows the manager to create a request for accessing funds, specifying a description, recipient, value, and grade.

7. **random**
   - Generates a pseudo-random number based on block information.

8. **selectReceiver**
   - Randomly selects a request index as the winner.

9. **showWinner**
   - Returns the index of the selected winner.

10. **voteRequest**
    - Allows contributors to vote for a specific request.

11. **makePayment**
    - Allows the manager to make a payment to the selected recipient if the request is approved by the majority of voters.

## How to Use

1. Deploy the `CrowdFunding` smart contract on the Ethereum blockchain.
2. Set the target fundraising amount, campaign deadline, and minimum contribution amount during deployment.
3. Participants can contribute Ether to the campaign using the `getEther` function.
4. The manager can create requests using the `createRequest` function.
5. Participants can vote for requests using the `voteRequest` function.
6. After the deadline, the manager can use the `makePayment` function to make a payment to the selected recipient.

**Note:** Ensure that the manager does not have access to funds until participants vote and approve the request.
