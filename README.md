# FixIt AI

### Product support grounded in the manual—not guesswork.

FixIt AI is a portfolio project that helps product owners find clear troubleshooting and maintenance guidance from a selected product's manual, with page-level citations and an explicit safety boundary.

**Status:** Working local demonstration; Azure deployment preparation is in progress. A public live demo is not available yet. This public repository is a project showcase only—the application source code remains private.

## Implemented step illustrations

These are the actual artwork assets used in the local application—not the earlier design mockup. Matching guidance steps display their model-specific illustration. The manual-source panel also shows the matching artwork, labeled **Demo illustration**, alongside the relevant cited excerpts and a link to the full PDF page.

| C100 · Bean lid | C200 · Water tank | W240 · Door closure |
| :---: | :---: | :---: |
| <img src="assets/c100-lid.png" width="220" alt="C100 bean lid resting flat"> | <img src="assets/c200-tank.png" width="220" alt="C200 water tank and seating recess"> | <img src="assets/w240-door.png" width="220" alt="W240 gentle washer door closure"> |
| Illustration beside the lid-closing step | Illustration beside the tank-refitting step | Illustration beside the door-check step |

| W360 · Laundry load | D60 · Mesh filter | D80 · Upper rack |
| :---: | :---: | :---: |
| <img src="assets/w360-laundry.png" width="220" alt="W360 loose laundry inside an unlocked washer"> | <img src="assets/d60-filter.png" width="220" alt="D60 mesh filter seated flat"> | <img src="assets/d80-rack.png" width="220" alt="D80 upper rack moving inward"> |
| Illustration beside the redistribution step | Illustration beside the filter-refitting step | Illustration beside the rack-positioning step |

Other supported steps use contextual icons, such as pause, waiting, and contacting support. This gallery shows application assets, not full interface screenshots or PDF scans. Illustrations supplement the cited text; they are not independent manual evidence. All examples are fictional and are not instructions for real appliances.

<details>
<summary>Earlier approved layout mockup (design reference only)</summary>

![Earlier FixIt AI support-interface design mockup](assets/support-design.png)

This earlier mockup predates the implemented illustrated steps and focused source excerpts. It is not the current application screenshot or a deployed service.

</details>

## The problem

The same error code can mean different things on different products. Generic answers can be irrelevant or unsafe. FixIt AI keeps guidance tied to the selected model and its published manual, and declines to invent an answer when the evidence is missing.

## What the local demo demonstrates

- Six fictional product models across coffee machines, washing machines, and dishwashers, with original demonstration manuals.
- Model-specific guidance, page-level citations, and manual-source previews.
- Unsupported-question handling and escalation for requests beyond the safety boundary.
- A Manufacturer workspace for manual upload, processing, review, publication, and feedback review.
- Versioned manuals: processing a replacement does not automatically publish it.
- Repeatable offline evaluations and automated API, web, browser, and security checks.

The repeatable local demo uses a deterministic answer path. Azure-backed model and retrieval integrations are implemented separately; this showcase does not claim that the public Azure deployment or cloud indexing of all six manuals is complete.

## Architecture

| Layer | Technology and responsibility |
| --- | --- |
| Web application | Next.js, React, and TypeScript: product selection, guidance, citations, and administration |
| API | Python and FastAPI: application workflows, evidence access, and safety handling |
| Ingestion | Explicitly enabled, bounded one-shot processing; successful manuals remain ready for human review |
| Azure integration target | Azure-hosted OpenAI through Microsoft Foundry, Azure AI Search, Blob Storage, and Azure SQL |
| Hosting and identity target | Azure Container Apps, managed identities, and Microsoft Entra ID |

Cloud hosting and identity configuration still require deployment and end-to-end verification. They are not represented here as a running production service.

## Engineering priorities

- **Evidence:** Answers stay associated with the selected model and cited manual content.
- **Safety:** Hazardous requests escalate instead of receiving repair procedures.
- **Publication control:** Ingestion, review, and publication are separate operations.
- **Cost control:** Bounded processing and provider usage limits support a low-usage demo; limits are not a guarantee of zero cloud costs.
- **Verification:** CI includes tests, dependency auditing, secret scanning, and security checks. Changes pass review before merging.

## Try it

The recruiter-facing live demo link will be added here after deployment and verification. There is currently nothing to install from this showcase repository.

## About this showcase

Created by [Krishna Mvwala](https://github.com/krishnamvwala).

This repository contains only this overview and selected visual assets. It does not contain application source code, credentials, internal project tracking, or the private repository's history.

All demonstrated products and manuals are fictional portfolio materials—not instructions for operating or repairing real appliances.
