# MoXi Chatbot – Contradictions Log

- **Created:** 2025-11-08
- **Last Updated:** 2025-11-08 12:25 PM
- **Purpose:** Track contradictions between system/personality instructions and knowledge base content that can confuse the chatbot or suppress valid information.

---

## How to Use This File

- Every time you discover a contradiction, append a new entry under the appropriate section.
- Always include:
  - A short title for the issue
  - The files involved
  - The relevant quotes from each file
  - A one–two sentence explanation of why this is a contradiction
- Keep this updated as we work through the KB.

---

## Contradictions

### Example – Employee Contact Info Suppressed by Personality Guide

- **Personality Guide File:** `moxi_bot_personality_guide_updated.md`
- **KB File:** `Why Real Estate Professionals Should Partner with MoXi 10162025.docx`
- **Personality Guide Rule (quote):** e.g., "The bot should never share information about any employee."
- **KB Content (quote):** Contains employee names, phone numbers, and calendar invite links intended for partners.
- **Why This Is a Contradiction:**
  The knowledge base clearly intends for the chatbot to share these BD contact details, but the personality guide forbids sharing any employee information. As a result, the model suppresses the contacts and users believe the chatbot is "broken."

---

### Finding 1 – Partnership Team Contact Information Blocked by Personality Guide

- **Personality Guide File:** `moxi_bot_personality_guide_updated.md`
- **KB File:** `Why Real Estate Professionals Should Partner with MoXi 10162025.docx`

- **Personality Guide Rule (quotes):**
  - Line 31: "NEVER share individual team member names, emails, or phone numbers"
  - Line 32: "NEVER provide Calendly or scheduling links for specific people"
  - Line 34: "ALWAYS direct inquiries to the corporate-level contact options above"
  - Lines 148-149: "NEVER share individual team member contact information"
  - Lines 259-260: "NEVER share individual team member contact information"

- **KB Content (exact quotes from partnership document):**
  ```
  Who are the Partnership team members, and how do we get connected with them?
  Maria Ocampo - Business Development Manager
  WhatsApp: +52 56 3396 9629
  Contact Me: https://www.globalmortgage.mx/mariaocampo

  Mike Petersen – Business Development Officer
  WhatsApp: +52 55 9448 5294
  Schedule a call: https://outlook.office.com/book/MOXI@moxiglobal.onmicrosoft.com/s/vBlLpZrs2E20JuSb57-obA2

  Victoria Avila – Business Development Officer
  WhatsApp: +52 333 167 4557
  Schedule a call: https://outlook.office.com/book/MOXI@moxiglobal.onmicrosoft.com/s/QcEWoylorU220kM4ml1i0g2?ismsaljsauthenabled=true
  ```

- **Why This Is a Contradiction:**
  The partnership document explicitly provides three Business Development team members with their names, WhatsApp numbers, personal contact pages, and Outlook scheduling links. The personality guide strictly forbids sharing any individual team member names, phone numbers, or scheduling links. When real estate professionals or partners ask the chatbot "How do I connect with the partnership team?", the bot will suppress this information per the personality guide rules, causing users to believe the chatbot is broken or unhelpful. **Decision needed:** Either update the personality guide to allow sharing BD team contact info for partnership inquiries, OR remove individual contacts from the KB and rely solely on referralpartners@moxi.global.

---

### Finding 2 – Outdated Property Value Minimum ($350K vs $300K)

- **Personality Guide File:** `moxi_bot_personality_guide_updated.md`
- **KB File:** `Partnership Programs Overview 10162025.docx`

- **Personality Guide Rule (quote):**
  - Line 291: "Changed property minimum from $350K to $300K"
  - Line 179-182: "If $300K or higher, continue. If between $200K-$300K and strong profile, mention may still qualify with advisor review"
  - Line 198: "Must be $300,000 or higher for core program"

- **KB Content (exact quotes from partnership document):**
  ```
  Your clients are buying or refinancing homes in Mexico valued above $350K USD

  Minimum property value of $350k USD

  Sell homes with prices above $350k USD
  ```

- **Why This Is a Contradiction:**
  The partnership document states multiple times that the minimum property value is $350K, but the personality guide was explicitly updated to lower this threshold to $300K. If the chatbot uses the partnership document, it will incorrectly tell partners and clients that properties valued between $300K-$350K don't qualify, potentially losing qualified business. **Decision needed:** Update all KB documents to reflect the new $300K minimum property value.

