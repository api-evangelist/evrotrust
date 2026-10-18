---
generated: '2026-10-18'
method: generated
name: evrotrust-registered-delivery
description: Send a file by qualified electronic registered delivery and collect delivery receipts.
api: openapi/evrotrust-api-openapi.yml
operations:
- post_delivery-online
- post_delivery-receipts-status
- post_delivery-receipts-download
source: Grounded in openapi/evrotrust-api-openapi.yml (Evrotrust API 3.0.0); every operationId verified verbatim
  in the spec.
---

# Send a file by qualified electronic registered delivery and collect delivery receipts.

## Steps

1. Send the file with `post_delivery-online` (`document` + `data`).
2. Check delivery state with `post_delivery-receipts-status`.
3. Download the delivery receipts with `post_delivery-receipts-download`.

## Operations

- `post_delivery-online`: POST /delivery/online (Send File for Delivery)
- `post_delivery-receipts-status`: POST /delivery/receipts/status (Check Delivery Status)
- `post_delivery-receipts-download`: POST /delivery/receipts/download (Download Receipts)

## Rules

- All operations are POST against https://api.sandbox.evrotrust.com/vendor (testing) or https://v.evrotrust.com/vendor (production). Credentials are issued by Evrotrust integration support.
- `ready*` operations are callbacks Evrotrust sends to you, not calls you make.
- The spec documents no idempotency keys: do not blindly retry create calls; check status first.
