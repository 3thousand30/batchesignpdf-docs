---
layout: default
title: Privacy Policy
nav_order: 5
---

# Privacy Policy

**Last updated: August 2026**

Batch eSign PDF is developed by [3thousand30](https://3thousand30.com).

---

## What we collect

3thousand30 does not collect, store, or receive your source PDFs, signed
output PDFs, filenames, folders, signature images, certificate details, PINs,
or batch results through this app.

- No analytics sent to us
- No telemetry sent to us
- No crash reporting sent to us
- No account or registration required
- No advertising SDKs

---

## What happens on your device

Batch eSign PDF processes selected PDF files locally on your Windows device.
Signature image capture, placement, PDF stamping, certificate signing
operations, output validation, progress reporting, and cleanup all happen on
the PC running the app.

Your PDF contents are not uploaded to 3thousand30 servers. Superimposed
signing needs no certificate or network access at all. USB-token signing
talks only to your own Windows certificate store and CNG provider — never to
a 3thousand30 server or any third-party signing service.

---

## Signature images

Signature profiles (drawn, typed, or uploaded images) are stored locally
under your Windows user profile's application data folder. They are
ordinary local image files, not secrets, and are never uploaded.

---

## Certificates and PINs

Certificate selection, private-key access, and PIN entry are handled
entirely by Windows and your certificate/token's own driver. Batch eSign PDF
never sees, stores, or logs your PIN. It does not persist which certificate
you used beyond the current session's settings.

---

## Source and output files

The app reads only the PDF files or folders you select. It writes signed
copies to the output folder you choose and never overwrites an input file
directly — it writes a temporary candidate, validates it, and only then
promotes it using the app's collision rules.

---

## Signed, encrypted, and malformed PDFs

Already-signed, encrypted, and malformed PDFs are skipped by default when
processing them would be unsafe, ambiguous, or would invalidate an existing
signature. Skipped files remain in their original location and are not
modified.

---

## Microsoft Store, Windows, and external links

Windows and the Microsoft Store may independently collect installation,
purchase, licensing, reliability, or crash information under Microsoft's
own terms.

Documentation, support, Microsoft Store, and website links open in your
browser. Those destinations are governed by their own privacy policies and
browser settings.

---

## Contact

Questions? Email [support@3thousand30.com](mailto:support@3thousand30.com).
