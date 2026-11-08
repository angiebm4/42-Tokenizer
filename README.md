# 42-Tokenizer

# 42Corrections

**A token-based correction points system built on BNB Smart Chain.**

## 1. Introduction

42Corrections is a blockchain-based project designed to explore how tokenization and smart contracts could be used to manage a peer-to-peer correction points system.

The project takes inspiration from the correction system used in 42 schools, where students participate in peer evaluations. Students use Valuation Points (Ev.P) to access corrections, while students who perform corrections receive points in return.

The objective is to create an independent prototype that reproduces some of these mechanisms using a token and smart contracts.

The first version will not connect to the 42 platform or depend on its API. It will work independently, using test accounts and simulated corrections. However, its architecture will be designed with possible future integrations in mind.

## 2. Motivation and problem statement

The idea behind 42Corrections comes from observing some limitations and challenges in the current peer-correction process.

### 2.1. Correction assignment

Students select correction slots according to the availability published by other students. This system can encourage people to coordinate with friends and repeatedly refresh the calendar to find specific slots, potentially undermining the intended assignment process.

### 2.2. Diversity and quality of corrections

Not all students have the same knowledge or experience.

There are three useful types of correction profiles:

- **Peer:** someone working on the same project or at a similar level. This allows students to exchange knowledge and approaches.
- **More experienced student:** someone who has already completed the project or has greater knowledge and can provide more advanced feedback.
- **Beginner:** someone who has less experience with the project. Explaining concepts and teaching others can also be a valuable learning experience.

Receiving corrections from different profiles can help students develop both technical knowledge and communication skills.

### 2.3. Availability of correctors

The number of students available to perform corrections can be limited. A system that distributes correction opportunities and rewards participation fairly could help encourage more students to contribute.

### 2.4. Valuation Points distribution

The existing system uses Valuation Points (Ev.P). Students receive points when they perform corrections and spend points when they receive them. The amount can vary depending on the project.

Point shortages and unequal accumulation can affect the availability of corrections.

There is also an existing donation mechanism called the correction pool. Students can voluntarily donate points to this pool. When it reaches a certain threshold, a special period begins:

- Receiving corrections becomes free.
- Correctors receive double their normal reward.
- The special period continues until the available pool funds are exhausted.

42Corrections uses this mechanism as inspiration for one of its planned extensions.

## 3. Project objectives

The main objectives are:

1. Learn how blockchain technology and smart contracts work in practice.
2. Develop and deploy a token compatible with the BEP-20 standard.
3. Understand token creation, balances, transfers and permissions.
4. Explore how smart contracts can manage a points-based incentive system.
5. Implement a donation pool and a temporary reward mechanism as an extension.
6. Design the project so that it can evolve into a larger correction management platform in the future.

The initial priority is learning and understanding the technology, while respecting the requirements of the Tokenizer assignment.

## 4. Technical decisions

### 4.1. Blockchain

**BNB Smart Chain Testnet**

BNB Smart Chain was selected because the Tokenizer assignment is presented in the context of a partnership between 42 and BNB Chain.

It is EVM-compatible, which makes it possible to use Solidity and tools from the Ethereum ecosystem.

The project will initially be deployed on a test network. No real money or mainnet transactions are required for development.

### 4.2. Smart contract language

**Solidity**

Solidity is used to develop smart contracts for EVM-compatible blockchains.

Learning Solidity will provide transferable knowledge applicable to BNB Smart Chain, Ethereum and other EVM-compatible networks.

### 4.3. Token standard

**BEP-20**

The token will follow the BEP-20 standard, which provides the common functionality expected from fungible tokens on BNB Smart Chain.

The implementation will use OpenZeppelin contracts where appropriate, rather than unnecessarily implementing standard token functionality from scratch.

### 4.4. Development tools

The initial development environment will use:

- Remix IDE: writing, compiling and deploying contracts.
- MetaMask: interacting with the test network.
- OpenZeppelin: reusable and standardised smart contract implementations.
- BNB Smart Chain Testnet: deployment and testing environment.
- BscScan Testnet: inspecting transactions and deployed contracts.

