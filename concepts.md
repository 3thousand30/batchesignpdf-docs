---
layout: default
title: Signing modes explained
nav_order: 3
---

# Signing modes explained

Batch eSign PDF has two genuinely different signing modes. Knowing which one
you actually need matters — they are not interchangeable.

## Superimpose mode

Superimpose mode places an image — your drawn, typed, or uploaded signature —
onto a PDF page, the same way a rubber stamp does. It is a **visual mark**,
not a cryptographic guarantee. Anyone who can edit a PDF can add, move, or
remove that image just as easily as you can. It's the right tool for
internal sign-offs, informal approvals, or documents where a recognisable
mark is all that's needed.

- No certificate required.
- Works fully offline.
- A saved signature profile can be reused across many batches.
- Placement (page + position) is fixed once and applied identically to every
  file in the batch, which is why it works best on a folder of similarly
  laid-out documents.

## USB Token mode

USB Token mode applies a real digital signature using a certificate from
your Windows certificate store — the same store a physical USB/DSC token's
driver registers its certificate into once connected. This produces a
`/ByteRange`-based PKCS#7/CMS signature cryptographically tied to that
certificate's private key, which never leaves the token or the store.

- Requires a certificate with an available private key.
- The OS/CNG provider handles the PIN prompt directly — this app never sees
  or stores it.
- One PIN entry covers the whole batch, not each file individually.
- Produces a signature a compliant PDF viewer can validate against the
  certificate and its issuing chain.

A digital signature is only as trustworthy as the certificate behind it.
Batch eSign PDF doesn't vouch for who a certificate belongs to or whether
it's suitable for a particular legal purpose — that's between you, your
certificate authority, and whoever's relying on the signed document.

## Which one do I need?

If you're not sure, ask: **does this signature need to hold up
cryptographically to someone who doesn't trust me by default** (a
regulator, a counterparty, a court)? If yes, use USB Token mode with an
appropriate certificate. If you just need your name or mark visibly on a
batch of internal documents, Superimpose mode is faster and needs no
certificate at all.

## Verification

Every signed output is reopened after signing to confirm the page count is
unchanged before it's promoted from a temporary file to the final output.
Files that fail that check are reported, not silently promoted as
successful.
