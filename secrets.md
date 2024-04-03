<h1 align="center">
    <img align="left" width="100" height="100" src="https://www.google.com/photos/about/static/images/ui/logo-photos.png" alt="Zetafence"/>
    <br />
    <p style="color: #808080; text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);">
    ZetaFence Secret Preservation
    </p>
</h1>

<br/>

## Underlying Motivations

Whether user attributes, JWT, service tokens, or other senstive attributes, Zetafence takes extra precautions to preserve those. Following is a summary of design of the secret preservation system.

## Problem

A company needs to secure their vault. If a single person knows the code to the vault, the code might be lost or unavailable when the vault needs to be opened. If there are several people who know the code, they may not trust each other to always act honestly. SSS can be used in this situation to generate shares of the vault's code which are distributed to authorized individuals in the company. The minimum threshold and number of shares given to each individual can be selected such that the vault is accessible only by (groups of) authorized individuals. If fewer shares than the threshold are presented, the vault cannot be opened.

## Group JWT Semantics

- JWT tokens are typically provided to authenticate an user/application, verify authenticity of the source,
  and authorize specific roles & permissions against the holder of token
- Zetafence extends those authn/authz semantics, authencity, and integrity by adding threshold (k, n)
  secret-sharing technique
- A single Group JWT token, issued by Zetafence, is enough to authn/authz an user belonging to a group to
  perform certain action on behalf of the group e.g. admin privilege to certain resources
- Within a single group, k-out-of-N JWT tokens are needed to collectively authn/authz a certain token secret,
  just as SSS mandates. And that no m < k will be able to obtain the secret token

## Advantages of Zetafence Group JWT Application

- Minimal edits are required to "repurpose" your authz semantics, and hence leads to quicker convergence
- Distributed authorization among mutually trusting parties
- Minimizing leaks of tokens, passwords, API keys, etc.

## References

- [Shamir's Secret Sharing (SSS)](https://en.wikipedia.org/wiki/Shamir%27s_secret_sharing)
- [Hashicorp Vault Seal/Unseal](https://developer.hashicorp.com/vault/docs/internals/architecture)

<br/>Copyright (C)
    <a href="https://zetafence.com">
    <img align="center" width="85" src="https://img.shields.io/badge/Zetafence-8A2BE2" alt="Zetafence"/></a>
2024.
