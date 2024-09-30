<h1 align="center">
    <img align="left" width="100" height="100" src="https://zetafence.com/images/logo.png" alt="Zetafence"/>
    <br />
    <p style="color: #808080; text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);">
    ZetaFence Secret Preservation
    </p>
</h1>

<br/>

## Underlying Motivations

Whether user attributes, JSON Web Tokens (JWT), API service tokens, or other senstive key-values, Zetafence takes extra precautions to preserve those secrets without revealing underlying contents. Following is a summary of design of the secret preservation system.

## Problem

Enterprises that need to protect their crown-jewel secrets need to secure their vault in the first place. If a single entity (e.g. admin user) knows the access codes to the vault, the code might be lost or unavailable when the entity is unavailable and vault needs to be opened. If there are several entities (users) who know the code, they may not trust each other to always act honestly. [Shamir's Secret Sharing (SSS)](https://en.wikipedia.org/wiki/Shamir%27s_secret_sharing) can be used in this situation to generate shares of the vault's code which are distributed to authorized individuals in the company. The minimum threshold and number of shares given to each individual can be selected such that the vault is accessible only by (groups of) authorized individuals. If fewer shares than the threshold are presented, the vault cannot be opened.

## Group JWT Semantics

- JWT tokens are typically provided to authenticate an user/application, verify authenticity of the source, and authorize specific roles & permissions against the holder of token
- Zetafence extends those authn/authz semantics, authencity, and integrity by adding threshold `(k, n)` secret-sharing technique
- A single Group JWT token, issued by Zetafence, is enough to authn/authz an user belonging to a group to perform certain action on behalf of the group e.g. admin privilege to certain resources
- Within a single group, `k-out-of-N` JWT tokens are needed to collectively authn/authz a certain token secret just as SSS mandates. And that no `m < k` will be able to obtain the secret token

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
