# The Zero-Ties Laptop: A Complete Audit of Israeli Entanglement in the Personal Computer Supply Chain

αΩ∞

*A fully-sourced investigation into whether a laptop with zero ties to Israel — in any way, foreign or domestic — can exist, and what the closest achievable alternatives are.*

---

## 1. The Question

The question sounds simple: **is there a laptop on the market with zero ties to Israel — no Israeli-designed components, no Israeli corporate involvement, no Israeli software, nothing?**

It turns out to be one of the hardest "simple" questions in consumer technology, because the answer is not found in any single part, brand, or factory. The answer is buried across five different structural layers of the global electronics industry, most of which are invisible to the buyer — and invisible to most of the industry itself.

This document audits every layer, names the specific companies, dollar figures, acquisitions, contracts, executives, and engineering centers involved, and then builds — piece by piece — the closest thing to a clean laptop that can actually be purchased, along with the only literal zero-tie paths that exist.

### How to read this document

- **Part 2** gives the short answer.
- **Part 3** explains the five-layer framework — the mental model for everything that follows.
- **Parts 4–12** are the layer-by-layer audit (the evidence): CPU, GPU, memory and storage, power, connectivity and sensors, software, the PC brands, the chip-design tooling, and manufacturing.
- **Part 13** is the practical result: the minimum-ties build.
- **Part 14** covers the literal zero-tie alternatives.
- **Part 15** examines the people layer — the one thing no purchase decision can reach.
- **Part 16** explains how we know what we know (methodology and evidence grading).
- **Part 17** lists what remains unresolved.
- **Part 18** is a key-figures table for quick reference.
- **Part 19** is a glossary of every technical term used.
- **Part 20** is the conclusion, in one paragraph.

A note on framing before we begin: this document does not argue for or against any political position. The user's requirement is a supply-chain criterion — zero ties to Israel — and this document measures the market against that criterion. Where Israeli involvement is found, it is documented with sources. Where it is *not* found, that is documented too, with the same care. Where evidence is ambiguous, the ambiguity is preserved rather than resolved by opinion.

---

### A thirty-second orientation for readers new to computer hardware

A laptop is a stack of roughly a dozen independently made technologies that happen to snap together. There is one main chip — the **CPU**, the computer's brain — plus memory (short-term workspace), storage (long-term files), a Wi-Fi radio, a webcam, power-management chips, firmware (software etched into the hardware itself), an operating system, and finally the brand-name shell. Each of those pieces is typically **designed in one country, manufactured in another, and assembled in a third**, often by companies the buyer has never heard of. Two facts from that sentence drive this entire document: first, "designed in" matters as much as "made in," because design authorship is invisible in the finished product yet embedded in everything it does; and second, the brand on the lid is often the *least* informative thing about the machine. Keep those two ideas in mind and every section below will read clearly.

---

## 2. The Short Answer

**No commercially available laptop has zero ties to Israel.** Not one. The reason is structural, not incidental:

1. **Every viable laptop CPU architecture has Israeli engineering at its core.** Intel's modern processor lineage — the chips inside the majority of the world's PCs — was designed in Israel, from the 8088 in 1979 to the Core Series 4 shown at CES 2026. Apple's M-series chips (M1 Pro, M1 Max, and successors) were physically designed and validated in Israel. The ARM architecture underlying nearly all remaining chips has Israeli-developed components, including its flagship GPU. The only mainstream exception is AMD's Zen architecture — and AMD the *corporation* still maintains documented Israeli ties, even though its silicon does not appear to.

2. **The tools used to design chips are also entangled.** The two companies whose software designs virtually every commercial chip on Earth — Synopsys and Cadence — both operate Israeli development centers. Even a hypothetical "clean" chip is authored with Israeli-engineered tooling.

3. **The major PC brands are entangled at the corporate level.** HP has supplied the Israeli military with PCs since 2009. Dell won a two-year Israeli Ministry of Defense server tender worth over $150 million in January 2023. Lenovo completed a $500M+ acquisition of an Israeli storage company in April 2026, embeds Israeli-founded security software in new PCs, and now owns one of the major BIOS firmware vendors (Phoenix Technologies, acquired April 2026).

4. **The dominant operating system has the deepest verified entanglement of all.** Microsoft's relationship with Israeli military intelligence is documented at audit level: Unit 8200 — Israel's signals-intelligence agency — operated a customized Azure cloud environment storing and analyzing intercepted Palestinian phone calls, a relationship that followed a 2021 meeting between Microsoft's CEO and Unit 8200's commander. Microsoft's own follow-up review in September 2025 found evidence supporting elements of that reporting, and it disabled specified Israeli Ministry of Defense services.

5. **The people layer cannot be excluded by any purchase decision.** An estimated ~1,400 veterans of Israeli intelligence units work across US technology companies (per MintPress/Drop Site News research), concentrated in exactly the companies that design laptop silicon and software. Talent is not a component, and it cannot be specified out of a bill of materials.

