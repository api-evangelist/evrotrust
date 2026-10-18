---
generated: '2026-10-18'
method: generated
name: evrotrust-one-time-sign-document
description: One-time (offline) signing of a PDF by a person who is not a registered Evrotrust user, activated by
  SMS OTP.
api: openapi/evrotrust-api-openapi.yml
operations:
- post_document-doc-offline
- post_document-doc-offline-activate
- post_document-doc-offline-activate-resend
- readyDocumentOffline
- post_document-status
- post_document-download
- post_document-offline-withdraw
source: Grounded in openapi/evrotrust-api-openapi.yml (Evrotrust API 3.0.0); every operationId verified verbatim
  in the spec.
---

# One-time (offline) signing of a PDF by a person who is not a registered Evrotrust user

## Steps

1. Create the one-time signing request with `post_document-doc-offline`.
2. Activate signing with the SMS code via `post_document-doc-offline-activate`; resend the SMS with `post_document-doc-offline-activate-resend`.
3. Track via the `readyDocumentOffline` callback or `post_document-status`.
4. Download with `post_document-download`, or withdraw with `post_document-offline-withdraw`.

## Operations

- `post_document-doc-offline`: POST /document/doc/offline (OTP eSign PDF (Agent))
- `post_document-doc-offline-activate`: POST /document/doc/offline/activate (Activate Signing)
- `post_document-doc-offline-activate-resend`: POST /document/doc/offline/activate/resend (Resend SMS)
- `readyDocumentOffline`: POST /document/offline/ready (One-time Signing Document Ready)
- `post_document-status`: POST /document/status (Check Status File)
- `post_document-download`: POST /document/download (Download File)
- `post_document-offline-withdraw`: POST /document/offline/withdraw (Withdraw File)

## Rules

- All operations are POST against https://api.sandbox.evrotrust.com/vendor (testing) or https://v.evrotrust.com/vendor (production). Credentials are issued by Evrotrust integration support.
- `ready*` operations are callbacks Evrotrust sends to you, not calls you make.
- The spec documents no idempotency keys: do not blindly retry create calls; check status first.
