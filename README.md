# Blockchain ID (DRAFT Specification)

This is a DRAFT for an Internet specification that describes a blockchain-based identity __format__ that's intended to serve as a decentralized replacement for login systems such as:

- OpenID
- Facebook login
- Mozilla persona
- GitHub login

It provides a foundation upon which a blockchain-based, blockchain-agnostic, *usable* Web of Trust (WoT) system can be built that has the potential to:

- Verify the identity of an individual based solely on their username (which can be a traditional username, or an email address).
- Verify that someone is a member of your church/group/org (publicly, or privately to group members only).
- Verify that a community member is allowed to vote in an election.

## Motivation

Traditional login systems have identities that are owned by corporations instead of by the individuals to whom those identities belong.

Companies can use their ownership of your identity to take it away from you, to censor you, and otherwise manipulate you.

With the blockchain, it is possible to say: "I am me, and here's what I'd like you to know about me." and provide easy-to-verify proof of that fact.

## Format Specification

Blockchain ID augments other ID systems (like [Openname Profiles](https://github.com/openname/openname-specifications)) with two extra key/value pairs:

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

TBD