**The closest achievable mainstream machine** — detailed in Part 10 — is an ASUS or Acer laptop with an AMD Ryzen CPU, Realtek Wi-Fi, SK Hynix memory, a Kioxia-based SSD, an OmniVision webcam on the USB path, and Linux running Firefox. Every one of those choices is individually defensible as clean or nearly clean. The residual ties (AMD's corporate-level Israeli presence, the EDA tooling authorship, partial Linux sponsorship taint) are irreducible.

**The only literal zero-tie paths** — detailed in Part 11 — are Chinese domestic Loongson/LoongArch machines and immature RISC-V machines, each with major practical tradeoffs.

Even the global boycott movement's own materials implicitly concede the point: no BDS-aligned guide claims a certified "Israel-free" laptop exists. Ethical Consumer's 2024 laptop guide recommends Framework and TCO-certified ASUS — recommendations based on *corporate conduct*, while the silicon problem underneath remains acknowledged but unresolved.

---

## The Plain-Language Version (Start Here If Chip Terminology Is New to You)

Everything in this document can be understood with one analogy: **a laptop chip is like a building.**

The factory that pours the concrete is only the last step. Before that, an architect draws the plans — the floor-by-floor layout, the wiring, the load-bearing walls. In chip terms, that drawing stage is called **design**, and the drawing itself is called a **tape-out** (because the finished design used to be sent to the factory on reels of magnetic tape). A chip can be designed in one country, manufactured in a second, assembled into a laptop in a third, and sold by a brand in a fourth. Each stage can have a different nationality.

This matters because of how the industry has evolved. Most people assume a product "comes from" wherever it is physically made. But semiconductors inverted that logic decades ago: the *design* is where the value and the authorship live. A processor designed in Haifa, Israel, and manufactured in Taiwan is Israeli-designed and Taiwanese-made — and the Israeli contribution travels inside every one of the millions of copies made, because it is baked into the plan itself. You cannot unscrew it, the way you could unscrew a foreign-made part.

Now add one more twist: even the architect doesn't draw by hand. Modern chips contain tens of billions of transistors — switches far too numerous for any human to place individually. Architects use specialized software to draw them, called **EDA** (Electronic Design Automation). There are effectively only two companies that make this software: Synopsys and Cadence. And both of those companies employ engineers in Israel. So even a chip with no Israeli designers on the team was drawn with tools containing Israeli engineering — the drafting software has its own nationality problem.

Then there is the hidden computer inside your computer. Every laptop ships with firmware — software frozen into the hardware itself. Intel builds one called the **Management Engine** (ME), AMD one called the **Platform Security Processor** (PSP). These are tiny computers that run *below* your operating system, with access to everything — screen, keyboard, network — and that the owner cannot inspect or disable. This document doesn't claim they contain Israeli code; it claims something more basic: every Intel Management Engine runs on Intel silicon, and Intel's silicon is Israeli-designed. The hidden layer and the design layer meet inside the same chip.

Finally, the cloud. When this document says Israeli military intelligence used Microsoft's Azure, here is what that means in everyday terms: Microsoft rents out computing power the way a landlord rents offices, over the internet, in enormous warehouses of computers called data centers. An Israeli intelligence unit (Unit 8200 — think of it as Israel's equivalent of the NSA's most elite department, staffed largely by soldiers recruited straight out of high school) reportedly rented a private, walled-off section of that computing power and stored intercepted phone calls in it. Journalists reported this; Microsoft first said its leadership didn't know, then ran its own review and announced it had found evidence supporting parts of the story, and switched off some of the services. Why does a laptop buyer care? Because that landlord also makes Windows — the operating system that would run on most laptops — and this record describes the *company*, not one product line.

One last decoding tool: the audit **scores**. You will see numbers like "BRS 712, Tier B (Severe)." These come from a research project called OpenIntel, which builds dossiers on major technology companies and scores how directly each is involved with Israel across four areas: military, digital, economic, and political. A higher number means more documented, more direct involvement. "Tier B (Severe)" is the second-highest of its bands. These scores are one framework's judgments, and this document quotes them the way it quotes everything else — as a documented summary of named facts, not as an endorsement of the framework's politics. Every underlying fact is also stated on its own, so you never have to take the score on faith.

With those five ideas — design vs. manufacture, EDA tooling, firmware, the cloud, and the audit scores — the rest of this document reads as a single connected story: who drew the plans for your laptop, who owns the companies on the lid, who their customers are, and how close to "zero ties" a real purchase can honestly get.

---

## 3. The Five Layers of Entanglement: A Framework

Think of a laptop not as a product but as a stack of layers, each of which can be independently audited. When people ask "is there Israeli involvement in this laptop?", they are usually imagining one layer — usually the assembly plant, or perhaps the brand name on the lid. The entanglement, however, lives in five distinct places:

- **Layer 1 — Authorship (who designed the silicon).** A chip can be fabricated in Taiwan, assembled in China, and shipped by an American brand — and still be *designed* in Haifa or Herzliya. Design authorship is the least visible and most consequential layer, because it is embedded in the chip's architecture itself and follows the product everywhere it goes.

- **Layer 2 — Tooling (what designed the silicon).** No human draws a modern chip by hand. Chips are designed using Electronic Design Automation (EDA) software — effectively, the CAD tools of the semiconductor world. If the EDA software itself contains Israeli engineering, every chip built with it carries that connection regardless of where the chip company is headquartered.

- **Layer 3 — Ownership (who owns whom).** Acquisitions, subsidiaries, venture investments, and voting control. A Taiwanese laptop brand can be clean in every factory and still be entangled if its supplier is majority-owned by a company with deep Israeli operations.

- **Layer 4 — Contracts (who sells to whom).** Military tenders, government cloud contracts, security-agency relationships. This is the layer that forensic audits (like the OpenIntel BDS-1000 assessments cited throughout this document) examine most closely, because it is the layer where corporate relationships become state relationships.

- **Layer 5 — People (who built it).** Engineers move between companies and countries. Unit 8200 — the Israeli military's elite signals-intelligence unit, roughly analogous to the NSA's Tailored Access Operations combined with a national talent academy — feeds thousands of alumni into global tech. This layer cannot be audited from a spec sheet at all.

The audit that follows walks the *physical* laptop layer by layer (silicon, memory, power, connectivity, sensors, firmware, software, OEM, manufacturing), and overlays the five entanglement layers onto each. Every claim carries a source. Where the evidence is strong, it is stated strongly. Where it is thin, it is labeled thin.

---

## 4. The CPU Layer: The Fatal Layer

The central processing unit is the laptop's brain, and it is where the entanglement is deepest. There are effectively three viable paths to a laptop CPU in 2026: Intel, Apple, and the ARM ecosystem (Qualcomm, Samsung, MediaTek, and everyone else). AMD is the fourth path — and the only one with no Israeli silicon authorship.

### 4.1 Intel — the deepest entanglement in the industry

Intel's relationship with Israel is not a footnote in company history; it is, by several measures, the single most important bilateral relationship in the semiconductor industry. The verified facts, in sequence:

**1974 — the founding.** Dov Frohman — a Holocaust survivor's son, Technion graduate, and the inventor of the EPROM (Erasable Programmable Read-Only Memory, an early chip that could be rewritten) — convinced Intel co-founder Andy Grove to open Intel's first design center outside the United States, in Haifa, initially with four workers. Gordon Moore, Intel's other co-founder, called Frohman's EPROM "as important in the development of the microcomputer industry as the microprocessor itself." *Why this matters: the EPROM made it possible to revise chip logic after manufacturing — a foundational enabler of the entire iterative design culture that later produced Intel Israel's design dominance.*

**1978–1979 — the 8088.** The Haifa team designed the 8088, a cost-reduced variant of Intel's 8086 processor with an 8-bit external bus, which IBM selected for its first personal computer in 1981. Every x86 PC architecture in existence descends from this decision. The Haifa center also designed Intel's first math coprocessor (1979) and later the MMX multimedia instruction set (mid-1990s), the Pentium MMX, the Pentium 4, and the Centrino platform — which integrated Wi-Fi into the laptop for the first time and, in Intel's own description, made Intel Israel "the headquarters for the corporation's global R&D for wireless technology." The Centrino line is what ignited the Wi-Fi laptop boom of the 2000s — meaning the Israeli design center midwifed the very concept of the modern laptop.

**1984–1985 — Jerusalem fab.** Intel built its first fabrication plant outside the US — in Jerusalem (Fab 8). A "fab" is the factory where chips are physically manufactured: a clean-room facility costing hundreds of millions to billions of dollars, printing circuit patterns onto silicon wafers. The Jerusalem fab cost $700 million — a project that included the first-ever Israeli government grant to Intel ($188 million). By the early 1990s, the Jerusalem fab was producing roughly **75% of global output of the 386 processor**, the chip that carried the PC through its first decade of mass adoption. The Jerusalem fab closed in 2008, briefly reopened as a die-preparation facility (the step where finished silicon wafers are cut apart into individual chips) in 2009, and closed permanently in 2016.

**1995–2008 — Kiryat Gat.** Intel built Fab 18 in Kiryat Gat in 1995 — the site Intel itself describes as its most advanced manufacturing facility — then Fab 28 in 2008 — a $3.5 billion project described at the time as the largest construction project in the history of the state of Israel. In 2007, Intel Israel's exports reached $1.4 billion, equal to 8.5% of Israel's total electronics exports.

**2003–2015 — the modern Core lineage.** The Banias project (released as the Pentium M in 2003) saved Intel's laptop roadmap and was developed in Israel; its successor Merom became the Core 2 Duo, the chip that made "Core" the dominant brand in computing. Sandy Bridge and Ivy Bridge — at their peak accounting for roughly 40% of Intel's global sales — were developed in Israel. Haswell and Skylake followed the same path; Skylake was, per Israeli industry sources, "produced for the most part in Israel at Intel's Haifa research center." Intel Israel also developed Thunderbolt connectivity.

**2023–2024 — Fab 38, the grant, the freeze.** In December 2023, Intel finalized a $25 billion expansion of its Kiryat Gat complex (Fab 38), paired with a **$3.2–3.25 billion Israeli government grant**, preferential tax treatment, and a commitment to purchase approximately NIS 60 billion (roughly $16–17 billion) in goods and services from Israeli suppliers over the following decade. In June 2024, Intel halted construction, citing "changing schedules, business conditions, market dynamics and capital management." Israeli business outlet Globes reported the expansion frozen "for the foreseeable future." The underlying operations — fabs, development centers, ~9,000–11,700 employees — continued, but the freeze rippled immediately through the local supplier ecosystem: publicly traded Israeli contractor Lesico reported that delays to contracts worth over NIS 100 million would materially affect its performance, and Calcalist's reporting noted that equipment giants Applied Materials and KLA maintain Israeli operations precisely because of Intel's physical presence there.

**2024–2026 — the design lineage continues.** Even Intel's newest architecture is Israeli-developed: Israeli industry reporting confirms that the Core Ultra Series 3 and Core Series 4 processors unveiled at CES 2026 were "largely developed in Israel." Apple's hardware chief Johny Srouji, in a rare on-record interview, put it directly: "By no coincidence, the [Apple M1] Max and the Pro were launched at the same time as our competitor, Intel's new Alder Lake Core 12 processor, which was also developed in Israel. So, the crème de la crème of the world's computer processors are made in Israel."

**Scale, per Intel's own corporate reporting and Israeli business press.** Intel's Israel page reports 9,335 employees; Calcalist's September 2024 reporting put the figure at ~11,700 — approximately 10% of Intel's entire global workforce. Roughly 3,900 of them work in manufacturing at Kiryat Gat. Intel Israel reported $27 billion in cumulative capital investment through 2021 and $86 billion in cumulative exports through 2023. In 2022 alone, Intel's Israeli operations were responsible for almost 2% of Israel's entire GDP; its $9 billion in exports represented roughly 6% of all Israeli high-tech exports; it indirectly employed an estimated 42,000 people in secondary and tertiary roles and purchased $3.5 billion in goods and services from Israeli businesses. Calcalist's description: "Unlike many international companies that only have development centers or limited activities in Israel, Intel Israel operates like a small Intel USA." Intel is Israel's largest private-sector employer and its single biggest exporter. The Israeli corporate footprint includes registered entities such as Intel Israel (74) Ltd., Intel Electronics Ltd., Hampton Acquisition Ltd., Intel Semi Conductors Ltd., Intel Mobile Communications Israel Ltd., and Granulate Cloud Solutions Ltd. — a structure documented in Intel's own filing-grade disclosures. The development staff (~7,000 of the total) work across communications networks, data centers, PC processors, and AI — which is to say, across every division whose output ends up in a laptop.

**Corporate acquisitions (all Israeli).** Mobileye ($15.3 billion, 2017 — the autonomous-driving company Intel retains control of to this day: per Mobileye's 2025 Form 10-K, Intel held approximately 77% of common stock and 96.9% of voting power as of February 2026 — voting power being what actually commands a company: it elects the board and approves major decisions, so Intel's roughly 77% economic stake understates its roughly 97% control); Habana Labs (~$2 billion, December 2019, AI chips); Moovit (transit app); Granulate (~$650 million reported, cloud optimization). The proposed $5.4 billion acquisition of Tower Semiconductor was terminated in August 2023 after Chinese regulators withheld approval — had it closed, Israel would have become Intel's second-largest site worldwide after the US. Intel Capital had invested $120 million across 14 Israeli companies by 2018, and Intel joined Team8's cybersecurity syndicate in 2017 (Team8 is a venture group founded by a former Unit 8200 veteran).

**Military-adjacent integration (downstream, verified at audit level).** Elbit Systems' ETC MK7 and MK7+ tactical computers — ruggedized command-and-control systems used for tactical data dissemination, with series-level use by the Israel Defense Forces — incorporate commercial Intel Core i7 processors (the MK7+ brochure identifies an Intel Core i7-1370). This is commercial off-the-shelf silicon embedded in a military product; the audit (OpenIntel, BDS-1000 methodology) found no direct Intel–IDF or Intel–Israeli Ministry of Defense procurement contract, and explicitly records "no public evidence identified" of such a contract.

**Governance and politics.** The BDS Movement launched a named global #BoycottIntel / "Apartheid Chips" campaign in March 2024. Intel's board opposed — and shareholders rejected — an Ethical Impact Assessment proposal concerning Israeli operations in the 2025 proxy cycle (a proxy vote is the annual mechanism by which shareholders formally instruct corporate management; rejection means the policy was not adopted); the board also opposed a human-rights due-diligence proposal in the 2026 cycle. Intel's then-CEO Pat Gelsinger (a devout Christian who frequently quoted Torah verses and described himself as having a mission of loyalty to Israel) wrote to employees on October 8, 2023 expressing concern for Intel's Israel-based staff; Intel Israel and the Intel Foundation reported approximately ₪4 million in urgent aid plus ₪4.4 million in employee-directed donations and matching grants for 2023, including a one-time $5,000 wartime grant per Israel-based employee. Context worth preserving alongside: in July 2024 the US government announced a $3.5 billion grant for Intel to produce chips for the Department of Defense — a marker of how strategically important Intel's production had become to two states at once — and Israeli industry sources speculated that Tower Semiconductor (the company Intel failed to acquire) could one day buy the aging Kiryat Gat fab, which would keep the site's Israeli character intact under new ownership.

**Audit verdict.** OpenIntel's human-reviewed V6.5 assessment assigns Intel a BDS-1000 score of **712 — Tier B ("Severe Complicity")** — driven principally by the economic domain (Mobileye control, manufacturing scale, the state-grant relationship). One caveat the audit preserves: Kiryat Gat lies within Israel's pre-1967 territory, not in West Bank/East Jerusalem/Golan settlements, though NGO sources describe the site as associated with Palestinian villages depopulated in 1948 — a land-history finding the audit treats as distinct from post-1967 settlement activity.

**Bottom line for a laptop buyer:** every Intel laptop CPU from the 8088 to the Core Series 4 carries Israeli design authorship at the architecture level. There is no Intel CPU generation exempt from this.

### 4.2 Apple Silicon — the M-series, in Apple's own words

Apple's Israeli operation is younger than Intel's but, in chip-design terms, arguably more concentrated.

**The center.** Apple opened its Herzliya R&D center (12 Hamaskit Street) in March 2012 — its first outside the US — with a single employee: Aharon Aharon, Srouji's former lecturer at the Technion, who served as CEO of the center until 2017 (when he left to run the Israel Innovation Authority, the government's tech-funding body). By 2022 the center employed 1,800 people; Rony Fried has run it since 2017. Apple added a Haifa site and, later, a Jerusalem development center specifically earmarked for future Mac processors. In 2026, Apple elevated Johny Srouji — Haifa-born, Technion-educated, a former Intel Israel engineer (1992–1999) — to the new role of Chief Hardware Officer under incoming CEO John Ternus, and Sribalan Santhanam took over leadership of Apple Silicon development in Israel. The operation is growing.

