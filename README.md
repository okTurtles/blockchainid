# Blockchain ID

Blockchain ID is intended as:

__1. A decentralized replacement for all of today's login systems, including:__

- OpenID
- Facebook login
- Mozilla persona
- GitHub login

__2. A foundation upon which to build a blockchain-based, *usable* Web of Trust (WoT) system__

Potential applications of blockchain-based WoT:

- Verifying that someone is a member of your church/group/org (publicly, or privately to group members only)
- Verifying that a community member is allowed to vote in an election

## Why?

Traditional login systems have identities that are owned by corporations instead of by the individuals to whom those identities belong.

Companies can use their ownership of your identity to take it away from you, to censor you, and otherwise manipulate you.

With the blockchain, you can say: "I am me, and here's what I'd like you to know about me." and provide easy-to-verify proof of that fact.

## Format

Blockchain ID augments other ID systems (like [Openname Profiles](https://github.com/openname/openname-specifications)) with two extra keys:

- __"keys"__
- __"attestations"__

```json
{
    "keys": {
        "pub": "{curve25519}aoisjf8fj23894u23u8jasdfjafd/=",
        "priv": "{scrypt,curve25519}aoisjf8fj23894u23u8jasdfjafd/="
    },
    "attestations": {

    }
}
```
