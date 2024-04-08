## Definitions

[[def: DID Log]]

~ A log of JSON arrays each of which provides the information necessary to
generate and validate a version of the DIDDoc from the previous version.

[[def: self-certifying identifier, SCID]]

~ An object identifier derived from initial data such that an attacker could not
create a new object with the same identifier. The input for a `did:tdw` SCID is
the initial DIDDoc with the placeholder `{SCID}` wherever the SCID is to be
placed.

[[def: parameters]]

~ `did:tdw` parameters are a defined set of configurations that control how the
issuer has generated the DID, and how the resolver should process the DID Log
entries. The use of parameters allows for the controlled evolution of `did:tdw`
log handling, such as evolving the permitted hash algorithms.

[[def: ISO8601, ISO8601 String]]

~ A date/time expressed using the [ISO8601
Standard](https://en.wikipedia.org/wiki/ISO_8601).

[[def: DID Controller]]

~ Per the [[spec:DID-CORE]], a DID controller is an entity that is authorized to
make changes to a DID document.

[[def: Entry Hash]]

~ A `did:tdw` entry hash is a hash generated using a formally defined process over
the data of a log entry. The generated entry hash is subsequently put into the
log entry and *MUST* be verified by a resolver.

[[def: Data Integrity]]

~ [W3C Data
Integrity](https://www.w3.org/community/reports/credentials/CG-FINAL-data-integrity-20220722/)
is a specification of mechanisms for ensuring the authenticity and integrity of
structured digital documents using cryptography, such as digital signatures and
other digital mathematical proofs.

[[def: JSON Patch]]

~ [[spec:rfc6902]] is a web
standard format for describing how to change a JSON document from one state to
another. It is used in `did:tdw` to define how a DIDDoc is changed from one
version to the next.

[[def: Key Pre-Rotation]]

~ A technique for a controller of a cryptographic key to commit to the next public
key that it will use for a purpose, without exposing the public key. It protects
from an attacker that gains knowledger of the current private key from being
able to rotate to a new key the controller does not know.

[[def: DID Log Entry, DID Log Entries]]

~ A DID Log Entry is a JSON array of items that define the authorized
transformation of a DIDDoc from one version to the next. The initial entry
establishes the DID and version 1 of the DIDDoc.

[[def: base32_lower]]

~ Applies [[spec:rfc4648]] to convert
data to a `base32` encoding, and then lower cases the result. Data encoded as
base32 consists of a string of characters containing only the letters A-Z and
digits 2-7.

[[def: JSON Canonicalization Scheme]]

~ The [[spec:rfc8785]] canonicalizes a JSON
structure such that is suitable for verifiable hashing or signing.

[[def: DID Core Specification, DID]]

~ Decentralized Identifiers (DIDs) ([[spec:did-core]]) are a type of identifier that enable
verifiable, decentralized digital identities. A DID refers to any subject (e.g.,
a person, organization, thing, data model, abstract entity, etc.) as determined
by the controller of the DID..

[[def: DID Method, DID Methods]]

~ DID methods are the mechanism by which a particular type of DID and its
associated DID document are created, resolved, updated, and deactivated. DID
methods are defined using separate DID method specifications. This document is
the DID Method Specification for `did:tdw`.

[[def: verifiableConditions]]

~ The (proposed) [verifiableConditions
Specification](https://github.com/w3c-ccg/verifiable-conditions) defines a way
to express complex conditions and additional metadata about verification
methods. It can be used to combine verification methods to form conjugated
conditions such as logical operations (like &&), thresholds, weighted
thresholds, relationships, or delegation to external verification methods.

[[def: multi-sig, multisig]]

~ A cryptographic signature that to be valid **MUST** contain a defined threshold
(for example, 4 of 7) individual signatures to be considered valid. The
multi-signature key reference points to a verification method that defines what
keys may contribute to the signature, and under what conditions the
multi-signature is considered valid.

[[spec]]