**What the center builds — from Srouji's own interview (Ynet, on the record):**

- "Every storage controller in every Apple product comes from Israel." The storage-controller line began with Apple's first Israeli acquisition, Anobit, whose team produced the first Apple-designed storage controller — in a Mac — nine months after the acquisition closed, later adapted for iPhone and iPad.
- "The M1 Max has 57 billion transistors. Both [M1 Pro and M1 Max] were developed in Israel. Building the chip, assimilating it, its physical design, validation — was all conducted in Israel."
- The Apple Watch's entire SoC — "the watch's electronic brain" — plus its Wi-Fi and Bluetooth capability, were developed in Herzliya.
- PrimeSense (acquired 2013, the Israeli depth-sensing company) built the core technology behind Face ID; the LiDAR core technology integrated into iPhones and iPads is Israeli; Cinematic Mode (iPhone 13) is based on the same technology; Israeli teams built hand- and eye-tracking and depth-sensing components for Vision Pro.
- The Mac facilities program — the decision, effectively, to move the Mac off Intel — was architected around the Israeli design operation.

A separate MintPress/Drop Site News investigation identified dozens of Unit 8200 veterans inside Apple's chip teams, as part of a larger mapping of approximately 1,400 Israeli intelligence-agency veterans across US technology companies.

**A structural note on disclosure.** Apple's public communications have never named Israel as the location of its second-largest R&D operation outside the US — Israeli site expansions are announced only as happening "all over the world." The design authorship is real; the branding obscures it.

