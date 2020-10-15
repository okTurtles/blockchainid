# BlockchainID (DRAFT Specification)

**UPDATE: This spec is now being developed as part of the [Blockstack initiative](https://github.com/blockstack/blockchain-id/wiki)**

This is a DRAFT for an Internet specification that describes a blockchain-based identity __format__ that's intended to serve as a decentralized replacement for login systems such as:

>>> OpenID
>>> Facebook login
>>> Mozilla persona
>>> GitHub login

It provides a foundation upon which a blockchain-based, blockchain-agnostic, *usable* Web of Trust (WoT) system can be built that has the potential to:

>>> Verify the identity of an individual based solely on their username (which can be a traditional username, or an email address).
>>> Verify that someone is a member of your church/group/org (publicly, or privately to group members only).
>>> Verify that a community member is allowed to vote in an election.

## Usage Example

>>> With BlockchainID, users will be able to use a traditional username/password pair to log in to any website or service, and that service will be able to verify them using the information that's stored in a blockchain. It can be any blockchain that supports arbitrary key/value mappings (like Namecoin, Ethereum, NXT, etc.).
>>> Users can send each other end-to-end encrypted messages by knowing each other's BlockchainIDs in a MITM-proof way by retrieving information via blockchain nodes, thin-clients, or trusted servers like [DNSChain](https://github.com/okTurtles/dnschain).

## Motivation

Traditional login systems have identities that are owned by corporations instead of by the individuals to whom those identities belong.

Companies can use their ownership of your identity to take it away from you, to censor you, and otherwise manipulate you.

With the blockchain, it is possible to say: "I am me, and here's what I'd like you to know about me." and provide easy-to-verify proof of that fact to web applications and individuals alike.

## Format Specification

Blockchain ID augments other ID systems (like [Openname Profiles](https://github.com/openname/openname-specifications)) with two extra key/value pairs:

- __"keys"__
- __"endorsements"__

```json
{
    "blockchainid": {
        "version": "1",
        "keys": {
            "pub": "{curve25519}aoisjf8fj23894u23u8jasdfjafd/=",
            "priv": "{scrypt,curve25519}aoisjf8fj23894u23u8jasdfjafd/="
        },
        "endorsements": {

        }
    }
}
```

#### Keys

>>> Notice the `"priv"` key. Guess what that is? That's the user's private key that corresponds to `"pub"`. Currently the spec defaults to encrypting it using [scrypt + AES](https://www.tarsnap.com/scrypt.html). Yep. That means the password must be a strong one. Strength can be enforced in a similar manner to how Peerio and miniLock enforce password strength.
>>> `"priv"` is __optional.__ Applications may choose to not use BlockchainID in this manner, electing instead to store the private key on some secure device, or some other manner. However, storing the encrypted private key in the blockchain itself results in massive UX improvements to all software that requires users to authenticate. If necessary, users can always use password managers to generate the password with a cryptographically secure random number generator.

#### Endorsements

Endorsements are a way of endorsing some statement. They can be by users to affirm that someone else belongs to some group (secret or public), that someone trusts someone else, etc.

They can change the context in which users understand each other online.

We are still working out the details!

### TBD:

This is a work in progress. Format will be fully specified "soonish". You are welcome to join in and help with it! For now, just open an issue.

- Decide how to represent values like `curve25519`, `scrypt`, etc. Do we care about compressing those due to blockchain-specific space limitations or not?
- Decide format of `"keys"` and `"endorsements"`
- Show examples of `"endorsements"`
