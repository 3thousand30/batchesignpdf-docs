---
layout: home
title: Batch eSign PDF
nav_order: 1
---

# Batch eSign PDF

Sign a batch of local PDFs two ways: superimpose a signature image (drawn,
typed, or uploaded) at the same spot on every file, or apply a real digital
signature using a certificate from a USB/DSC token or your Windows
certificate store. Your files stay on the device.

[Get started](getting-started.md){: .btn .btn-primary }
[Signing modes explained](concepts.md){: .btn }

## What it does

- Draws, types, or uploads a signature image and saves it as a reusable, named profile.
- Places it on the same page and position across a folder of similarly laid-out PDFs, with a live position preview before you run the batch.
- Signs with a certificate from your Windows certificate store — the same place a USB/DSC token registers itself — producing a real PKCS#7/CMS digital signature, not just a visual mark.
- Prompts for your token PIN at most once per batch, not once per file.
- Writes a `signing-report.csv` audit trail alongside your signed files.
- Never modifies your originals — always writes to a separate output folder.
- Skips already-signed, encrypted, or malformed PDFs by default rather than risking source files.

## Local by design

Batch eSign PDF reads the files you select, signs locally, and never uploads document contents. Superimposed signing needs no certificate at all; USB-token signing talks only to your own Windows certificate store, never a network service.