**The wider chip family.** Beyond the M1 Pro/Max, Israeli teams are publicly tied to the **M2** generation, the **R1** chip (the sensor-fusion processor inside the Vision Pro headset), the **C1** modem (Apple's first in-house cellular modem, which shifts modem design — long a Qualcomm domain — into the Israeli operation), and the **N1** wireless chip. A 2026 statement by Apple Israel's site lead, Rony Fried, distilled the pattern: "It's hard to find an Apple product that doesn't have some kind of touch from Apple employees in Israel."

**Bottom line for a laptop buyer:** every Apple laptop sold today carries silicon physically designed, integrated, and validated in Israel, plus Israeli storage controllers in every unit. MacBooks are among the *most* Israeli-authored laptops on the market.

### 4.3 AMD — the cleanest mainstream silicon, with corporate-level caveats

AMD is the only mainstream CPU vendor whose actual silicon appears free of Israeli authorship. The full record:

**The silicon is US-designed.** AMD's Zen microarchitecture — the design family inside every Ryzen laptop processor — was rebuilt under CTO Mark Papermaster (ex-IBM, ex-Apple, ex-Cisco), who joined in October 2011 and, per the public record, "restructured the CPU design team to build Zen." AMD's known CPU design sites are Austin, Boston, Fort Collins, and Bellevue — none in Israel. No evidence was found in any pass of this investigation of Israeli design involvement in Zen silicon, in the AGESA firmware, or in the PSP (Platform Security Processor, AMD's analog to Intel's Management Engine).

**The corporate ties are real but commercial-grade.** Per the OpenIntel forensic audit: the Graphic Remedy acquisition (~$5 million, October 2010) seeded a Ramat Gan/Tel Aviv R&D center (opened June 2011, focused on parallel computing and AMD's Fusion APU software); **Xilinx Israel Ltd. (Holon) is a 100%-owned AMD subsidiary**, per AMD's own FY2023 subsidiary schedule; AMD Ventures participated as a co-investor in Jerusalem-based Teramount's **$50 million Series A (July 2025)** — explicitly a participant, not the lead investor. AMD has a reported AI-inferencing collaboration with Israeli startup NeuReality, and its technology surfaces in Israeli product contexts (e.g., Kameleon Security's ProSPU). A 2020/2023 export-control incident involving AMD and Israeli firm CNG Labs was investigated and did not result in AMD enforcement action. An Israeli corporate registry entry for an "AMD Advanced Micro Devices Israel Ltd." entity shows as voluntarily eliminated — a low-confidence detail, preserved here for completeness.

**What the audit explicitly did *not* find:** any direct AMD or Xilinx Israeli military contract, any Project Nimbus role, any verified surveillance deployment, any settlement operation. The audit characterizes AMD's Israeli nexus as "economic rather than military or digital."

**Bottom line for a laptop buyer:** an AMD Ryzen CPU carries no Israeli silicon authorship — the design lineage is American. AMD the *corporation* maintains a small, documented, commercial-only Israeli presence (an R&D office, a wholly-owned subsidiary inherited from Xilinx, a venture stake). For a buyer applying a "zero ties in any way" standard strictly, this corporate residue is a tie; for a buyer applying a "nothing Israeli inside the machine" standard, AMD is the clean choice.

### 4.4 The ARM ecosystem — the architecture beneath everything else

Everything that isn't x86 (Intel/AMD) is, with rare exceptions, ARM. And ARM itself is entangled:

- **ARM (the company):** its Ra'anana development center's hardware teams oversee development of the flagship **Immortalis GPU** and chip-security components, inherited via the 2015 acquisition of Israeli security-IP firm Sansa Security. ARM licenses its processor designs and architecture to Qualcomm, MediaTek, Samsung, Apple, and effectively everyone else — so ARM's Israeli-engineered IP propagates into every non-x86 laptop chip.
- **Qualcomm:** two Israeli R&D centers (Haifa, Hod Hasharon) operating since 1993; five Israeli acquisitions between 2010 and 2016. Its Snapdragon laptop chips therefore carry both direct Israeli R&D and ARM-derived IP.
- **Samsung:** its Tel Aviv R&D center (SIRC) is responsible for development of next-generation flash/SSD/UFS/eMMC architecture and image sensors — Samsung-made storage, not just Samsung chips, has Israeli design involvement at the platform architecture level. (Samsung DRAM appears Korea-designed.)
- **Nvidia:** acquired Israeli chipmaker Mellanox for $6.9 billion in 2019; Nvidia Israel now accounts for over a tenth of Nvidia's global workforce and has been aggressively hiring ex-Intel Israel engineers.
- **Marvell:** three Israeli offices leading Ethernet/NIC development — relevant to docking stations and wired connectivity.
- **Historical footnote:** National Semiconductor operated a chip design center in Herzliya in the 1980s that co-developed hardware-description-language technology with Tel Aviv University — evidence that Israeli chip-design DNA in the US industry is generational, not recent.

**Bottom line:** the only CPU paths without Israeli architectural authorship are AMD's x86 (corporate ties only) and non-ARM, non-x86 architectures — Chinese Loongson or open RISC-V (see Part 11).

---

## 5. The GPU Layer

- **Intel Arc and Intel integrated graphics:** same Intel Israel design pipeline as the CPUs. Maximal entanglement.
- **Nvidia (GeForce/RTX in gaming laptops):** consumer GPU silicon is US-designed; the Mellanox acquisition adds Israeli networking IP (more relevant to datacenter than consumer laptops) and a large Israeli workforce.
- **AMD Radeon:** clean. The ATI lineage is Canadian (acquired 2006); leadership and engineering are US-based; no Israeli design centers were found in any pass.

**Practical consequence:** the GPU question resolves the same way as the CPU question — AMD is the clean path.

---

## 6. Memory & Storage

- **SK Hynix: clean.** No Israeli R&D center, acquisition, or design presence was found in any pass. Korean-designed, Korean-manufactured. Its external partnerships (e.g., MRAM co-development with Kioxia) do not involve Israel.
- **Kioxia: clean.** Japanese; its diversification partnership is with Taiwan's Nanya Technology.
- **Micron: not clean.** Micron's official R&D location list explicitly includes Israel, with an active Israel ASIC design team currently hiring (an E3-level ASIC Design Engineer posting for the Israel ASIC team). Historically, Micron operated a fab in Kiryat Gat — a plant Intel built and leased to Micron for NOR flash — until Intel repossessed it in 2010, absorbing roughly 800 Micron workers when Micron shut the line. Separately, SanDisk (now part of Western Digital) was co-founded by Israeli-born Eli Harari.
- **Samsung NAND/flash storage: compromised at the architecture level** via SIRC (above). Samsung DRAM appears Korea-designed and cleaner.
- **SSD controllers: clean.** Phison and Silicon Motion (Taiwan) dominate third-party controller supply; Realtek has entered the category. None has documented Israeli ties.
- **Dell/Lenovo storage software (ecosystem note):** Dell's PowerFlex storage platform is built on technology from Israeli company ScaleIO; Lenovo now owns Israeli storage vendor Infinidat (Part 9). These are enterprise products, not laptop components, but they document how deeply Israeli storage engineering runs through the OEM ecosystem.

---

## 7. Power & Battery Management

A laptop's power circuitry — the charger IC, the PMIC (power management integrated circuit), the battery fuel gauge — is a genuine blind spot in most supply-chain thinking. The audit found it mostly clean:

- **Intersil (now Renesas):** the dominant laptop battery-charger IC family (ISL6255, ISL9237, ISL88731, ISL95522, used across Dell, Lenovo, and HP boards) is US-origin (Milpitas, California), now owned by Japan's Renesas. No Israeli ties found.
- **Texas Instruments:** TI's Israeli chapter is real but irrelevant to its power products. TI's Israel operations were built on two 1990s acquisitions (Libit, $365 million; Betterplay, $50 million) focused on short-range communications (Wi-Fi/Bluetooth/NFC "Butterfly" technology); TI shut its Israel development center in 2013, laying off 250 staff — and **Apple hired 100–150 of those engineers**, who became core contributors to Apple's Ra'anana design center. So TI's old Israeli chip DNA literally flowed into Apple's silicon operation, while TI's laptop power ICs themselves show no Israeli authorship.
- **Monolithic Power Systems (MPS) and Richtek:** clean (US and Taiwan respectively).
- **Battery cells** (ATL, Panasonic, LG Energy Solution): clean.

---

## 8. Connectivity, Sensors, Firmware, and the Component Long Tail

### 8.1 Wi-Fi / Bluetooth / Ethernet

- **Avoid on a minimum-ties build:** Intel (Israeli-designed silicon), Qualcomm (Haifa/Hod Hasharon), Marvell (three Israeli offices), Broadcom (Israeli R&D).
- **Realtek: the practical clean choice.** Taiwan's leading fabless (chip-design-only; manufacturing outsourced) designer, in-house engineering, extremely widely used in AMD-based laptops. Caveat: Realtek SoCs license ARM processor cores and are built on Synopsys EDA platforms — an *indirect* taint through shared tooling and licensed IP, not Israeli-authored silicon.
- **USB controllers:** ASMedia and Genesys Logic (Taiwan) — clean.
- **Emerging vector to watch:** Astera Labs — a US connectivity-chip firm whose PCIe/USB4 retimer chips are entering new laptop designs — opened Ramat Gan and Haifa R&D offices in February 2026 by hiring roughly 60 hardware engineers from failed Israeli startup Pliops.

### 8.2 Webcam, fingerprint, touchpad, audio

- **Webcam sensors: OmniVision — clean of Israeli ties.** US-founded, majority-owned by China's Will Semiconductor since 2018–2019; ubiquitous in laptops (OV9734, OV02C10). **Critical caveat:** on Intel platforms, the sensor typically feeds an **Intel IPU6** imaging processor — an Israeli-designed chip. On AMD platforms, the same OmniVision sensor runs over a plain USB path with no Israeli imaging processor. This is a concrete, purchasable distinction.
- **Fingerprint sensors: Goodix — clean** (Chinese; used by Lenovo, Framework, and others). Synaptics (US): no Israeli footprint found.
- **Touchpads:** Synaptics (US) or Elan (Taiwan) — clean.
- **Audio codecs:** Realtek or Cirrus Logic — clean.

### 8.3 Firmware

- **Intel ME (Management Engine) / AMD PSP (Platform Security Processor):** the closed-source subsystems that run below the operating system (sometimes called "Ring -3" — a privilege level even the OS kernel cannot see into). No public source attributes ME development to Israel specifically — but every Intel ME instance runs on Israeli-designed silicon, and the early independent security research on ME came from Russian (Positive Technologies) and Polish (Invisible Things Labs) researchers, not from the vendor. The deeper point: the ME/PSP layer is un-auditable by the owner *regardless of nationality*, which is itself a finding worth stating plainly.
- **BIOS/UEFI vendors:** AMI, Insyde (US/Taiwan) — clean. **Phoenix Technologies' BIOS unit was acquired by Lenovo, deal closed 26 April 2026** — meaning one of the major firmware vendors is now inside a Chinese OEM with deepening Israeli ties (Part 9). This does not taint Phoenix's firmware *per se*; it is a corporate-structure note.
- **Embedded controllers:** ITE, ENE, Nuvoton (Taiwan) — clean.

---

## 9. Software: The Operating System Is the Heaviest Layer

### 9.1 Microsoft Windows — the deepest verified entanglement in this document

Microsoft's Israeli operation predates most: the company began operating in Israel in 1989, and its Israel R&D center (established 1991) was **Microsoft's first development center outside the United States**. Today Microsoft runs five Israeli sites (a 46,000-square-meter Herzliya campus housing both commercial and R&D functions, plus Haifa, Tel Aviv, Be'er Sheva, and Nazareth), thousands of employees, and a dedicated Israel Azure cloud region launched November 2023. Israeli acquisitions include Aorato (2014), Equivio (2015), Adallom (2015), Secure Islands (2015), Hexadite (2017), and Peer5.

The verified military-digital record, from the OpenIntel audit and the underlying Guardian/+972 Magazine/Local Call investigation:

- In late 2021, Unit 8200 commander Yossi Sariel met Microsoft CEO Satya Nadella at Microsoft headquarters regarding the migration of sensitive intelligence workloads to Azure.
- From 2022, **Unit 8200 operated a customized, segregated Azure environment storing, translating, transcribing, searching, and analyzing intercepted Palestinian phone calls from Gaza and the West Bank** — reportedly supporting intelligence used in planning operations, including target research and West Bank arrests. Microsoft engineers collaborated with Unit 8200 on the security measures needed to host the workloads.
- Microsoft initially said its leadership had not known intercepted civilian calls were being stored; in **September 2025, its own follow-up review "found evidence supporting elements of the reporting,"** and Microsoft ceased and disabled specified IMOD cloud-storage and AI subscriptions. The restriction was partial — other Microsoft–Israeli government and cybersecurity relationships continued, with audited contracts scheduled through 2026–2028.
- The commercial record alongside it: an approximately **$133 million, three-year Israeli Ministry of Defense agreement beginning 2021**; approximately **19,000 hours of Microsoft engineering support purchased by the IMOD between October 2023 and June 2024** (reported ~$10 million); a circa-2002 ~$35 million IMOD software/cybersecurity licensing agreement (partly financed through US Foreign Military Sales); Elbit Systems' OneSim military simulation infrastructure rebuilt on Azure with Microsoft engineering collaboration; Azure reportedly powering the Civil Administration's "Al Munaseq" permit-application system and Microsoft applications associated with the "Rolling Stone" population-and-movement system — both used in the administration of Palestinian movement; documented Microsoft services to Ariel University (occupied West Bank) into 2025, and a 2019 education partnership in Ma'ale Adumim settlement schools. An IAI tank prototype used retail Xbox controllers — off-the-shelf repurposing, not a defense product, but recorded in the audit for completeness.
- **AnyVision:** Microsoft's venture arm M12 invested $74 million in a 2019 round for Israeli facial-recognition company AnyVision; Microsoft divested in 2020 after an independent review said the evidence did not substantiate the alleged mass-surveillance program, and announced it would stop minority investments in facial-recognition companies.
- **Governance:** in December 2025, a shareholder proposal seeking a public report on human-rights due diligence received more than 26% support. Employee protests over the Israeli military contracts were followed by terminations Microsoft attributed to conduct and safety-rule violations; no labor-board finding against Microsoft resulted.
- **Audit verdict:** OpenIntel assigns Microsoft a BDS-1000 score of **711 — Tier B (Severe)** — with the maximum domain score in Digital (7.80), driven by the Azure/Unit 8200 record. BDS-movement literature accordingly describes Microsoft as "perhaps the most complicit tech company" in its category. The audit's exculpatory record is preserved here with the same weight as its inculpatory record: no evidence Microsoft manufactured weapons, built Israel's named targeting models ("Gospel," "Lavender," "Where's Daddy"), or collected the underlying intercepted data; the interception and analytical tooling are attributed to Israeli agencies operating on general-purpose Microsoft infrastructure.

### 9.2 Linux — mostly clean, with a sponsorship asterisk

The Linux kernel is community-authored, but development is employer-sponsored. The Linux Foundation's own reporting lists the top-10 sponsoring organizations as **Intel, Red Hat, Linaro, IBM, Samsung, SUSE, Google, AMD, Renesas, and Mellanox** — Mellanox being the Israeli company Nvidia acquired. So the kernel that would run on a "clean" laptop is partly funded by the exact companies this document flags. The code is open and inspectable; the sponsorship is real; both facts belong in the record. **Linux remains the cleanest practical OS layer by a wide margin.**

### 9.3 Browsers and applications

- **Firefox/Mozilla:** open source; no documented Israeli R&D or acquisition ties — the cleanest mainstream browser.
- **Chrome/Chromium:** Google operates large Israeli R&D (Google acquired Israeli companies including Waze; Project Nimbus — the Google/Amazon cloud contract with the Israeli government — is extensively documented separately).
- **macOS/Windows:** both covered above.

---

## 10. The OEM Layer: The Brand on the Lid

This is the layer most buyers actually see, and it is where corporate entanglement concentrates.

### 10.1 Dell — BRS 691, Tier B (Severe)

**Structure:** two Israeli legal entities (Dell Technology & Solutions Israel Ltd.; EMC Israel Advanced Information Technologies Ltd.), sites in Herzliya, Haifa, and Beersheba; cumulative Israeli M&A exceeding **$1 billion since 2006**.

**The acquisition ledger:**
- Kashya (2006) — data replication
- Cyota (2005, via RSA) — anti-fraud
- Exanet (2010) — storage
- **XtremIO ($430 million, May 2012)** — Herzliya flash-storage company founded by Israeli storage veterans including M-Systems co-founder Aryeh Mergi; EMC's sixth Israeli acquisition; EMC already ran a 700–800-person Israel R&D center including VMware staff
- **ScaleIO (~$200 million, June 2013)** — founded by Boaz Palgi, Erez Webman, Lior Bahat, Eran Borovik, and Erez Ungar; became Dell's PowerFlex storage platform ("Dell's PowerFlex software is built on technology developed by the Israeli company ScaleIO")
- VMware's Israeli stack during Dell ownership: B-hive, Wanova, Digital Fuel
- **Cloudify (January 2023, est. ~$100 million)** — orchestration
- Dell Technologies Capital's Israel portfolio includes VAST Data, Redis, Pecan, JFrog, GuardiCore, Elastifile, Descope, Entro, Iguazio, LightBits, LayerX, and Quantum Source

**Military procurement (verified reporting):** January 2023 — a two-year IMOD tender **reported above $150 million**, funded through US foreign aid, covering servers and maintenance for the Israeli military and security bodies; 2006 — tender for ~50,000 army computers (~$35 million); 2010 — EMC storage contract (~$300 million); VMware's NIS 100 million IMOD agreement (2016–2019, during Dell ownership); NIS 22.56 million in Israeli R&D incentives (2019–2024) tied to National Cyber Park activity in Beersheba, adjacent to an IDF technology campus; Dell mentored a 2018 military cyber hackathon attended by the IDF Computer and IT Directorate. Workforce cited at ~1,200 staff (circa 2019 figure, now dated).

**Political record:** Michael Dell's January 2024 social-media post alongside Israeli President Isaac Herzog ("an honor to stand with Isaac Herzog and Israel"); a **$1.8 million Friends of the IDF scholarship donation** by Michael and Susan Dell (2014). Michael Dell has separately been quoted in Israeli business press describing himself as "deeply committed to Israel."

**Audit verdict:** BDS-1000 score **691, Tier B (Severe)** — driven by the acquisition stack and the IMOD contract record.

### 10.2 HP — deep, current, and historical

**Structure:** HP Indigo — manufacturing in Kiryat Gat (an 11,000 m² ink plant) and R&D headquarters in Ness Ziona — employs roughly 2,400–3,000 workers and is cited at approximately **$1 billion in annual exports**. Indigo itself is Israeli-born: founded in Rehovot in 1977 by Benny Landa, acquired by HP for approximately $829 million in 2001; HP Scitex (also Israeli-origin) merged into Indigo in 2022/23.

**Military and security contracts:** HP has been the **exclusive PC provider to the Israeli military since 2009**, with the most recent such contract signed in 2014. Historical entanglements (largely discontinued by 2016–2017) include the "Basel" biometric checkpoint system and exclusive IDF PC/server contracts. **Critically for 2026: HPE holds renewed Israeli security-body contracts — Israel Police (through December 2026), Israel Prison Service (through February 2026), and the Population & Immigration Authority's "Aviv" population-registry system (through May 2028)** — with renewals occurring after the July 2024 ICJ advisory opinion and November 2024 ICC warrants. NGO sources (AFSC's Investigate database) list HP in the UN OHCHR settlement database; the audit notes the entry details are unverifiable due to database access restrictions.

**Acquisition history:** Mercury Interactive ($4.5 billion, 2006); NUR Macroprinters ($457 million, 2008).

### 10.3 Lenovo — rapidly deepening (2025–2026)

- **Infinidat:** acquisition announced January 16, 2025, **completed April 9, 2026**. Herzliya-based enterprise storage company founded in 2011 by storage pioneer Moshe Yanai; ~300 of its 500 staff are Israel-based; reported value above $500 million (market estimates ran to ~$1 billion). Infinidat operates as a business unit inside Lenovo's Infrastructure Solutions Group, with its Herzliya development center expanding — Lenovo's Israel GM stated the acquisition is expected to **double Infinidat's local sales and headcount**.
- **Security ecosystem:** a Cybersecurity Innovation Center with Ben-Gurion University (2023), evolving into a Tel Aviv Digital Trust Lab (February 2026) — located in the Gav-Yam Negev/CyberSpark ecosystem that co-locates IDF intelligence and technology units including Unit 8200. **SentinelOne — an Israeli-founded cybersecurity company — has its Singularity platform embedded in new Lenovo PC shipments via ThinkShield**, under an expanded multi-year collaboration.
- **Firmware:** Lenovo's acquisition of **Phoenix Technologies' BIOS unit closed 26 April 2026** (per TechCrunch/MassDevice deal reporting).
- **Corporate residue:** a registered "Lenovo (Israel) Ltd." entity; venture exposure via Lenovo Capital into Canaan Partners Israel and (2012) Vertex's Israel fund.
- **Not found:** any Lenovo military contract with Israel; Lenovo does not appear on BDS target lists. The trajectory, however, is unmistakably toward deeper entanglement — two Israel-linked acquisitions and an Israeli security-software embedding in consumer PCs, all within ~15 months.

### 10.4 ASUS and Acer — the cleanest major OEMs

Across all audit-grade sources, **no Israeli R&D centers, acquisitions, or subsidiaries were found for either ASUS or Acer.** Both operate under a general Taiwan–Israel R&D cooperation framework (signed 2015), but neither has planted Israeli operations. For a buyer applying any tie-based standard, this makes ASUS and Acer the default chassis choice — and notably, even BDS-adjacent consumer guides converge here: Ethical Consumer's 2024 laptop guide recommends Framework and TCO-certified ASUS (recommendations made on corporate-conduct grounds, which implicitly acknowledges the silicon layer this document documents).

---

## 11. The Meta-Layer: EDA Tooling, and Why Even "Clean" Chips Aren't

Before a chip exists as hardware, it exists as a design inside software. **Electronic Design Automation (EDA)** is the category of software used to design, simulate, verify, and lay out every modern integrated circuit — the CAD of the semiconductor world, but vastly more complex: a single chip can contain tens of billions of transistors, and no human team could place them by hand.

The EDA market is effectively a duopoly: **Synopsys and Cadence**, whose tools are used to design "virtually any" commercial chip. And both have Israeli development operations — Cadence lists Israel explicitly in its stated geographic footprint (its development center is in Netanya); Synopsys is Realtek's "primary EDA partner," with Realtek licensing Synopsys' Galaxy Implementation Platform and DesignWare IP. Synopsys' own Israeli presence (via acquisitions including Virage Logic) is documented in the public record, though this investigation cites it conservatively.

**Why this matters:** even the cleanest component choice in this entire document — a Taiwanese Realtek Wi-Fi chip with no Israeli employees, no Israeli subsidiary, no Israeli contract — is *designed using tooling that contains Israeli engineering*. This is the floor of the problem. A "zero ties in any way" standard, applied with total literalism, bottoms out here: there is no modern chip, from any country, designed without these tools. This finding does not negate the component-level distinctions elsewhere in the document — choosing AMD over Intel removes *Israeli-authored silicon*, which is categorically different from *shared tooling* — but it must be stated, because it defines the theoretical limit of what procurement can achieve.

---

## 12. Manufacturing: The Clean Layer

For completeness: the *physical production* of laptops is essentially Israel-free.

- **Assembly (ODMs):** Quanta, Compal, Wistron, Foxconn, Pegatron — Taiwanese/Chinese contract manufacturers. No Israeli ties.
- **Displays:** BOE (China), AUO and Innolux (Taiwan), LG (Korea). No documented Israeli ties.
- **Fabrication equipment:** ASML (Netherlands), Applied Materials, Lam Research, KLA (US), Tokyo Electron, Nikon, Canon, Advantest (Japan). No laptop's manufacture depends on Israeli equipment. (Applied and KLA do maintain Israeli *operations* — they "came because of Intel," per Calcalist's reporting on the Kiryat Gat ecosystem — but this is downstream service activity, not an equipment dependency.)
- **Fabs:** TSMC (Taiwan), Samsung (Korea), Intel (US/Israel — Kiryat Gat does fabricate Intel CPUs, which is Layer 1 authorship, distinct from equipment).
- **Tower Semiconductor** (Israel) is a specialty/analog foundry — not in the laptop supply chain.

