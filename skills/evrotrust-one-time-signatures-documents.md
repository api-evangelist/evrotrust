---
name: evrotrust-one-time-signatures-documents
description: Create and manage one-time signature documents with OTP verification for PDF files
api: openapi/evrotrust-api-openapi.yml
operations:
- post_document-doc-offline-file
- post_document-doc-offline
- post_document-doc-offline-activate
- post_document-doc-offline-activate-resend
- post_document-offline-withdraw
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/evrotrust-api-openapi.yml ; every operationId checked against the contract
---

# evrotrust-one-time-signatures-documents

Create and manage one-time signature documents with OTP verification for PDF files

## Steps

1. 1. Upload a PDF file for one-time signature using `post_document-doc-offline-file` with the file in the request body
2. 2. Initiate OTP eSign process for the uploaded document using `post_document-doc-offline` with document details and signer information
3. 3. Activate the signing process using `post_document-doc-offline-activate` with the activation code received via SMS
4. 4. If needed, resend the SMS activation code using `post_document-doc-offline-activate-resend` with the document identifier
5. 5. Withdraw a document if necessary using `post_document-offline-withdraw` with the document withdrawal details

## Rules

- Authentication header is required for all API calls
- Operations are idempotent where specified in the endpoint documentation
- Error responses follow standard HTTP status codes with specific error messages
- File uploads have specific size and format requirements as documented
