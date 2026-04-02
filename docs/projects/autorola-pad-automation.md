# Autorola PAD Automation

!!! warning "Phase 1 Working — Phase 2 In Progress — Phase 3 Planned"

---

## Overview

The Autorola PAD Automation is a multi-phase Power Automate Desktop (PAD) flow designed to fully automate interactions with the Autorola auction and fleet management platform. This project addresses one of the most time-consuming manual processes in the COE's daily operations: navigating the Autorola interface to extract appraisal queues, download vehicle photo evidence, and submit pricing decisions.

The working directory for all automation artifacts is located at:

```
D:\Users\qasims\OneDrive - Al-Futtaim Group\Documents\Autorola_ZIP_Inbox
```

---

## Phase Breakdown

| Phase | Scope | Status |
|---|---|---|
| **Phase 1** | Login to Autorola, extract the "Appraisal Pending Pricing" queue, populate `EnquiryListJSON` and `EnquiryIdList` variables | :white_check_mark: Working |
| **Phase 2** | For Each loop: click each Enquiry ID, navigate to Pictures tab, download ZIP (damages + photos), close modal | :orange_circle: In Progress |
| **Phase 3** | Inject pricing decisions back into Autorola | :blue_circle: Planned |

---

## Key Architectural Findings

During the development of this automation, several critical technical discoveries were made that informed the overall design approach.

**Modal Overlay Handling** required careful attention. The Autorola web interface uses modal dialogs extensively, and the PAD flow must correctly detect, interact with, and close these overlays without losing context or triggering JavaScript errors.

**Bulk ZIP Downloads** presented challenges around timing and file system synchronization. The flow must wait for each download to complete before proceeding to the next enquiry, ensuring no files are corrupted or missed.

**JavaScript Injection Blocks** on password fields required workaround strategies. The Autorola login page blocks direct JavaScript injection into password fields, necessitating alternative approaches for automated credential entry.

---

## Phase 1 — Login & Queue Extraction (Working)

Phase 1 successfully automates the login process and extracts the full "Appraisal Pending Pricing" queue from Autorola. The extracted data is stored in two key variables: `EnquiryListJSON` (containing the full queue metadata) and `EnquiryIdList` (a flat list of enquiry identifiers for iteration in Phase 2).

---

## Phase 2 — Per-Enquiry ZIP Download (In Progress)

Phase 2 iterates over each enquiry in the `EnquiryIdList`, opens the enquiry detail modal, navigates to the Pictures tab, triggers a ZIP download of all damage and vehicle photos, and closes the modal before proceeding to the next record. This phase is currently under active development, with the primary challenge being reliable modal interaction and download synchronization.

---

## Phase 3 — Pricing Decision Injection (Planned)

Phase 3 will complete the automation loop by injecting pricing decisions (ACQUIRE, NEGOTIATE, or DECLINE with AED pricing) back into Autorola. This phase depends on the successful completion of Phase 2 and will require careful validation to ensure pricing data is accurately submitted.

---

## Technology

| Component | Detail |
|---|---|
| **Platform** | Power Automate Desktop (PAD) |
| **Target System** | Autorola (Web-based auction/fleet platform) |
| **Data Storage** | OneDrive (ZIP files), JSON variables |
| **Dependencies** | Corporate device with PAD installed, Autorola credentials |