The choke point of this entire investigation is **design authorship**, not tooling, not assembly, not materials. Chips are conceived in Israel; they are not (outside Intel's Kiryat Gat) generally *made* there.

---

## 13. The Minimum-Ties Build: The Practical Result

Putting every layer together, this is the closest a buyer can get to the stated criterion with a modern, usable, warranty-backed machine:

| Layer | Choice | Why | Residual taint |
|---|---|---|---|
| OEM / chassis | **ASUS or Acer** | No Israeli R&D, acquisitions, or subsidiaries found (audit-grade) | None found |
| CPU | **AMD Ryzen** | Zen architecture US-designed; no Israeli silicon authorship found | Corporate only: Ramat Gan R&D office, Xilinx Israel Ltd. (100% subsidiary), $50M Teramount co-investment |
| GPU | **AMD Radeon (integrated)** | ATI Canadian lineage; no Israeli design centers found | None found |
| Wi-Fi / Bluetooth | **Realtek** | In-house Taiwanese design | Indirect: ARM IP licensing; Synopsys EDA tooling |
| SSD | **Kioxia NAND + Phison controller, or SK Hynix** | Japanese/Korean/Taiwanese chain | None found |
| RAM | **SK Hynix** | Korean design and manufacture | None found |
| Charger / PMIC | **Intersil-Renesas, TI, or MPS** | US/Japan power ICs | None found |
| Webcam | **OmniVision sensor on the AMD USB path** | Clean sensor; on Intel it would feed an Israeli-designed IPU6 imaging processor | None found on this path |
| Fingerprint reader | **Goodix** | Chinese vendor, widely used | None found |
| Touchpad / audio | **Synaptics or Elan; Realtek codec** | Clean vendors | None found |
| BIOS / EC | **Insyde/AMI (or Phoenix, noting Lenovo ownership); ITE embedded controller** | Clean vendors; structural note that Phoenix is now Lenovo-owned | None found in firmware itself |
| OS | **Linux** | Community-authored; inspectable | Partial: kernel sponsorship top-10 includes Intel, Mellanox (Israeli→Nvidia), AMD, Samsung, Google |
| Browser | **Firefox** | Open source; no documented Israeli ties | None found |

**The irreducible floor — stated plainly, because honesty requires it:**

1. **AMD corporate ties.** Even the cleanest CPU vendor has an Israeli office, a wholly-owned Israeli subsidiary, and an Israeli venture stake. If "zero ties in any way" means zero corporate relationships, no x86 or ARM machine qualifies.
2. **EDA authorship.** Every chip in the machine was designed with Synopsys/Cadence tools containing Israeli engineering (Part 11).
3. **Linux sponsorship.** Partial funding taint at the kernel-sponsor level.
4. **The people layer.** ~1,400 Israeli intelligence-unit veterans work across US tech (MintPress/Drop Site mapping), concentrated in exactly the firms that design chips and OSes. No purchase decision touches this layer.

That is the honest floor of a mainstream machine. It is dramatically cleaner than an Intel/HP/Windows laptop — it removes Israeli *silicon authorship* entirely — but it is not, and cannot honestly be called, zero.

---

## 14. The Literal Zero-Tie Paths

Three paths satisfy the criterion as literally as the physical market allows. Each carries real tradeoffs that must be stated with the same honesty as the entanglement findings.

### 14.1 Loongson / LoongArch (China)

**What it is:** the Chinese domestic CPU program (its current mainstream laptop/desktop processor is the 3A6000). Loongson processors use the LoongArch instruction set architecture — a fully Chinese-designed ISA (the fundamental language a CPU speaks), not x86 and not ARM. Complete laptops — current desktop-class models include the 3A6000 — ship with Chinese domestic operating systems (Loongnix, UOS, or Kylin).

**Why it qualifies:** at the CPU level, this is the only literal zero-Israeli-R&D path found in the entire investigation. No Israeli design involvement, no Israeli subsidiary, no Israeli venture relationship. Fabrication runs through TSMC or SMIC; SMIC's fabs run on ASML tooling (Netherlands) — and per Part 11, even this bottoms out at the EDA layer unless the Chinese toolchain (which exists in domestic form) was used end-to-end.

**The tradeoffs, stated without exaggeration:** performance and compatibility well behind x86/ARM (x86 software requires translation layers); the Chinese-state trust question inverts the original criterion for many buyers (a machine with zero Israeli ties that is, by design, transparent to a different state); and ecosystem immaturity (driver support, peripheral compatibility).

### 14.2 RISC-V open-hardware laptops

**What it is:** RISC-V is an open-source instruction set — free to implement, no license fees, no ARM. As of 2026, fully functional RISC-V laptops exist: the Framework 13 with a RISC-V mainboard, and the DC-ROMA II (DeepComputing), built around the 8-core ESWIN EIC7700 (P550) SoC — a Chinese-designed RISC-V chip.

**Why it qualifies:** no Israeli design involvement in the ISA or the ESWIN silicon; no ARM IP; no Israeli corporate presence in the vendor chain.

**The tradeoffs:** performance far below x86/ARM contemporaries; an immature software ecosystem; small vendors with limited warranty infrastructure. This is a real, purchasable category — not a concept — but it is early-adopter territory.

### 14.3 Vintage (pre-1979)

Machines predating the Israeli-designed 8088 (i.e., pre-IBM-PC) avoid the Intel Israel lineage — but a 1978-era computer is a museum piece, not a tool. It is listed for completeness, not as a recommendation.

---

## 15. The People Layer: What No Spec Sheet Can Exclude

One finding deserves its own section because it reframes the entire question: the *talent pipeline*. Unit 8200 is the IDF's signals-intelligence unit — Israel's equivalent of the NSA's most elite operations, combined with a national talent academy that selects teenagers out of high school, trains them intensively, and releases them into industry. The MintPress/Drop Site News mapping identified approximately **1,400 veterans of Israeli intelligence agencies across US technology companies** — with concentrations at exactly the firms that author laptop silicon and software: Apple, Intel, Microsoft, Google, Amazon, Nvidia, Meta.

Johny Srouji himself is a product of this pipeline-adjacent ecosystem (Technion → IBM Haifa → Intel Israel → Intel Austin → Apple), and the pattern repeats at every company in this document: the Israeli design centers are staffed substantially by veterans of Israeli military technology units. This is not an accusation of anything illegal — it is a structural description of how the industry actually works, confirmed by the companies' own executives ("If you're looking for engineering talent, Israel is the place," Srouji says, on the record).

**Implication:** a "zero ties" laptop criterion can be applied to components, corporations, contracts, and tooling. It cannot be applied to the biography of every engineer who touched the supply chain — and any framework that pretends otherwise is not evidence-based. This document therefore treats the people layer as context that sharpens the other findings, not as a purchasing criterion.

---

## 16. Methodology and Evidence Grading

**How this investigation was conducted.** Four sequential research passes: (1) breadth mapping of all supply-chain layers; (2) targeted gap-closure on memory, power, OEMs, and firmware; (3) full consolidation; (4) primary-source deep reading — full articles and audit dossiers rather than search snippets. Sources include named-executive interviews (Srouji/Ynet), Israeli business press (Calcalist, Globes, CTech), SEC filings (Mobileye 10-K, AMD subsidiary schedules), company press releases (Lenovo/Infinidat), forensic corporate audits (OpenIntel's BDS-1000 assessments of Intel, Microsoft, and Dell, cited with their methodology and their exculpatory findings), NGO databases (AFSC Investigate, Who Profits), and hardware-teardown reporting.

**Evidence grades used implicitly throughout:**
- **Audit-grade:** documented in a forensic dossier with named sources and explicit "not found" statements (OpenIntel entries).
- **Filing-grade:** corporate disclosure (SEC, subsidiary schedules).
- **On-record:** named executive or company statement.
- **Reported:** quality press, single or convergent sourcing.
- **Unresolved:** flagged where evidence is thin, dated, or contested.

**Caveats the record requires:**
- "No public evidence identified" (the audits' formulation) records the result of specified public-source checks; it does not prove non-public activity impossible. This applies symmetrically — to Intel's lack of a direct IMOD contract and to AMD's lack of military ties alike.
- Some figures are dated cumulative measures (e.g., Intel's $86B cumulative exports through 2023; Dell's ~1,200 Israel staff circa 2019) and are labeled as such.
- BDS-1000 scores (Intel 712, Microsoft 711, Dell 691 — all Tier B "Severe") are one framework's human-vetted output, reproduced here as evidence of *documented activity*, not as endorsements of the framework's politics. The underlying documented facts stand independently of the scoring.
- This document adopts no theory of anyone's intent. It gathers clues and evidence: who designs what, who owns whom, who contracts with whom, and what remains unproven.

---

## 17. What Remains Unresolved

Stated for completeness, in descending order of significance:

1. **Intel ME/AMT firmware authorship at team level.** Whether Haifa teams specifically developed ME or AMT firmware is internal and likely unresolvable from open sources. Moot in practice — every ME runs on Israeli-designed silicon anyway.
2. **Micron's Israel ASIC team scope.** Active hiring is confirmed; whether its output ships in consumer products or enterprise-only is unresolved.
3. **Synopsys Israel specifics.** Cadence's Israel footprint is confirmed; Synopsys' Israeli R&D is documented in the public record but this investigation cites it conservatively (no site-level detail).
4. **MediaTek's direct footprint.** None found; its indirect taint (ARM IP, Synopsys tooling) is quantified and that is the honest statement.
5. **BDS-framework blind spots.** Scoring frameworks optimize for their own criteria; a company can score low while having meaningful ties, or high while lacking direct military contracts. The scores are used here as documentary summaries, not oracles.

---

## 18. Key Figures at a Glance

| Figure | Value | Context |
|---|---|---|
| Intel Israel workforce | ~9,335 (Intel) / ~11,700 (Calcalist 2024) | ~10% of Intel's global staff |
| Intel cumulative exports from Israel | $86 billion (through 2023) | ~6% of Israeli high-tech exports in 2022 |
| Intel Israel share of Israeli GDP (2022) | ~2% | Largest private employer in Israel |
| Fab 38 expansion | $25B announced; $3.2–3.25B state grant; NIS 60B local procurement pledge | Construction halted June 2024 |
| Intel acquisitions in Israel | Mobileye $15.3B (2017, 96.9% voting control), Habana ~$2B (2019), Moovit, Granulate ~$650M | Tower $5.4B deal blocked by China (2023) |
| Intel BDS-1000 score | 712 — Tier B (Severe) | OpenIntel V6.5 audit |
| Microsoft BDS-1000 score | 711 — Tier B (Severe) | Driven by Digital domain (7.80) |
| Microsoft–IMOD agreement | ~$133M, three years, from 2021 | Plus ~19,000 engineering hours Oct 2023–Jun 2024 |
| Dell BDS-1000 score | 691 — Tier B (Severe) | Israeli M&A >$1B since 2006 |
| Dell–IMOD tender | >$150M, two years, January 2023 | US foreign-aid funded |
| HP Israel workforce (Indigo) | ~2,400–3,000; ~$1B annual exports | Exclusive IDF PC supplier since 2009 |
| Lenovo–Infinidat | >$500M (est. to ~$1B), completed April 2026 | ~300 of 500 staff Israel-based |
| Apple Herzliya center | Opened 2012; 1,800 staff by 2022 | Every Apple storage controller Israeli-built |
| AMD Israeli ties | R&D office, 100%-owned Xilinx Israel Ltd., $50M Teramount co-investment | No Israeli silicon authorship found |
| Unit 8200 alumni in US tech | ~1,400 (MintPress/Drop Site mapping) | People layer; not purchasable |
| Linux kernel top-10 sponsors | Includes Intel, Mellanox (Israeli→Nvidia), AMD, Samsung, Google | Sponsorship taint, not code authorship |

---

## 19. Glossary

- **ISA (Instruction Set Architecture):** the fundamental language a CPU speaks — the set of operations it can execute. x86 (Intel/AMD), ARM, LoongArch, and RISC-V are ISAs. Software must be translated or rewritten to move between them.
- **SoC (System on Chip):** a single chip integrating CPU, GPU, memory controllers, and I/O. Apple's M-series chips are SoCs.
- **Fabless:** a chip company that designs but does not manufacture (Realtek, Qualcomm, Nvidia). Manufacturing is outsourced to fabs.
- **ODM (Original Design Manufacturer):** the contract manufacturers that actually build laptops (Quanta, Compal) — usually invisible to buyers behind the brand.
- **EDA (Electronic Design Automation):** the software used to design chips. Synopsys and Cadence dominate.
- **IP (Intellectual Property) cores / IPU:** licensed chip-design building blocks (ARM sells CPU cores); IPU here also means Intel's Image Processing Unit (IPU6), a camera-interface chip.
- **BIOS/UEFI & EC (Embedded Controller):** firmware that runs before the OS (BIOS/UEFI) and the microcontroller managing keyboards, fans, and power (EC).
- **ME / PSP:** Intel Management Engine / AMD Platform Security Processor — closed subsystems running below the OS with full hardware access.
- **PMIC:** Power Management Integrated Circuit — the chip(s) governing charging and power distribution.
- **Retimer:** a signal-conditioning chip for high-speed interfaces (PCIe, USB4); Astera Labs' product.
- **Unit 8200:** the IDF's signals-intelligence unit; primary feeder of Israeli tech talent to global industry.
- **IMOD:** Israel Ministry of Defense.
- **BDS / BDS-1000:** the Boycott, Divestment, Sanctions movement, and OpenIntel's audited 1,000-point complicity-scoring methodology (Tier B = "Severe").
- **Tier B (Severe Complicity):** OpenIntel's second-highest complicity band. Intel 712; Microsoft 711; Dell 691.
- **Tape-out:** the moment a chip design is finalized and sent for manufacturing — the "plans handed to the construction crew" stage.
- **Data center:** a warehouse of computers that rents computing power over the internet; Microsoft's Azure and its Israeli region are examples.
- **Transistor:** the microscopic on/off switch that is the basic building block of all chips; modern processors contain tens of billions of them.

---

## 20. The Conclusion, in One Paragraph

A laptop with zero ties to Israel cannot be bought — not because of one component, but because Israeli engineering sits inside the design of the world's dominant CPU architectures, the tools used to design every chip, the acquisition stacks of three of the four biggest PC brands, the cloud contracts of the dominant operating-system vendor, and the talent pipeline of the entire industry. The closest a buyer can honestly get is an ASUS or Acer machine with an AMD processor, Realtek connectivity, Korean or Japanese memory and storage, an OmniVision camera on the USB path, and Linux with Firefox — a configuration that eliminates Israeli *silicon authorship* entirely while retaining small, documented, corporate-level ties that no consumer choice can remove. The only literal zero-tie machines are Chinese Loongson systems and early RISC-V systems, each carrying tradeoffs that must be weighed against the criterion itself. That is the complete, evidence-backed answer — every layer audited, every stone listed, nothing adopted from anyone's theory, and every unresolved item marked as unresolved.

---

*Compiled 2026-09-20. Four research passes; primary sources opened in full. All monetary figures as reported by the cited sources; dated figures labeled. "No public evidence identified" statements are preserved from the underlying audits and mean exactly what they say.*