---

### Finding 3 – Outdated Eligibility (U.S. Citizens Only vs U.S. Taxpayers)

- **Personality Guide File:** `moxi_bot_personality_guide_updated.md`
- **KB File:** `Partnership Programs Overview 10162025.docx`

- **Personality Guide Rule (quote):**
  - Line 292: "Added permanent residents as eligible (U.S. taxpayers)"
  - Line 173: "Are you a U.S. taxpayer (U.S. citizen or permanent resident)"
  - Line 5: "designed to support U.S. taxpayers (citizens and permanent residents)"

- **KB Content (exact quotes from partnership document):**
  ```
  At this time, MoXi® lends only to US Citizens
  (appears 4 times throughout document)

  Your clients are US Citizens. At this time, MoXi® lends only to US Citizens

  They're US Citizens
  ```

- **Why This Is a Contradiction:**
  The partnership document repeatedly states that MoXi only lends to U.S. citizens, but the personality guide was updated to expand eligibility to all U.S. taxpayers, which includes both citizens AND permanent residents. This means the chatbot could incorrectly tell permanent residents they don't qualify, excluding an entire category of eligible borrowers. **Decision needed:** Update all KB documents to say "U.S. taxpayers (citizens and permanent residents)" instead of "U.S. Citizens only."

---

### Finding 4 – FAQ Document Excludes Permanent Residents

- **Personality Guide File:** `moxi_bot_personality_guide_updated.md`
- **KB File:** `MoXi Frequently Asked Questions.docx`

- **Personality Guide Rule (quote):**
  - Line 292: "Added permanent residents as eligible (U.S. taxpayers)"
  - Line 173: "Are you a U.S. taxpayer (U.S. citizen or permanent resident)"
  - Line 5: "designed to support U.S. taxpayers (citizens and permanent residents)"

- **KB Content (exact quotes from FAQ document):**
  ```
  Can I finance property in Mexico?
  Global Mortgage (MoXi) offers U.S. citizens sound and secure cross-border mortgage financing...

  Can U.S citizens buy in Mexico?
  (Discusses US Citizens only, no mention of permanent residents)

  Making mortgages in Mexico available to U.S. Citizens since 2017
  ```

- **Why This Is a Contradiction:**
  The FAQ document refers only to "U.S. citizens" throughout, with no mention that permanent residents (Green Card holders) are also eligible. This contradicts the personality guide which explicitly states that both U.S. citizens AND permanent residents are eligible. If the chatbot uses this FAQ, it will incorrectly tell permanent residents they don't qualify, excluding eligible borrowers. **Decision needed:** Update the FAQ document to say "U.S. taxpayers (U.S. citizens and permanent residents)" instead of "U.S. citizens" throughout.

---

### Finding 5 – Multiple FAQ Documents with Conflicting Information

- **Files Involved:**
  - `MoXi Frequently Asked Questions.docx` (OUTDATED)
  - `MoXi® - Frequently Asked Questions - Expanded - Please use this one.docx` (UPDATED)

- **The Problem:**
  There are TWO FAQ documents in the knowledge base with the same general purpose but different content:

  **Old FAQ Document** contains outdated information:
  - References "U.S. citizens" only (excludes permanent residents)
  - No clear $300K property minimum stated

  **Expanded FAQ Document** (marked "Please use this one") contains updated information:
  - References "U.S. citizens and permanent residents" correctly
  - States $300K property minimum clearly
  - Better alignment with personality guide

- **Why This Is a Contradiction:**
  If both documents are included in the chatbot's knowledge base, the AI may randomly pull from either document, resulting in inconsistent answers depending on which source it retrieves. A user asking the same question twice might get different answers. The filename "Please use this one" suggests the team knows one is outdated, but both remain in the KB folder. **Decision needed:** Remove the old "MoXi Frequently Asked Questions.docx" file from the knowledge base entirely and use only the Expanded version. Alternatively, clearly mark deprecated documents in a separate "Archive" or "Deprecated" folder so they're not ingested by the chatbot.

---

*(Additional contradictions will be added below as they are discovered)*
