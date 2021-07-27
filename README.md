# open-core-licensing-demo

This repo demonstrates how open core can be achieved with Golang.

- `oss.go` contains the `hello()` function for open source use
- `not_oss.go` contains the `hello()` function for closed source use

Which one is used is determined by the build tag provided.

Some licenses, such as Mozilla Public License 2.0 (a weak copyleft license), allow for use OSS within 'larger works' of software, with the commercial code present in separate files.

This is how Hashicorp's Open Core Vault product works. There are no-op open source stubs for enterprise features: https://github.com/hashicorp/vault/blob/d341378c6353a9e0f776ca024215ea11be8672df/vault/policy_util.go

In practice, an enterprise build would involve applying the enterprise patchset, and then running the build with the `enterprise` tag.

## Demonstration

```bash
dustin $ go run hello
hello from oss!

dustin $ go run -tags=enterprise hello
hello from enterprise!
```
