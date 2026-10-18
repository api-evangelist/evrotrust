---
generated: '2026-10-18'
method: generated
name: evrotrust-one-time-identification
description: Run an Ident Lite one-time identification and retrieve the verified user data.
api: openapi/evrotrust-api-openapi.yml
operations:
- post_onetimeidentification-validaterefid
- post_onetimeidentification-status
- post_onetimeidentification-getdata
source: Grounded in openapi/evrotrust-api-openapi.yml (Evrotrust API 3.0.0); every operationId verified verbatim
  in the spec.
---

# Run an Ident Lite one-time identification and retrieve the verified user data.

## Steps

1. Validate the reference ID with `post_onetimeidentification-validaterefid`.
2. Poll `post_onetimeidentification-status` until identification completes.
3. Fetch the identified person's data with `post_onetimeidentification-getdata` (`vendorNumber`, `referenceID`, `includes`).

## Operations

- `post_onetimeidentification-validaterefid`: POST /onetimeidentification/validaterefid (Validate refID)
- `post_onetimeidentification-status`: POST /onetimeidentification/status (Check Status)
- `post_onetimeidentification-getdata`: POST /onetimeidentification/getdata (Get User Data)

## Rules

- All operations are POST against https://api.sandbox.evrotrust.com/vendor (testing) or https://v.evrotrust.com/vendor (production). Credentials are issued by Evrotrust integration support.
- `ready*` operations are callbacks Evrotrust sends to you, not calls you make.
- The spec documents no idempotency keys: do not blindly retry create calls; check status first.
