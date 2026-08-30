---
layout: default
title: Troubleshooting
nav_order: 4
---

# Troubleshooting

## A file was skipped

Already-signed, encrypted, and malformed PDFs are skipped by default. The
original file remains unchanged. Turn on "Allow restamping already-signed
PDFs" in Superimpose mode if you specifically want to stamp over an
existing signature.

## The signature lands in the wrong place on some files

Fixed-position placement applies the same page/position to every file in
the batch, which assumes similarly laid-out documents. If your folder mixes
different page sizes, orientations, or layouts, check the position preview
against a representative file from each layout before running, or run
mismatched files as separate batches.

## No certificates appear in USB Token mode

The list comes from your Windows certificate store (`CurrentUser\My`). If
you're using a USB/DSC token, confirm its driver/minidriver is installed and
the token is connected — Windows needs to have registered its certificate
into that store before this app (or any other Windows app) can see it. Only
certificates with an available private key are listed.

## Windows keeps asking for my PIN

The app acquires the certificate's private-key handle once per batch, so a
single PIN entry should cover every file in that run. If you're being
prompted repeatedly, check whether your token's own software is configured
to time out or re-lock the session between operations — that's controlled
by the token's driver, not this app.

## Output name already exists

The app uses collision-safe names by default. If an output filename already
exists, a numbered copy is created instead of overwriting the input or an
existing result.

## Where's the audit trail?

Every batch writes a `signing-report.csv` to the output folder alongside
the signed files, listing each file's mode, status, and message. It's a
convenience log, not a legal attestation.
