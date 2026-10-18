---
name: evrotrust-sign-document-via-hash
description: Sign a document or group of documents using the hash method for electronic signatures.
api: openapi/evrotrust-api-openapi.yml
operations:
- post_document-hash-online
- post_document-group-hash-online
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/evrotrust-api-openapi.yml ; every operationId checked against the contract
---

# evrotrust-sign-document-via-hash

Sign a document or group of documents using the hash method for electronic signatures.

## Steps

1. 1. To sign an individual document, call `post_document-hash-online` with the required document hash and signing parameters
2. 2. To sign multiple documents as a group, call `post_document-group-hash-online` with the group hash and signing parameters for batch processing
3. 3. Handle the response to confirm successful signing and retrieve any signature identifiers or verification details

## Rules

- Authentication header required as specified in the API contract
- Idempotency handling for retry scenarios as per API documentation
- Error responses follow the provider's standard error format