Additional tools may be introduced as the project evolves.

## 5. Token design

### 5.1. Token identity

| Property | Value |
|---|---|
| Name | 42Corrections |
| Symbol | 42C (provisional) |
| Intended unit | Valuation Points (Ev.P) |
| Blockchain | BNB Smart Chain |
| Standard | BEP-20 |
| Language | Solidity |
| Decimals | 18 (initial proposal) |

The name 42Corrections was chosen because it reflects the purpose of the project: managing points used in peer corrections.

The symbol 42C is provisional. Ev.P is the terminology used to describe the points within the correction system.

### 5.2. Token purpose

The token represents correction points within the prototype.

It is not intended to be a speculative cryptocurrency or a token with real monetary value.

Its purpose is to experiment with:

- Managing user balances.
- Transferring points.
- Rewarding correction activities.
- Donating points to a shared pool.
- Distributing rewards according to predefined rules.

### 5.3. Supply and distribution

The total supply and initial distribution have not yet been finalised.

The design will consider:

- Initial balances for participants.
- A possible allocation for the correction pool.
- Whether additional tokens can be issued.
- Which accounts or contracts can perform administrative operations.

The current 42 system provides an initial reference of five Ev.P per student, but the prototype's final supply and distribution model will be defined during implementation.

## 6. Project scope

Development will be divided into two main stages.

### 6.1. Stage 1 — Basic token

The first stage focuses on implementing a functional BEP-20 token.

Expected functionality:

- Create the initial token supply.
- Assign tokens to an initial wallet or predefined test accounts.
- Check account balances.
- Transfer tokens between addresses.
- Check the total supply.
- Support standard token approvals and delegated transfers.
- Understand and document ownership and permissions.

This stage is the core of the Tokenizer assignment and must be completed before adding unnecessary complexity.

### 6.2. Stage 2 — Correction pool

Once the basic token is implemented, tested and deployed, the project can be extended with a correction pool.

The pool will simulate the donation and reward mechanism.

Planned functionality:

1. Allow users to donate tokens voluntarily.
2. Hold donated tokens in a shared contract.
3. Track the pool balance.
4. Define a configurable activation threshold.
5. Activate a special correction period when the threshold is reached.
6. Make corrections free during that period.
7. Double the normal reward received by correctors.
8. End the special period when the available funds are exhausted.

The pool must not create tokens without authorisation or distribute rewards that it cannot fund.

## 7. Future development

The first version will deliberately remain independent of the 42 platform.

However, the project is intended to be extensible.

Possible future improvements include:

### 7.1. Correction management

- Register correction activities.
- Define correction costs and rewards according to the project.
- Maintain correction histories.
- Prevent excessive repeated corrections between the same participants.

### 7.2. Corrector profiles

Introduce different correction profiles:

- Peer.
- More experienced student.
- Beginner.

These profiles could be used by a future assignment system to promote diversity and learning.

### 7.3. Common Core and Outer Core

Introduce different correction policies depending on the educational stage.

For example, Common Core could have stricter limits on repeated corrections, while Outer Core could allow more flexibility due to lower corrector availability.

### 7.4. External platform integration

Investigate whether the 42 platform provides an authorised API that exposes relevant information, such as:

- Projects and correction requirements.
- Correction costs and rewards.
- User correction history.
- Available correction slots.
- Valuation Points balances.
- Correction pool parameters.

An external backend would be needed to retrieve and validate information from an API and communicate authorised operations to the smart contracts.

This integration is outside the scope of the initial Tokenizer implementation.

## 8. Architecture

The proposed architecture separates token functionality from correction management.

### 8.1. EvPToken

The main token contract.

Responsibilities:

- Implement the BEP-20 token standard.
- Manage balances and transfers.
- Define the initial supply.
- Control authorised token issuance, if enabled.

### 8.2. CorrectionPool

An independent contract that interacts with the token.

Responsibilities:

