# passky

A CLI password manager for teams, built on [Pubky Core](https://github.com/pubky/pubky-core).

> **Work in progress** -- not usable yet.

## What is this?

`passky` is a team password manager inspired by [pass](https://www.passwordstore.org/) and [gopass](https://github.com/gopassio/gopass). Like its predecessors, it follows the Unix philosophy of *doing one thing well*: passky is the glue between existing, proven tools -- not a reimplementation of them.

- **Encryption** -- Passwords are encrypted with the Pubky of every user who has access, so sharing is built into the data model.
- **Storage** -- Encrypted data lives on Pubky Homeservers. No extra server to run.
- **Trust** -- Pubky's existing web of trust means you can start sharing passwords with people you already know and trust on Pubky, with no separate key exchange.

## Why Pubky?

Traditional team password managers either require a central server you have to trust, or bolt on their own key management. Pubky already solves identity, trust, and storage -- passky just wires those pieces together for the specific use case of shared secrets.

## Design goals

- **CLI only** -- scriptable, composable, no GUI.
- **Minimal glue** -- delegate encryption, storage, and trust to Pubky Core; only implement what's missing.
- **Team support** -- works well for personal use, like syncing passwords across devices, but the main goal is sharing secrets within a team.
- **[Pubky Ring](https://github.com/pubky/pubky-ring) integration** -- planned once Pubky Ring supports it, either via direct decryption or by signing device subkeys.

## Security disclaimer

`passky` is only as secure as your Pubky identity. If your private key is compromised, all passwords encrypted for that key become publicly accessible -- there is no additional layer of protection. Guard your seed and private key accordingly.
