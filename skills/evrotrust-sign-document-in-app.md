---
generated: '2026-10-18'
method: generated
name: evrotrust-sign-document-in-app
description: Send a PDF to a registered Evrotrust user for remote qualified e-signature in the Evrotrust app, track
  it and download the signed file.
api: openapi/evrotrust-api-openapi.yml
operations:
- post_user-check-extended
- post_document-doc-online
- readyDocument
- post_document-status
- post_document-download
- post_document-withdraw
source: Grounded in openapi/evrotrust-api-openapi.yml (Evrotrust API 3.0.0); every operationId verified verbatim
  in the spec.
---

# Send a PDF to a registered Evrotrust user for remote qualified e-signature in the Evrotrust app

## Steps

1. Check the signer is a registered, identified Evrotrust user (`post_user-check-extended`).
2. Upload the document as multipart (`document` + `data`) with `post_document-doc-online`; keep the returned thread/transaction identifiers.
3. Receive the status callback (`readyDocument`: 2 Signed, 3 Rejected, 4 Expired, ...) on your callback URL, or poll `post_document-status`.
4. Download the signed file with `post_document-download`.
5. Cancel a pending request with `post_document-withdraw`.

## Operations

- `post_user-check-extended`: POST /user/check/extended (Check User Status)
- `post_document-doc-online`: POST /document/doc/online (eSign Single File)
- `readyDocument`: POST /document/ready (Document Ready)
- `post_document-status`: POST /document/status (Check Status File)
- `post_document-download`: POST /document/download (Download File)
- `post_document-withdraw`: POST /document/withdraw (Withdraw File)

## Rules

- All operations are POST against https://api.sandbox.evrotrust.com/vendor (testing) or https://v.evrotrust.com/vendor (production). Credentials are issued by Evrotrust integration support.
- `ready*` operations are callbacks Evrotrust sends to you, not calls you make.
- The spec documents no idempotency keys: do not blindly retry create calls; check status first.