- Receive donations.
- Track the available balance.
- Manage the activation threshold.
- Control the special correction period.
- Distribute funded rewards.

### 8.3. Future CorrectionManager

A possible future contract responsible for correction operations.

Responsibilities could include:

- Registering corrections.
- Applying project-specific costs and rewards.
- Tracking repeated corrections.
- Applying correction rules.

This contract is not required for the first implementation.

## 9. Implementation roadmap

The project will be developed incrementally.

### Phase 1 — Understand the foundations

- [ ] Understand blockchain transactions, wallets and smart contracts.
- [ ] Understand the EVM and Solidity.
- [ ] Understand BEP-20 and ERC-20.
- [ ] Understand token supply, balances and decimals.
- [ ] Understand ownership and contract permissions.

### Phase 2 — Build the token

- [ ] Define the final token parameters.
- [ ] Create the Solidity contract.
- [ ] Use OpenZeppelin's ERC-20 implementation.
- [ ] Compile the contract.
- [ ] Understand the constructor and inherited functions.
- [ ] Test token creation and initial distribution.

### Phase 3 — Test token functionality

- [ ] Check balances.
- [ ] Transfer tokens between test wallets.
- [ ] Test approvals.
- [ ] Test delegated transfers.
- [ ] Check total supply.
- [ ] Test invalid operations and insufficient balances.
- [ ] Review security and permissions.

### Phase 4 — Deploy the token

- [ ] Configure MetaMask for BNB Smart Chain Testnet.
- [ ] Deploy the token using Remix.
- [ ] Record the contract address.
- [ ] Verify the deployment on the testnet explorer.
- [ ] Interact with the deployed contract.

### Phase 5 — Document the mandatory implementation

- [ ] Explain the technical decisions.
- [ ] Document token functionality.
- [ ] Explain deployment and interaction.
- [ ] Record the network and contract address.
- [ ] Prepare the documentation required by Tokenizer.

### Phase 6 — Implement the correction pool

- [ ] Design the pool contract.
- [ ] Connect it to the token contract.
- [ ] Implement donations.
- [ ] Implement a configurable threshold.
- [ ] Implement special period activation.
- [ ] Implement double rewards.
- [ ] Prevent rewards exceeding available funds.
- [ ] Test pool exhaustion and period termination.

### Phase 7 — Future improvements

- [ ] Investigate the 42 API and its access conditions.
- [ ] Design an external backend.
- [ ] Implement correction registration.
- [ ] Introduce correction profiles.
- [ ] Explore correction assignment rules.
- [ ] Consider a web interface.

## 10. Security considerations

Security is an important part of the project.

The implementation should consider:

- Restricting administrative functions to authorised accounts.
- Preventing unauthorised token issuance.
- Preventing transfers or rewards that exceed available balances.
- Checking that only valid operations can activate or end special periods.
- Avoiding double rewards for the same correction.
- Protecting against reentrancy and other smart contract vulnerabilities where relevant.
- Testing edge cases before deployment.

The initial implementation will use testnet tokens only.

## 11. Repository structure

The proposed repository structure is:

```text
42Corrections/
│
├── README.md
│
├── code/
│   ├── 42CorrectionsToken.sol
│   └── CorrectionPool.sol
│
├── deployment/
│   └── deployment instructions and scripts
│
├── documentation/
│   ├── token-design.md
│   ├── architecture.md
│   ├── security.md
│   └── usage.md
│
└── tests/
    └── contract tests
```

`CorrectionPool.sol` and the tests directory will be added when the corresponding development stages begin.

## 12. Final considerations

42Corrections starts as a learning project focused on blockchain and smart contract development.

The objective is not to reproduce the entire 42 correction platform, but to implement a small, understandable and extensible prototype inspired by a real problem.

The project prioritises understanding the technology, building a correct token implementation and learning how smart contracts interact.

Future features will only be added after the core requirements have been completed and tested.

**The guiding principle is to build something small that works, understand every part of it, and leave room to make it bigger later.**
