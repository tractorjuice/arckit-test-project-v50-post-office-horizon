# Post Office Horizon IT System — Background Research Report

| Field | Value |
|---|---|
| Document type | External reference document |
| Date | 2026-05-21 |
| Purpose | Background research for the Horizon replacement architecture project |
| Status | Reference material |
| Prepared for | Enterprise architecture project replacing the Post Office Horizon IT system |

---

## Executive Summary

The **Horizon IT system** is the branch accounting and electronic point-of-sale (EPOS) platform used across the UK Post Office branch network — historically around 11,500–14,000 branches. It was built by **ICL** (acquired by Japan's **Fujitsu** in 1998) and rolled out from **1999–2000**. Defects in Horizon produced apparent cash shortfalls in sub-postmasters' branch accounts. Rather than treating these as system faults, the Post Office held sub-postmasters personally liable and **prosecuted more than 900 of them** between 1999 and 2015 for theft, fraud and false accounting — securing roughly **700+ convictions** (of approximately 736 Horizon-related convictions identified) — while pursuing thousands more for shortfalls through civil demands. It is widely described as one of the most extensive miscarriages of justice in British legal history.

The truth emerged through journalism (notably **Computer Weekly**, which broke the story in 2009), campaigning by sub-postmaster **Alan Bates**, and ultimately the **Bates & Others v Post Office Ltd** group litigation. In December 2019 **Mr Justice Fraser** found Horizon was not "remote-access proof" and that **bugs, errors and defects** rendered it unreliable; the Post Office settled for **£57.75m**. The **Court of Appeal quashed 39 convictions** in *Hamilton & Others v Post Office* (April 2021), finding the prosecutions an abuse of process. The **Post Office (Horizon System) Offences Act 2024** then quashed the great majority of remaining convictions by statute — an unprecedented legislative exoneration.

A **statutory public inquiry** chaired by **Sir Wyn Williams** has heard 226 days of evidence. **Volume 1 of its final report** (published **8 July 2025**) addressed the human impact and redress; it found at least **13 people may have taken their own lives** in connection with the scandal and that more than **10,000 people** were affected. Subsequent volumes covering systemic and individual accountability are expected in/after 2026.

As of **30 April 2026**, approximately **£1.56 billion** had been paid in redress to over **12,300 claimants** across four schemes; the government has estimated total redress at around **£2 billion**.

For the replacement programme: the Post Office's in-house **New Branch IT (NBIT)** programme was judged by chairman Nigel Railton to have been "set up to fail" and was abandoned after a reported **~£1bn** taxpayer cost; it was succeeded by a **Future Technology Portfolio (FTP)** strategy. The Post Office is procuring replacement capability through a competitive tender, and **on 21 May 2026 it named Accenture and One View Commerce (OVC)** as the suppliers selected to take over operating Horizon and to help build its replacement. **Caveat — see Section 6:** as of this report's date the public reporting of the Accenture/OVC selection is wire-service coverage published the same day; contract values, exact scope split, signature dates and the precise Fujitsu exit date were **not confirmed** in the sources reviewed and should be verified directly.

---

## 1. The Horizon IT System

### 1.1 What it is

Horizon is an integrated **branch accounting and retail/EPOS system**. It enables sub-postmasters and counter staff to record sales and transactions on touchscreen terminals, with branch accounts (cash, stock and ledgers) reconciled in the background. It handles the full range of Post Office services — mails and parcels, banking and cash withdrawals, bill payments, foreign currency, lottery, vehicle excise duty and, historically, benefits and pension payments. At its peak it spanned roughly **11,500 to 14,000 branches** and, at launch, was described as the largest non-military IT project in Europe.

### 1.2 Origins — the Benefits Agency / Pathway project

Horizon's roots lie in a mid-1990s **Private Finance Initiative (PFI)** procurement. In **May 1996**, following a competition begun in 1994, a contract was awarded to **ICL Pathway** — a division of ICL created for the purpose — to deliver a system jointly for the **Post Office** and the **Benefits Agency**, originally centred on a magnetic swipe-card ("benefit payment card") for paying pensions and benefits over Post Office counters. **Fujitsu** owned roughly 80% of ICL at the time and acquired ICL outright in 1998.

The **Pathway** project ran badly over budget and behind schedule. In **May 1999** the government cancelled the benefits-card element — a failure the Commons Public Accounts Committee called one of the biggest public-sector IT failures, with reported losses of the order of **£700m**. However, against the advice of its own IT specialists, the Post Office elected to proceed with the remaining element: using the system to convert its paper-based branch accounting to an electronic system. Evidence later heard by the inquiry indicated Fujitsu lobbied hard for the deal to survive. The retained contract for branch automation was the genesis of Horizon.

### 1.3 Rollout

Horizon was rolled out to Post Office branches from approximately **1999 into 2000**. Almost immediately, sub-postmasters began reporting unexplained accounting **shortfalls** they could not reconcile.

### 1.4 The major versions

- **Legacy Horizon (c.1999/2000–2010).** Built on the **Riposte** message-store product from **Escher Group**. It supported **offline operation**, with branch transaction data held **locally on a branch server** and then replicated overnight to clustered central servers. The original infrastructure comprised tens of thousands of **Windows NT4** workstations connected over **ISDN** lines to BT exchanges, with central **Windows NT** server clusters replicating messages between two data centres. Fujitsu wrote the business applications, including **EPOSS**, the EPOS/accounting application.
- **Horizon Online / HNG-X (from 2010).** A complete rewrite by Fujitsu, delivered over several years to 2010, moving to a **fully online architecture** with branch data held **centrally** in a single **Branch Database (BRDB)** rather than on local branch servers.
- **HNG-A / "Horizon Anywhere" (from c.2017).** A further iteration on the same online architecture, still in use into 2025.

### 1.5 Architecture and the role of remote access

Horizon's architecture is central to the scandal. For years the Post Office told sub-postmasters, courts and the public that branch account data could **only** be altered by the sub-postmaster and that no one — not the Post Office, not Fujitsu — could change branch figures remotely. This was untrue.

Justice Fraser found in the **Horizon Issues** judgment (December 2019) that **Fujitsu, and to a lesser extent the Post Office, had remote access** to branch records and could "**insert, inject, edit or delete transaction data or data in branch accounts**." Whistleblower **Richard Roll**, a former Fujitsu employee, testified that remote access to branch accounts was a routine practice. The ability for a third party to alter a branch's accounts — potentially without an audit trail visible to, or comprehensible by, the sub-postmaster — undermined the central premise on which sub-postmasters were held liable and prosecuted.

---

## 2. The Scandal — Bugs, Errors and Defects, and Wrongful Prosecutions

### 2.1 Bugs, errors and defects ("BEDs")

The Horizon Issues trial established that Horizon contained numerous **bugs, errors and defects** capable of causing discrepancies in branch accounts. Among the specifically documented examples:

- **Callendar Square / Falkirk bug.** A defect in the underlying database caused **duplicate transaction entries** in the branch ledger. Despite the entries being obvious duplicates, the affected sub-postmaster was held responsible for the resulting discrepancy.
- **Dalmellington bug.** When the system froze mid-transaction, repeatedly pressing "enter" caused the system to **repeat the transaction** in the ledger. In one case an attempt to record an £8,000 cash transfer generated a **£24,000** apparent shortfall, for which the sub-postmistress was held liable.
- **Receipts and Payments Mismatch (RPM) bug.** After Horizon Online went live in 2010, a discrepancy issue affected roughly **40 branches**, with the system mis-recording certain receipts and payments.

Justice Fraser concluded that Horizon was **not "remote-access proof"** and that BEDs gave rise to a **material risk** that an apparent shortfall was caused by the system rather than the sub-postmaster. Evidence to the inquiry indicated Fujitsu was aware of bugs from as early as **1999**, and that this knowledge was not properly disclosed to sub-postmasters or to the courts.

### 2.2 Scale of prosecutions and convictions

- Between **1999 and 2015**, **more than 900 sub-postmasters, managers and counter assistants were prosecuted** for theft, fraud and false accounting.
- The **Post Office itself prosecuted approximately 700 people** (it held private prosecution powers); others were prosecuted by the Crown Prosecution Service or, in Scotland, the Crown Office (COPFS).
- Approximately **736 Horizon-related convictions** have been identified; **around 236 people were imprisoned**.
- Far larger numbers were never prosecuted but were pursued by the Post Office to **make good apparent shortfalls** from their own funds, often under threat of prosecution. By February 2024 **more than 4,000 sub-postmasters** had been identified as potentially eligible for redress, and Volume 1 of the inquiry report estimated **over 10,000 people** were affected to varying degrees.

### 2.3 The human cost

The inquiry and litigation documented severe and lasting harm: bankruptcies and loss of homes and businesses; criminal records and imprisonment; destroyed reputations in close-knit communities; family breakdown; serious physical and mental illness, including alcohol dependency; and deaths. **Volume 1 of the inquiry report (July 2025)** found that **at least 13 people may have taken their own lives** as a result of the scandal, that **59 people had contemplated suicide**, and that many affected people **died before receiving any redress**. The Post Office's most senior executives were accused, in evidence to the inquiry, of having known of Horizon errors and not disclosed them.

---

## 3. Litigation — Bates & Others v Post Office Ltd

### 3.1 The Group Litigation Order

After the Post Office shut down a mediation scheme in 2015 and forensic accountants **Second Sight** (engaged 2012) were stood down despite having raised serious concerns about Horizon, sub-postmasters led by **Alan Bates** brought a **group action**. The High Court approved a **Group Litigation Order (GLO)** in 2017; ultimately **555 claimants** joined. The case was heard by **Mr Justice Fraser** between 2017 and 2019, producing six judgments — two substantive, the remainder procedural.

### 3.2 The 2019 judgments

- **Common Issues judgment (March 2019).** Addressed the contractual relationship between the Post Office and sub-postmasters; Fraser was sharply critical of the Post Office's conduct and contract terms. The Post Office's attempt to have him recused was refused, and the Court of Appeal declined permission to appeal.
- **Horizon Issues judgment (16 December 2019).** A **313-page** judgment, following 21 days of hearings, on the operation and reliability of Horizon itself. Fraser found Horizon was **not remote-access proof**, that it contained **bugs, errors and defects**, and that these created a real risk of discrepancies in branch accounts — directly contradicting the Post Office's long-standing position.

### 3.3 The settlement

In **December 2019**, before the remaining scheduled trials, the parties settled for **£57.75m** (commonly rounded to £58m), accompanied by an apology. Because much of the settlement was consumed by litigation funding and legal costs, individual claimants received only a fraction of their losses — a key reason the government later established dedicated redress schemes (Section 5). The Fraser judgments also provided the evidential foundation for the criminal appeals that followed.

---

## 4. The Statutory Public Inquiry

### 4.1 Establishment and scope

A government review into the scandal was **converted into a full statutory public inquiry in 2021**, chaired by retired High Court judge **Sir Wyn Williams**. The **Post Office Horizon IT Inquiry** (postofficehorizoninquiry.org.uk) was structured into multiple phases (commonly described as seven), covering the human impact; the procurement, design and operation of Horizon; the conduct of investigations and prosecutions; redress and compensation; governance, oversight and whistleblowing; and recommendations.

### 4.2 Scale of evidence

The inquiry held **226 days of hearings**, heard oral evidence from **298 witnesses**, and disclosed/scrutinised in the order of **2 million pages** of documents (roughly 274,604 documents disclosed). Hearings featured testimony from sub-postmasters, Post Office and Fujitsu staff and executives (including former CEO Paula Vennells), government officials and ministers.

### 4.3 Volume 1 of the final report (8 July 2025)

Sir Wyn Williams published **Volume 1** of the inquiry's final report on **8 July 2025**, focused on the **human impact** of the scandal and the **redress schemes**. Key points:

- It set out the suffering of affected people through first-hand accounts, finding the situation "profoundly disturbing."
- It found that **at least 13 people may have taken their own lives** in connection with the scandal and **59 contemplated suicide**, and estimated **more than 10,000 people** were affected.
- It made **19 recommendations**, focused on making redress faster and fairer — including: allowing an independent route to **appeal a fixed-sum offer** in the Horizon Shortfall Scheme; establishing a **redress scheme for family members** of affected sub-postmasters; allowing GLO claimants to retain (“bank”) the best offer available to them; defining **"full and fair" redress** as compensation equivalent to what a court would award at the top of the damages range; and exploring a standing **independent body to deliver redress** in future scandals.

### 4.4 Government response and later volumes

The **Department for Business and Trade** responded on **12 February 2026**, **accepting 18 of the 19 recommendations** and rejecting one (Recommendation 13, on closing the Dispute Resolution Procedure). **Subsequent volume(s)** — examining systemic failures, the role of senior leadership, the legal profession, governance and individual accountability — are expected in or after **2026**; as of this report no firm publication date had been announced, with the **Maxwellisation** process (giving criticised individuals the right to respond, under Rule 13 of the Inquiry Rules 2006) ongoing.

---

## 5. Legal and Redress Aftermath

### 5.1 Quashing of convictions

- **December 2020.** The first six convictions based on Horizon evidence were quashed at Southwark Crown Court.
- **April 2021 — *Hamilton & Others v Post Office* [2021] EWCA Crim 577.** The Court of Appeal (Criminal Division) **quashed 39 convictions**, finding that in 39 cases the prosecutions involved an abuse of process — both because Horizon's reliability was essential to the conviction and the Post Office had failed to investigate and disclose properly ("category 1" abuse), and, in many, because the prosecutions were "an affront to the public conscience" ("category 2" abuse). The court described the Post Office's conduct as undermining public confidence in the criminal justice system.
- Further convictions were quashed individually by the appeal courts of England and Wales, Scotland and Northern Ireland, but the case-by-case route was slow.

### 5.2 The Post Office (Horizon System) Offences Act 2024

To exonerate the remaining victims at scale, Parliament passed the **Post Office (Horizon System) Offences Act 2024**. The Bill was introduced on **13 March 2024**, passed on **23 May 2024**, received Royal Assent on **24 May 2024**, and came into force immediately. The Act **automatically quashes**, by statute, qualifying convictions for specified dishonesty offences (theft, fraud, false accounting) prosecuted by the Post Office or the CPS within defined date and circumstance criteria. Convictions already considered by the Court of Appeal were **excluded**. Parallel legislation addressed Scotland and Northern Ireland. This blanket legislative quashing of convictions was unprecedented and prompted constitutional debate about Parliament overriding the courts; it was justified by government and many commentators as a proportionate response to a systemic injustice.

### 5.3 The compensation / redress schemes

Four principal schemes have operated, with combined redress of approximately **£1.56 billion paid to over 12,300 claimants as of 30 April 2026** (government estimates total redress at around **£2 billion**):

| Scheme | Who it covers | Status / progress as of 30 April 2026 |
|---|---|---|
| **Horizon Shortfall Scheme (HSS)** | Sub-postmasters who suffered shortfalls but were **not** GLO claimants and were not convicted. Established 2020. | ~**£943m** paid; **13,982** claims received, **11,109** paid. Closed to **new applications on 31 January 2026** (continues processing existing claims). Fixed-sum awards of ~£629m to 8,394 claimants; ~£119m in top-ups. Appeals route (HSSA) created. |
| **GLO Compensation Scheme (GLOS)** | The **555** *Bates v Post Office* group litigants, to top up their inadequate 2019 settlement share. | ~**£226m** paid; of ~492 eligible, **465 (95%)** had received substantial redress; **443** paid in full and final. Closes to new applications **31 July 2026**, with the scheme expected to conclude **31 December 2026**. |
| **Overturned Convictions (OC) scheme** | People whose convictions were overturned by the courts (e.g. *Hamilton*). Post Office–run. | ~**£68m** paid prior to closure; **formally closed 2 June 2025**. |
| **Horizon Convictions Redress Scheme (HCRS)** | People whose convictions were quashed by the **2024 Act**; **government-run** (Department for Business and Trade). | ~**£312m** paid; **511** full-and-final claims received, **492** paid (487 via fixed-sum acceptances). |

Affected people whose convictions were quashed could opt for a **fixed-sum settlement** (a standard offer, e.g. £600,000 for those exonerated by the 2024 Act) or pursue a fuller individually assessed claim. The schemes have been criticised for delays, legalistic processes and the burden placed on claimants; Sir Wyn Williams' Volume 1 recommendations were aimed squarely at these shortcomings. **Sir Gary Hickinbottom** was appointed HSS Senior Lawyer to drive timely, "full and fair" offers.

### 5.4 Accountability and Fujitsu's contribution

A Metropolitan Police-led criminal investigation, **Operation Olympos**, is examining potential offences of **perjury and perverting the course of justice** (with **corporate manslaughter** reported to be under consideration), with reports of around **eight suspects** and dozens of persons of interest; trials are not expected before **2027–2028**. As of this report, **no Post Office or Fujitsu executive has been criminally convicted** in connection with the scandal.

**Fujitsu** has publicly acknowledged a **"moral obligation"** to contribute to redress costs but, per reporting through March 2026, had **not made any interim payment nor agreed a figure**, stating it would await the conclusion of the inquiry — drawing criticism from MPs and campaigners (Lord Arbuthnot called for an interim **£700m**). Government has pressed Fujitsu for an interim contribution.

### 5.5 The pre-Horizon "Capture" system

Separately, attention has turned to **Capture**, a Post Office accounting software product used by some branches in the **1990s before Horizon**. Forensic firm **Kroll** concluded there is a "reasonable likelihood" Capture could also have caused shortfalls; the **Criminal Cases Review Commission** began reviewing Capture-related convictions in 2024. This is relevant context for the **provenance and reliability of historical branch records** predating Horizon.

---

## 6. The Replacement Programme

### 6.1 New Branch IT (NBIT) — a troubled in-house build

The Post Office launched the **New Branch IT (NBIT)** programme — its in-house effort to build a Horizon replacement — around **May 2022**. NBIT ran into serious difficulty: delays, **cost overruns**, and concerns about software quality. The Post Office reportedly sought around **£1bn of additional public funding** in connection with the programme. Post Office chairman **Nigel Railton** publicly stated NBIT was effectively **"set up to fail,"** and that the decision to build the replacement **in-house** was "fundamentally wrong in hindsight." Reporting indicates the **NBIT programme was abandoned**, with a cited taxpayer cost reaching the order of **£1bn**, and replaced by a portfolio-based strategy — referred to as the **Future Technology Portfolio (FTP)**.

### 6.2 Current replacement strategy

The Post Office's current approach is a **competitive procurement** rather than an in-house build, and a broader **system redesign** rather than a simple EPOS swap. Post Office CTO **Paul Anastassi** has described Horizon as comprising **more than 80 components**, of which only about half are managed by Fujitsu, with the remainder internal or supplied by other third parties. The stated target architecture is a **composable, event-driven, service-oriented architecture** built from standards-based modular components, including **migration from on-premise data centres to the cloud** and a **cloud-native back-office and channel platform**.

The procurement has been reported as split into two lots. **Note: source descriptions of the lot numbering are inconsistent** — Computer Weekly reporting variously labels them — but the **two work packages** are consistently described as:

- An **operations / transition package** (sometimes "Walk In and Take Over" / WITO), reported at around **£323m**, covering application support, development and release management, the cloud migration and the cloud-native platform.
- An **EPOS replacement package**, reported at around **£160m–£169m**, to provide an **off-the-shelf point-of-sale system** to replace the Horizon front end.

Reported timeline and funding: supplier contracts were expected to be **signed in summer 2026**; **Fujitsu's exit** was projected for roughly **eight to twelve months after both contracts are signed** (i.e. broadly mid-2027), with **complete eradication of Horizon targeted by 2030** and cutover/training of postmasters spanning **mid-2026 to end-2028** in some accounts. The UK government committed substantial funding to Post Office IT transformation (figures including a **£483m** commitment reported in February 2026, and references to total investment exceeding **£700m**). Fujitsu's Horizon contract was extended via bridging arrangements (e.g. a **£41m** extension) to around **March 2027**.

### 6.3 The Accenture involvement — what is and is not confirmed

**The project context for this report states:** *"Accenture has won the deal to replace Fujitsu in running the Horizon IT system."* Research partially corroborates this, but with important caveats:

- **What reporting indicates (21 May 2026):** On the date of this report, **wire-service coverage (Press Association, carried by regional outlets) stated that the Post Office has named Accenture and One View Commerce (OVC) as the suppliers selected** to take over operating Horizon from Fujitsu and to work together to **build the technology intended to replace it**. This is consistent with the procurement described above (Accenture had previously been reported by Computer Weekly as a bidder).
- **Separately and already confirmed:** the Post Office awarded Accenture a **distinct, non-Horizon contract** — reported at around **£45m**, running **1 April 2026 to 30 June 2029** — to modernise and support its **back-office IT applications** (hosting, operation and maintenance of core applications, explicitly **excluding** the Horizon system itself). A further reported additional Accenture spend (~£54m, awarded outside competitive tender) also relates to back-office modernisation. These back-office contracts are **not** the Horizon takeover.
- **What could NOT be verified from the sources reviewed:** the **contract value(s)** for the Accenture/OVC Horizon work; the **precise division of scope** between Accenture and OVC (and how this maps onto the two procurement lots); the **contract signature and start dates**; the **exact date Fujitsu will cease running Horizon**; and whether the selection is a final, signed award or a "preferred/named supplier" announcement pending contract execution. As recently as **May 2026**, Computer Weekly reporting still described the Horizon operations lot as **at the bidding/shortlist stage** (with Accenture, IBM/DXC and Escher among contenders) — so the 21 May 2026 naming appears to be a **very recent development**, and the same-day wire coverage did not include commercial detail.

**Recommendation for the project team:** treat the Accenture/OVC role as **reported but not yet fully documented**. Confirm the specifics directly from a **Post Office Ltd official announcement / corporate communications**, the **government (DBT) statements**, and any **published contract award notices** (e.g. Find a Tender / Contracts Finder) before relying on values, dates or scope boundaries in architecture or governance documents. Do **not** assume Accenture's previously confirmed back-office contracts are the same engagement as the Horizon takeover.

---

## 7. Implications for a Replacement Architecture

The Horizon history is not merely background — it defines hard, non-negotiable requirements and risks for any team building or running the replacement system. Key implications:

1. **A profound trust deficit must be designed against.** The replacement will be scrutinised by sub-postmasters, Parliament, the inquiry's legacy, the media (Computer Weekly remains highly engaged) and the public. The system and the programme should be **transparent and explainable by default**, and design decisions should be documented in a way that can withstand external and legal scrutiny.

2. **Transaction integrity must be provable and tamper-evident.** Branch accounts must be backed by an **immutable, cryptographically verifiable, append-only audit trail** of every transaction and every adjustment. It must be possible to reconstruct, definitively, what happened in a branch on any given day — and to demonstrate that the record has not been altered.

3. **Covert remote access must be eliminated.** The single most damaging fact about Horizon was that third parties could **alter branch accounts remotely** while the Post Office denied it was possible. The replacement must ensure that **no party can change a branch's financial records without the change being authenticated, attributed to a named individual, fully logged, immutably recorded, and visible to the affected sub-postmaster**. "Support" access that can mutate financial data without the postmaster's knowledge must be architecturally impossible, not merely discouraged by policy.

4. **The sub-postmaster's view must be authoritative and complete.** Sub-postmasters must be able to see **everything** that affects their accounts — including any centrally or remotely initiated entries — in clear, intelligible terms, in real time, with the data and tools to **understand and challenge** a discrepancy before any liability attaches.

5. **Robust, fair, independent dispute and discrepancy handling.** Apparent shortfalls must be **presumed to require investigation, not presumed to be the postmaster's fault**. There must be a defined, fair process — ideally with **independent oversight** — for raising, investigating and resolving discrepancies, and liability must not be imposed while a genuine dispute is unresolved. The contractual relationship and any "make good" obligations should be re-examined in light of Fraser's Common Issues findings.

6. **Bug/error transparency and disclosure obligations.** Known defects (a "bugs, errors and defects" register) must be **tracked, disclosed and accessible** to affected parties. Any process that uses system data as evidence — internally or in any legal context — must be founded on an honest, current assessment of system reliability. The catastrophic failure here was concealment of known defects.

7. **Migration of disputed and historical records.** Migrating data from Legacy Horizon, Horizon Online/HNG-A (and the awareness that pre-Horizon **Capture** data is itself contested) demands extreme care. Historical balances and disputed items must be **clearly flagged as to provenance and reliability**, never silently presented as authoritative, and migration logic must be auditable. The replacement must not "launder" disputed historical figures into apparently clean opening balances.

8. **Independent assurance and governance throughout.** Horizon went live over the objections of IT specialists; NBIT was later judged "set up to fail." The replacement programme needs **genuine independent technical assurance**, realistic governance gates, honest status reporting, and a culture in which **bad news travels upward** — explicitly the opposite of the Fujitsu/Post Office culture the inquiry exposed.

9. **Supplier and contractual accountability.** Clear allocation of responsibility across the (reported 80+) components and multiple suppliers — including the incoming operators (reported as Accenture/OVC) and the EPOS provider — is essential. Contracts should provide for transparency, access to evidence, defect disclosure and meaningful accountability, avoiding the opacity that characterised the Fujitsu arrangements.

10. **Resilience, exit and continuity.** The decade-long difficulty of exiting Fujitsu shows the cost of lock-in. The new architecture's emphasis on **composable, standards-based, modular, cloud-native** components should be matched by deliberate **exit strategy, data portability and avoidance of single-supplier dependence**, so a future transition is not another multi-year, multi-hundred-million-pound ordeal.

---

## Sources

- British Post Office scandal — Wikipedia: https://en.wikipedia.org/wiki/British_Post_Office_scandal
- Bates & Others v Post Office Ltd — Wikipedia: https://en.wikipedia.org/wiki/Bates_%26_Others_v_Post_Office_Ltd
- Computer Weekly — Post Office Horizon scandal explained: everything you need to know: https://www.computerweekly.com/feature/Post-Office-Horizon-scandal-explained-everything-you-need-to-know
- Computer Weekly — How Fujitsu became a central part of the Post Office scandal: https://www.computerweekly.com/news/366565720/How-Fujitsu-became-a-central-part-of-the-Post-Office-scandal
- Computer Weekly — Eradicating Fujitsu and Horizon from the Post Office, step by step: https://www.computerweekly.com/news/366639049/Eradicating-Fujitsu-and-Horizon-from-the-Post-Office-step-by-step
- Computer Weekly — Fujitsu will be out by summer 2027, says Post Office CTO: https://www.computerweekly.com/news/366638999/Fujitsu-will-be-out-by-summer-2027-says-Post-Office-CTO
- Computer Weekly — Accenture joins IBM in battle for £323m Post Office Horizon deal: https://www.computerweekly.com/news/366642986/Accenture-joins-IBM-in-battle-for-323m-Post-Office-Horizon-deal
- Computer Weekly — What will the Post Office scandal bring in 2026?: https://www.computerweekly.com/news/366636915/What-will-the-Post-Office-scandal-bring-in-2026
- Computer Weekly — Fujitsu UK pays staff bonuses as it sits on Post Office scandal contribution: https://www.computerweekly.com/news/366642879/Fujitsu-UK-pays-staff-bonuses-as-it-sits-on-Post-Office-scandal-contribution
- Press Association (via Fenland Citizen) — Post Office names Fujitsu's replacements to run scandal-hit Horizon system: https://www.fenlandcitizen.co.uk/national/post-office-names-fujitsu-s-replacements-to-run-scandal-hit-horizon-system-166990/
- UKAuthority — Post Office awards non-Horizon modernisation work to Accenture: https://www.ukauthority.com/articles/post-office-awards-non-horizon-modernisation-work-to-accenture
- The Stack — Post Office skips tender, spends another £54m with Accenture: https://www.thestack.technology/post-office-skips-tender-to-spend-another-54m-with-accenture/
- Post Office Horizon IT Inquiry — Homepage: https://www.postofficehorizoninquiry.org.uk/
- Post Office Horizon IT Inquiry — Volume 1 of the final report: https://www.postofficehorizoninquiry.org.uk/volume-1-post-office-horizon-it-inquirys-final-report
- Post Office Horizon IT Inquiry — Volume 1 Rapid Read (PDF): https://www.postofficehorizoninquiry.org.uk/sites/default/files/2025-07/Post_Office_Horizon_Inquiry_Volume_1_Rapid_Read.pdf
- GOV.UK — Government response to the Post Office Horizon IT Inquiry report (volume 1): https://www.gov.uk/government/publications/government-response-to-the-post-office-horizon-it-inquiry-report-volume-1/government-response-to-the-post-office-horizon-it-inquiry-report-volume-1
- GOV.UK — Post Office Horizon financial redress data as of 30 April 2026: https://www.gov.uk/government/publications/post-office-horizon-financial-redress-and-legal-costs-data-for-2026/post-office-horizon-financial-redress-data-as-of-30-april-2026
- GOV.UK — Post Office Horizon IT Inquiry (collection): https://www.gov.uk/government/collections/post-office-horizon-it-inquiry
- GOV.UK — Post Office GLO Scheme to close following successful delivery: https://www.gov.uk/government/news/post-office-glo-scheme-to-close-following-successful-delivery
- Judiciary of England and Wales — Bates v Post Office (Horizon Issues) judgment (PDF): https://www.judiciary.uk/wp-content/uploads/2019/12/bates-v-post-office-judgment.pdf
- Judiciary of England and Wales — Hamilton & Others v Post Office, summary (PDF): https://www.judiciary.uk/wp-content/uploads/2022/07/Hamilton-Others-v-Post-Office-summary-230421.pdf
- BAILII — Hamilton & Ors v Post Office Ltd [2021] EWCA Crim 577: https://www.bailii.org/ew/cases/EWCA/Crim/2021/577.html
- legislation.gov.uk — Post Office (Horizon System) Offences Act 2024: https://www.legislation.gov.uk/ukpga/2024/14
- UK Parliament — Post Office (Horizon System) Offences Act 2024, Parliamentary Bills: https://bills.parliament.uk/bills/3694
- Hansard — Post Office Horizon Inquiry: Volume 1: https://hansard.parliament.uk/commons/2025-07-08/debates/25070846000011/PostOfficeHorizonInquiryReportVolume1
- ITV News — MPs criticise Fujitsu for not contributing 'a penny' to Post Office redress: https://www.itv.com/news/2026-03-13/mps-criticise-fujitsu-for-not-contributing-a-penny-to-post-office-redress
- Post Office Ltd — Horizon Shortfall Scheme: information and data: https://corporate.postoffice.co.uk/horizon-scandal-pages/horizon-shortfall-scheme-information-and-data/

---

*Prepared as background reference material for the enterprise architecture project replacing the Post Office Horizon IT system. Compiled from publicly available sources as of 2026-05-21. Where reporting was contested or unverified — in particular the commercial specifics of the Accenture/One View Commerce Horizon engagement — this is stated explicitly in the relevant section. Figures and dates should be re-verified against primary sources before use in formal governance artefacts.*
