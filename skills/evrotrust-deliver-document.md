---
name: evrotrust-deliver-document
description: Send a document for e-Delivery, check its status, and download the receipt.
api: openapi/evrotrust-api-openapi.yml
operations:
- post_delivery-online
- post_delivery-receipts-status
- post_delivery-receipts-download
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/evrotrust-api-openapi.yml ; every operationId checked against the contract
---

# evrotrust-deliver-document

Send a document for e-Delivery, check its status, and download the receipt.

## Steps

1. 1. Send a document for delivery using `post_delivery-online` with the required file and recipient information
2. 2. Check the delivery status using `post_delivery-receipts-status` with the transaction ID
3. 3. Download the delivery receipt using `post_delivery-receipts-download` once the delivery is complete

## Rules

- Use the appropriate authentication headers as required by the API
- Check the delivery status before attempting to download receipts
- Handle pagination if multiple receipts need to be downloaded
