# substrate-voting

[![Check Set-Up & Build](https://github.com/matias-gonz/substrate-voting/actions/workflows/check.yml/badge.svg)](https://github.com/matias-gonz/substrate-voting/actions/workflows/check.yml)

This is a substrate proof of concept that includes a custom voting pallet. The voting pallet allows users to cast votes for candidates and retrieve voting results.

## Usage

### Build

```sh
cargo build --release
```

### Run local dev

```sh
cargo build --release -- --dev
```

### Connect front end apps

You can interact with it using the
hosted version of the [Polkadot/Substrate
Portal](https://polkadot.js.org/apps/#/explorer?rpc=ws://localhost:9944)
front-end by connecting to the local node endpoint.

You can also use the [Substrate Front End Template](https://github.com/substrate-developer-hub/substrate-front-end-template).

## Voting pallet

The voting pallet is a module in the substrate-voting proof of concept that handles the voting functionality. It allows users to cast votes and retrieve voting results.

### Storage

`HasVoted` is a mapping of account addresses to a boolean value indicating whether the corresponding account has voted (`true`) or not (`false`).

`CandidateVotes` is a mapping that associates candidate ids with the number of votes they have received.

### Dispatchable functions

`vote` is a dispatchable function that allows users to cast votes for candidates. It takes a candidate id as an argument and increments the vote count for the candidate.

### Events

`SomeoneVoted` is an event that is emitted when a user casts a vote. It includes the account address of the voter and the candidate id they voted for.

### Errors

`AlreadyVoted` is an error that is returned when a user tries to vote more than once.
`CandidateNotFound` is an error that is returned when a user tries to vote for a candidate that does not exist.

## Future work

- Add more dispatchable functions to allow for more complex voting scenarios.
- Implement a more sophisticated voting system with multiple rounds of voting.
- Make the voting secret and anonymous.
