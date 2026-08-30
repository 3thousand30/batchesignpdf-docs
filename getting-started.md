---
layout: default
title: Getting started
nav_order: 2
---

# Getting started

The mode toggle at the top of the app switches between **Superimpose** (stamp
a signature image) and **USB Token** (a real certificate-backed digital
signature). The steps below cover Superimpose first; see
[Sign with a USB token or certificate](#sign-with-a-usb-token-or-certificate)
for the other direction.

## 1. Add PDFs

Add PDF files or choose a folder. The app runs preflight checks and skips
already-signed, encrypted, or malformed files by default.

## 2. Create or choose a signature

Draw a signature with your mouse or pen, type your name in a script font, or
upload an existing signature image. Saved signatures become reusable named
profiles — draw one once, reuse it in future batches.

## 3. Choose placement

Pick a target page (first, last, every page, or a specific page number) and a
position using the 3×3 anchor grid, then fine-tune with the width and offset
controls. The right-hand panel shows a live preview of where the signature
will land.

Fixed-position placement assumes a batch of similarly laid-out documents —
check the preview on your first file before running a large batch of PDFs
with different page sizes or layouts.

## 4. Review and run

Choose an output folder and collision behaviour, then run. Inputs are never
modified — signed copies go to a separate folder, and a `signing-report.csv`
is written alongside them.

## Sign with a USB token or certificate

Switch the mode toggle to **USB Token** to apply a real digital signature
instead of a visual stamp.

1. Add PDFs the same way as above.
2. Choose a certificate from the list — this comes from your Windows
   certificate store, which is also where a USB/DSC token's driver
   registers its certificate once connected.
3. Run the batch. Windows may prompt for your token's PIN once, the first
   time the certificate's private key is used — not once per file.
4. Each signed file carries a `/ByteRange`-based PKCS#7/CMS signature over
   the certificate you chose, distinct from a superimposed image stamp.

USB-token signing is a real cryptographic signature, not a picture of one —
see [Signing modes explained](concepts.md) for what that does and doesn't
guarantee.
