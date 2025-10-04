# USB Baiting Analysis — Parking Lot USB Exercise

## Purpose
This repository contains a short analysis of a found USB drive (parking lot scenario) used to demonstrate USB baiting risks, attacker techniques, and practical mitigations for workplace environments.

## Contents
- `parking-lot-usb-exercise.md` — Answers to the activity: Contents, Attacker Mindset, and Risk Analysis.
- This README — project purpose and quick usage notes.

## Key Findings (summary)
- The USB drive contains both personal (photos) and work-related files (new hire letter, employee schedules) that likely include PII.
- An attacker could use the files to craft targeted phishing or social-engineering attacks or plant malware (including BadUSB).
- Main mitigations: employee awareness, disable AutoPlay, endpoint protection, sandboxed analysis workstation, and enforced USB policies.

## How to use
1. Review `parking-lot-usb-exercise.md` for the exercise answers.
2. Use this repository as example content for training, reports, or portfolio display.
3. Do **not** plug unknown USB devices into production systems — use an isolated VM or write-blocker for safe analysis.

## Recommendations
- Add a link to your organization’s USB/device policy or training materials.
- Include screenshots or image evidence (sanitized) if used in reports.
- Keep this example updated with new mitigations and lessons learned.

---

## License
This repository content is educational. Feel free to reuse or adapt for training and portfolio purposes.
