# The Zero-Ties App: A Complete Audit of Israeli Entanglement in the Cell Phone App Ecosystem

αΩ∞

*A fully-sourced investigation into the apps on a cell phone — messaging, payments, productivity, AI, VPNs, creative tools, games, and the invisible advertising infrastructure beneath them — and which can pass a zero-ties-to-Israel criterion, as of September 2026.*

---

## 1. The Question

The device investigations established that no phone and no laptop can be bought with zero ties to Israel. But a phone is also a container of apps — and apps are different from hardware in one crucial way: **they are individually choosable.** You cannot choose your Snapdragon chip away, but you can delete an app and install a different one in ninety seconds.

So the question sharpens: **among the apps a phone user actually touches — messaging, social, payments, maps, music, work, security, AI — which are entangled with Israel, at what depth, and what are the clean substitutes?** And beneath the apps themselves lies a second question most users never think to ask: what invisible code is embedded *inside* the apps other people wrote?

### How to read this document

- **Part 2** gives the short answer.
- **Part 3** explains the three axes of an app audit — the framework everything below uses.
- **Parts 4–11** walk the app categories one by one: messaging and social, payments and finance, productivity, AI, VPN and security, navigation and travel, creative tools and education, and streaming.
- **Part 12** is the invisible infrastructure layer — the advertising and analytics code embedded inside apps, where three of the finding pillars live.
- **Part 13** is the consolidated Israeli-app catalog.
- **Part 14** is the clean column — the substitution table.
- **Parts 15–18** cover method, open questions, key figures, and a glossary.
- **Part 19** is the conclusion.

The framing note from both previous reports applies unchanged: this document argues no political position. The user's criterion is a supply-chain standard — zero ties to Israel — and the market is measured against it. Where involvement is found it is documented with sources; where it is not found, that is documented too; where evidence is thin, the ambiguity is preserved.

---

### A thirty-second orientation for readers new to how apps are built

When you tap an app, you are running code written by that app's company — but rarely *only* by that company. Modern apps are assembled like a meal from ingredients: the developer writes the core, then bolts in **SDKs** (software development kits) — pre-built code for analytics, advertising, crash reporting, payments, maps. A single weather app can contain a dozen companies' code, most of them invisible to you. This matters because it means an app audit has three separate questions: **who made the app** (the company axis), **what is bolted inside it** (the infrastructure axis), and **what it shows you** (the content axis). A clean company can ship an app containing an entangled SDK; an entangled company can stream clean content. All three axes are audited separately below.

---

## 2. The Short Answer

**Most of the app categories a phone user touches daily are led — at company level, infrastructure level, or both — by Israeli-authored software; the clean substitutes exist but are consistently second-tier in market share.** The deepest findings, in plain terms:

1. **Some of the apps themselves are Israeli companies.** Viber (~a billion users, built from Tel Aviv), eToro (an Israeli-headquartered brokerage, NASDAQ-listed), the Lightricks editing suite (Facetune, Photoleap, Videoleap — built in Jerusalem), the Waze/Via navigation pair, and a remarkable share of the world's top-grossing mobile games (Playtika, Moon Active's Coin Master, Plarium's RAID).

2. **The "privacy" category is owned by the wrong people.** ExpressVPN, CyberGhost, Private Internet Access, and ZenMate — four of the most recommended VPN apps on Earth — are all owned by **Kape Technologies**, a British-Israeli company wholly owned by Israeli billionaire Teddy Sagi, founded by a Unit 8200 veteran, whose review-site arm (vpnMentor, Wizcase) recommends its own products. The tools people download to escape tracking are, at ownership level, tracked to the same place as everything else.

3. **The advertising infrastructure underneath everything is a three-pillar Israeli layer.** **AppsFlyer** (Israeli-founded; its attribution SDK sits inside roughly half of all Android apps), **ironSource** (Israeli, merged into Unity — the monetization stack inside free games), and **Taboola/Outbrain** (both Israeli-founded; their merger, completed in 2024, left one company running recommendation modules across 20,000 publisher properties reaching a claimed 2.6 billion people — including the news apps on your phone). No consumer choice removes an SDK from an app someone else wrote.

4. **The payment rails are deeply tied.** PayPal and Venmo's fraud-detection and security systems are built in Israel (three acquisitions: Fraud Sciences, CyActive, Cymbio); Coinbase's wallet cryptography is Israeli-authored (the Unbound Security acquisition); the card networks behind Apple Pay and Google Pay (Visa, Mastercard, Citi) all run Israeli R&D centers.

5. **The clean column is real but narrower:** Signal and Telegram (messaging), the Match Group dating portfolio (Tinder, Hinge — a fully clean acquisition ledger), Proton and Mullvad (VPN), Duolingo and Canva and Notion (education/design/notes), X, Robinhood, Binance, Zelle (finance), and — notably — **OpenAI, which has deliberately declined to open an Israeli office** (Globes, July 2026: it manages Israel operations "from abroad"), though its reported talks to acquire Israeli-founded Decart could change that.

---

## 3. The Three Axes of an App Audit

**Axis one — the company.** Is the app maker itself Israeli-founded, Israeli-headquartered, or operating an Israeli R&D center that writes the app's code? This is the strongest tie: the code is the product.

**Axis two — the infrastructure inside.** Acquisitions and SDKs that place Israeli-authored components in the app's data path. The AppsFlyer attribution SDK (48.51 percent of Android installs per its own 2024 industry data) is the canonical case: the app belongs to someone else, but Israeli code inside it tracks the install.

**Axis three — the content.** What the app streams or hosts. Content is a consumption fact, not a code fact: Netflix's Israeli connection is content-level (Fauda, Tehran, Shtisel, backing for the Sam Spiegel Series Lab) with no Israeli engineering office found — the exact opposite of Spotify, whose Tel Aviv office of roughly 300 staff builds recommendation systems. Same "tie" word, entirely different mechanisms, and the distinction is maintained throughout.

---

## 4. Messaging and Social

- **Viber — Israeli app.** Founded in Tel Aviv in 2010 by Talmon Marco (former IDF Central Command chief information officer) and Igor Magazinnik; core functionality developed from the Tel Aviv office; Rakuten acquired it for **$900 million in 2014**; half its employees are in Israel; 950 million to 1.2 billion registered users. A billion-person messaging network that is Israeli-authored at the core.
- **Meta (Facebook, Instagram, WhatsApp, Messenger) — deep R&D tie.** The Tel Aviv R&D center works on core advertising and AI systems for Facebook and Instagram (per Meta's own descriptions, recently in the news for layoffs of roughly 5 percent). These apps ship preinstalled or near-mandatory on virtually every Android phone, so the ads-ranking and AI inference monetizing them includes Israeli-authored engineering regardless of device.
- **Snapchat — corporate tie.** Herzliya R&D center built on the **Cimagine** (augmented reality) and **Voca.ai** acquisitions (about $70 million, November 2020); sites in Tel Aviv and Kfar Yehoshua.
- **Reddit — acquisition tie.** Acquired **Spell**, an Israeli natural-language-processing startup, in 2024 — its first acquisition — followed by AI ad-tech purchases.
- **X — no Israeli ties found.** Zero results across dedicated searches; recorded no-evidence-found.
- **Tencent / WeChat — light, audited.** OpenIntel's audit: no office or subsidiary; but **GateHub, a Tel Aviv firm, is Tencent Cloud's first strategic partner in Israel**, marketing Tencent Cloud, WeChat Pay, and facial-recognition products; Tencent's venture record in Israel includes Phytech ($11 million round, 2017), Future Crops (2022; bankrupt 2023), and ONE ZERO Digital Bank ($120 million round, December 2021). The audit's own verdict: "no public evidence identified" of any Israeli state or military contract.
- **TikTok (ByteDance) — no ties found, at consumer-guide grade** (no audit dossier exists for ByteDance).
- **Match Group (Tinder, Hinge, OkCupid, PlentyOfFish) — clean ledger, the dating category.** The full acquisition record contains nothing Israeli: Match.com itself (1999, ~$50 million, via IAC), OkCupid (2011, ~$50 million), PlentyOfFish (2015, $575 million), Hinge (majority 2017, remainder 2019), and Hyperconnect (2021, $1.73 billion — Korean, maker of Azar and Hakuna). Tinder was incubated inside IAC's Hatch Labs, not acquired. No Israeli R&D center, acquisition, or office surfaced across dedicated searches — the cleanest major app category identified. (Bumble, the remaining major dating app, is unresolved — see Part 16.)
- **Signal, Telegram, LINE — clean.** Signal is US-based; Telegram is Dubai-based; LINE is Japanese-Korean. No Israeli operations found in any pass.

---

## 5. Payments, Commerce, and Finance

- **PayPal and Venmo — the deepest fintech tie.** PayPal acquired **Fraud Sciences for $169 million in January 2008** — founded by Shvat Shaked and Saar Wilf, both intelligence veterans; the deal seeded PayPal's Israeli operation — then **CyActive of Beersheba for about $60 million in March 2015** (founders from military intelligence; opened a second development center), and **Cymbio in May 2026**, with PayPal Israel now described as a "strategic technology hub" for agentic commerce, including Microsoft Copilot and Perplexity integrations. The fraud-detection, cybersecurity, and AI risk systems that score **every PayPal and Venmo transaction** are Israeli-authored, built by an Israel R&D operation of roughly 200-plus engineers.
- **eBay — five Israeli acquisitions.** Shopping.com ($620 million, 2005); The Gifts Project (~$30 million, 2011 — became eBay's Israeli development center); SalesPredict (~$40 million, 2016); plus Fraud Sciences via PayPal and CyActive via PayPal.
- **eToro — the app itself is an Israeli company.** Headquartered in Bnei Brak (its principal executive offices are at 30 Sheshet Hayamim Street per its own SEC filings); incorporated in the British Virgin Islands; NASDAQ: ETOR since May 14, 2025 (an IPO raising roughly $620 million at a ~$4.2–4.3 billion valuation); founded 2007 by Yoni and Ronen Assia and David Ring; about 1,520 employees; 3.81 million funded accounts across 75 countries, with about $18.5 billion in assets under administration and roughly 1,520 employees. A user's brokerage, order routing, and crypto custody run on an Israeli-headquartered platform.
- **Coinbase — Israeli-authored wallet cryptography.** Acquired **Unbound Security** in November 2021 (Petah Tikva; founded 2015 by cryptographers Yehuda Lindell, Nigel Smart, and Guy Peer; reported at up to $150 million) and announced a "tech center of excellence in Israel." The multi-party-computation technology securing Coinbase's keys is Israeli-authored.
- **The card rails:** Visa, Mastercard, and Citi all operate Israeli R&D centers — so the card networks underneath Apple Pay and Google Pay carry an engineering-level tie regardless of phone choice.
- **Robinhood, Binance — no Israeli corporate ties surfaced.** Recorded alongside a symmetry note to prevent confusion: Binance is *sued by* October 7 victims' families over alleged laundering for Hamas — entanglement with Israel's adversaries, a different axis entirely.
- **Zelle (the bank consortium) — no ties found**; cash remains the only fully clean payment rail.

---

## 6. Productivity and Work

- **Slack / Salesforce — a major and current tie.** Salesforce entered Israel in 2011 (Navajo Systems) and now runs roughly **900 employees across three R&D centers** (Tel Aviv, Nazareth). Its Israeli acquisition ledger: BlueTail, Kernesen, Implisit, Datorama, Bonobo, ClickSoftware, **Zoomin and Own ($1.9 billion, 2024)**, and **Doti (~$100 million, November 2025)** — whose team "will join Salesforce's AI R&D hub in Israel," with Doti's founders leading the Israeli branch of Slack. Slack's agentic search and AI features are being written in Israel.
- **Microsoft 365 and Google Workspace** — the parent-company dossiers from the laptop and phone reports apply in full (Microsoft BRS 711, the Unit 8200 cloud; Google Nimbus and Israeli chip teams).
- **Zoom Video — no Israeli R&D surfaced**, with one critical naming warning: **do not confuse it with ZoomInfo**, the business-data company whose global R&D is centered in Ra'anana with 400-plus Israel employees. Search results conflate them constantly; the distinction is preserved here.
- **Yahoo apps:** Yahoo's Israeli R&D (ClarityRay, Dapper, RayV) persists under Apollo ownership.
- **Notion, Basecamp — no Israeli ties found** (no-evidence grade). FOSS alternatives (CryptPad, Nextcloud) are structurally cleaner still.
- **The continuing B2B pattern — Zendesk→Unleash.** December 2025: Zendesk acquired **Unleash**, an Israeli AI enterprise-search startup, for its agent products. Not a consumer phone app, but recorded here because it exemplifies the mechanism by which ties enter the app economy quietly: one startup acquisition at a time, the acquired team's code becoming the parent product's core (the same mechanism as Salesforce/Own and Salesforce/Doti above, and Reddit/Spell in Part 4).

---

## 7. The AI Apps

- **ChatGPT (OpenAI) — no Israeli office, deliberately.** Globes (July 2026): "OpenAI to manage Israel operations from abroad." But OpenAI is reported to be in talks to acquire **Decart** — Israeli-founded, Tel Aviv-based, about 89 of its 106 staff in Israel, previously valued near $4 billion — at a reported **$6 billion** valuation. If completed, an engineering-level tie; at compilation time, talks only. Also of record: **Irregular**, a Tel Aviv AI-security testbed company ($450 million valuation; Sequoia and Redpoint-backed), was the named host in the August 2026 "rogue AI" security-testing episode involving OpenAI, Anthropic, and Meta — an adversarial-testing relationship, not ownership, and flagged as such.
- **Claude (Anthropic) — no Israeli development center** (a representative sits in Ireland). Two recorded ties: its **Palantir partnership** (Palantir operates an Israeli R&D center and holds Israeli military contracts), and an **Intercept report (October 2025)** that **Rafael — the Israeli arms prime — obtained Claude via Amazon Web Services and specifically sought to test it**, despite Anthropic's acceptable-use policy barring weapons development. How that squares remains unresolved.
- **Gemini (Google) and Copilot (Microsoft)** — the parent dossiers apply.

---

## 8. The VPN and Security Category — the Defining Finding

**Kape Technologies** is the story of the category. The company is British-Israeli, formerly **Crossrider** — an ad-injection platform that Malwarebytes classified as malware — founded in 2011 by Shmueli Achdut and **Koby Menachemi, a Unit 8200 veteran**. Teddy Sagi bought it in 2012 for $37 million; it listed on London's AIM at a $250 million valuation; it rebranded Kape in 2018; Sagi took it fully private in June 2023 (it is now wholly owned by his Unikmind vehicle), followed by roughly 180 layoffs. Its portfolio:

- **ExpressVPN — acquired for $936 million in 2021** · **CyberGhost — €9.1 million, 2017** · **Private Internet Access — $127.5 million, 2019** · **ZenMate — €4.8 million, 2018** (merged into CyberGhost, 2023) · **Intego antivirus**.
- **Webselenese — the review-site arm:** owner of **vpnMentor and Wizcase**, two of the largest VPN-review sites on the internet, which rank its owner's products for the users trying to research them.
- Development center in Tel Aviv's Azrieli Sarona Tower; CEO Ido Erlichman is a Duvdevan veteran. Sagi's own record: a 1996 fraud conviction (roughly nine months served), a ~$3 million Friends of the IDF scholarship donation (2019), a 1-million-shekel soldier-transport donation (2023), Panama Papers appearances, ~$6.4 billion net worth.

**The honest counterweight, stated because the record requires it:** VPN-industry reporting — including competitors with an interest, flagged as such — notes that **no evidence of misuse has surfaced**; ExpressVPN runs RAM-only servers and has commissioned audits. The documented facts are the ownership chain and the review-site circularity; wrongdoing is not claimed, only the chain. Buyers who find the chain disqualifying under the criterion have a clean, well-audited set: **Proton (Swiss), Mullvad (Swedish), IVPN (Gibraltar), and Nord Security's NordVPN/Surfshark (Lithuanian — which also owns Saily, the clean travel-eSIM from the phone investigation).** **HolaVPN**, the other famous Israeli VPN, is Israeli-founded with its own bandwidth-reselling history — avoid under this criterion.

---

## 9. Navigation, Travel, and Food

- **Waze — Israeli, Google-owned** (covered in the phone report).
- **Via — Israeli-founded, filing-grade:** two wholly-owned Israeli subsidiaries and 250-plus Israel staff, per its own SEC filing.
- **Uber — resolved this investigation:** an OpenIntel dossier identifies an R&D/engineering footprint in Israel, and in June 2026 Uber partnered with Israeli **Autobrains** (Tel Aviv; 300-plus patents) and Nvidia on its Munich robotaxi program. Corporate tie confirmed; no Israeli-authored app core asserted.
- **Booking.com — Tel Aviv AI Innovation Center** (documented since 2017).
- **Google Maps and Apple Maps** — parent dossiers.
- **Lyft — no Israeli ties found.** DoorDash and Instacart — none surfaced (unverified grade).
- **The clean navigation option:** **Organic Maps** and other OpenStreetMap-based free-software apps.

---

## 10. Creative Tools and Education

- **Lightricks — the editing category's crown is Israeli, fully confirmed.** Jerusalem-based, founded 2013 by Hebrew University postdoctoral researchers in computer graphics — Zeev Farbman, Nir Pochter, Yaron Inger, Amit Goldstein; founder profiles record Unit 8200 service. **Facetune** was Apple's #1 best-selling paid app of 2013, topping charts in 120-plus countries; the suite (Photoleap, Videoleap, Motionleap, the LTX Studio AI-filmmaking platform, Popular Pays) has passed 500–730 million downloads with multiple millions of paying subscribers; $335 million raised, including a **$130 million Series D at a $1.8 billion valuation (2021)** led by Insight Partners; Getty Images and Shutterstock training partnerships (December 2024); the 2024–2026 generative-AI pivot came with repeated layoffs (70 in 2024, 85 earlier, 75 more in June 2026) and a split of the profitable consumer apps from the costly LTX AI-video division. The alternatives are Adobe (US), Canva (Australian), and CapCut (ByteDance) — both clean at no-evidence grade.
- **Duolingo — clean.** Its first acquisition was Gunner, a US design agency (2022); no Israeli ties found. The adjacent fact: **Loora**, an Israeli AI English-learning app founded by two former IDF commandos (Roy Mor and Yonatan Levin), serves 15 million users and competes directly with Duolingo — Israeli-founded entrants define the category's frontier even where incumbents are clean.

---

## 11. Streaming and Content

- **Netflix — content-level tie only.** Fauda, Tehran, Shtisel, and backing for the Sam Spiegel Series Lab (2022); no Israeli engineering office found. The cleanest major streaming service on the engineering axis.
- **Spotify — engineering-level tie:** the Tel Aviv R&D office (roughly 300 staff) builds recommendation and AI systems.
- **YouTube and Twitch** — parent dossiers (Google; Amazon, whose Annapurna Labs chip division is Israeli-founded and which co-holds Project Nimbus).
- **Music alternative at no-evidence grade:** Bandcamp and local files; Apple Music inherits its parent's dossier.

---

## 12. The Invisible Infrastructure Layer — Where Three Pillars Live

Beneath every category above sits the layer the user never chooses: SDKs embedded in other people's apps, and the ad systems that monetize the free tier of the mobile world. Three pillars, all Israeli-founded, dominate it.

- **AppsFlyer — attribution.** Founded 2011; CEO Oren Kaniel; headquartered in effect "San Francisco, Israel"; **about $500 million ARR as of January 2026 and profitable since 2024**; the dominant mobile-attribution SDK — per its own industry data leading Android with **48.51 percent of all installs** (third-party trackers put its share near 44 percent, ahead of Germany's Adjust at ~27 percent and the US Branch at ~22 percent). Its Series C ($56 million) was led by Israeli VCs **Qumra and Pitango** alongside Goldman Sachs and Deutsche Telekom Capital Partners. The SDK inside roughly half of Android apps reports installs, ad sources, and in-app events to an Israeli-founded analytics company. No consumer setting removes an SDK from an app someone else wrote; the mitigations are app selection (F-Droid's free-software catalog largely lacks it) and network-level blocking of its endpoints (imperfect).
- **ironSource — monetization.** Israeli; merged into **Unity** in a deal reported around $4.4 billion; the mediation and monetization stack inside a large share of free mobile games (reported-deal grade, flagged for filing-grade confirmation). Together with AppsFlyer it means the free-app economy's two money pipes are Israeli-authored.
- **Taboola/Outbrain — content recommendation.** The sponsored-content modules at the bottom of articles across the mobile web and news apps — the "around the web" boxes — are an Israeli duopoly that became a monopoly: **Taboola** (founded Tel Aviv 2007 by Adam Singolda; NASDAQ: TBLA; investors including Pitango, Baidu, Fidelity, Comcast Ventures, DailyMail, and Groupe Arnault; $632 million revenue in H1 2021 alone, roughly a fifth of it from Microsoft) and **Outbrain** (founded 2006 by Israelis Yaron Galai and Ori Lahav; backed by Carmel, Gemini Israel, GlenRock Israel, Rhodium, Index, and Lightspeed). The two announced an $850 million merger in 2019; after years of negotiation it **closed in mid-2024**, leaving one Israeli-founded company running recommendation modules across **20,000 publisher properties with a claimed audience of 2.6 billion people** — customers include CNN, the BBC, The Washington Post, USA Today, The Guardian, Sky News, and MSN. Every ad-funded news app monetizes through it.

**Why this layer matters most:** the company axis can be dodged by app choice; the content axis by taste; but the infrastructure axis attaches to apps the user merely *uses* — a bank app, a airline app, a local newspaper app — and it follows them regardless of every other choice they make.

---

## 13. The Consolidated Israeli-App Catalog

Across all passes, the apps a phone user can hold that are **Israeli-authored at the core**:

| Category | Israeli app / company |
|---|---|
| Messaging | **Viber** (Rakuten-owned; ~1 billion users; Tel Aviv-built) |
| Navigation | **Waze** (Google-owned) |
| Transit | **Via** (SEC: two wholly-owned Israeli subsidiaries, 250+ staff) |
| Brokerage | **eToro** (HQ Bnei Brak; NASDAQ: ETOR) |
| Photo/video editing | **Lightricks suite** (Facetune, Photoleap, Videoleap, LTX Studio; Jerusalem; $1.8B valuation) |
| Mobile games | **Playtika** (NASDAQ: PLTK), **Moon Active** (Coin Master, $6B+ lifetime), **Plarium** (RAID, ~$1B), plus Reworks ($400M, via Playtika) and Beach Bum (via Voodoo) |
| Education | **Loora** (AI English learning; 15M users) |
| Attribution SDK | **AppsFlyer** (~half of Android installs) |
| Ad monetization | **ironSource** (merged into Unity) |
| Content recommendation | **Taboola + Outbrain** (merged 2024; 2.6B-reach) |
| VPN (ownership) | Crossrider→**Kape** (ExpressVPN, CyberGhost, PIA, ZenMate, vpnMentor) |
| App-adjacent SaaS | **Fiverr, Monday.com, Wix** (and Payoneer) — Israeli companies used through their phone apps |

The catalog's breadth is itself the finding: **from the phone's photo filters to the ads under its news to the VPN protecting it, each category's leading independent traces to Israel.** The counter-catalog is real but consistently second-tier in market share, category by category. (Fiverr, Wix, MyHeritage, and Moovit — the latter two Intel-owned — are included at well-established-public-record grade; they were not re-verified in this investigation's searches and are labeled accordingly.)

**The colonization pattern, stated once because it generalizes:** where a platform is clean, Israeli industry builds on top of it. Roblox Corporation surfaced no Israeli corporate ties — yet Israel has a booming Roblox creator economy (a live championship selling out the Menorah Arena six times), and Israeli studios keep being acquired into global gaming portfolios (Beach Bum to Voodoo; Reworks to Playtika for $400 million). The tie migrates to whatever layer Israeli startups colonize.

---

## 14. The Clean Column — the Substitution Table

| Category | Tied | Clean substitute (grade) |
|---|---|---|
| Messaging | WhatsApp/Messenger/Viber (Meta R&D / Israeli) | **Signal, Telegram** |
| Social | Instagram, Snapchat (Cimagine/Voca), Reddit (Spell) | **X (no-evidence)** |
| Dating | — | **Tinder, Hinge — Match Group ledger fully clean** |
| Payments | PayPal/Venmo, eToro (Israeli), Coinbase (Unbound), card rails | **Zelle, Robinhood, Binance (no-evidence), cash** |
| Brokerage/crypto | eToro | Robinhood, Binance (no-evidence) |
| Productivity | Slack (Doti→Slack AI Israel), Microsoft 365, Google Workspace | **Notion, Basecamp, FOSS (no-evidence)** |
| AI | Gemini, Copilot; ChatGPT (Decart pending) | **Claude (no office; Palantir/Rafael caveat)**, local models |
| VPN | **ExpressVPN, CyberGhost, PIA, ZenMate, Hola (Kape)** | **Proton (CH), Mullvad (SE), IVPN (GI), Nord/Surfshark (LT)** |
| Creative | **Facetune/Photoleap/Videoleap (Lightricks)** | **Canva (AU), CapCut, Adobe** |
| Music | Spotify (Tel Aviv R&D) | Bandcamp, local files |
| Navigation | Waze, Google/Apple Maps, Uber, Via, Booking | **Organic Maps (FOSS), Lyft (no-evidence)** |
| Education | Loora | **Duolingo (no-evidence)** |
| Email | Gmail/Outlook/Yahoo | **Proton Mail, Tuta, Fastmail (AU)** |
| Cloud | Drive/OneDrive/iCloud | **MEGA (NZ), pCloud (CH), self-hosted** |
| Streaming | YouTube/Twitch; Spotify (eng.) | **Netflix (content-level only)** |
| In-app SDKs | **AppsFlyer, ironSource/Unity, Taboola/Outbrain** | F-Droid FOSS catalog; DNS blocking (imperfect) |

---

## 15. Methodology and Evidence Grading

**How the investigation was conducted.** Three research passes over the app layer: breadth mapping of every major category; gap-closure on the open items (Lightricks, Match Group, Uber, Canva/Duolingo/Notion); and the infrastructure sweep (Taboola/Outbrain, Roblox, the Israeli catalog). Sources include forensic corporate audits (OpenIntel dossiers for Tencent and Uber), SEC filings (eToro, Via), company press releases and funding announcements, Israeli business press (Globes, Calcalist), quality international press (NYT, The Intercept, Digiday), and market-share datasets (AppsFlyer's own industry data, third-party trackers — flagged as self-reported where applicable).

**Evidence grades:** audit-grade (OpenIntel, with their explicit "no public evidence identified" statements preserved); filing-grade (SEC); on-record (company statements); reported (press); no-evidence-found (nothing surfaced, not proof of absence); unresolved (flagged). Where a review site or market-share dataset has an interest in its own finding, the interest is flagged.

**Caveats the record requires:**
- "No ties found" means no Israeli office, acquisition, R&D center, or investment surfaced in the searches conducted; it is a statement about the evidence, not a guarantee about the world.
- The Kape counterweight is stated in full: ownership documented, misuse not claimed, audits exist.
- The Anthropic/Rafael finding is a report about a customer relationship, not about Anthropic's corporate structure; it is recorded with that framing.
- Self-reported market shares (AppsFlyer's 48.51 percent) are labeled as such and corroborated where third-party trackers exist.

---

## 16. What Remains Unresolved

1. **Bumble** and the **password-manager set** (1Password, Bitwarden, Dashlane, LastPass) — two query rounds timed out; unresolved, not asserted either way.
2. **Uber's numeric BRS score** — the dossier confirms an Israeli footprint; the score was not extracted.
3. **Pinterest's** acquisition of The Yes (2022) — unconfirmed in results.
4. **ByteDance/TikTok** at audit grade — no dossier exists.
5. **Decart/OpenAI** — talks at compilation time; completion unconfirmed.
6. **ironSource/Unity** merger terms at filing grade.
7. **Roblox** — no corporate ties found, unverified grade.
8. **Health/fitness, smart-home, and kids' app categories** — not yet individually swept (Fitbit, Calm, MyFitnessPal, Roblox-adjacent titles).

---

## 17. Key Figures at a Glance

| Entity | Figure | Context |
|---|---|---|
| Viber | $900M (2014) | Rakuten acquisition; ~1B users; Tel Aviv-built |
| eToro | ~$4.2–4.3B valuation | NASDAQ IPO May 2025; HQ Bnei Brak |
| Lightricks | $1.8B valuation (2021) | Facetune et al.; 500–730M downloads |
| PayPal/Israel | $169M + ~$60M + Cymbio | Fraud Sciences 2008; CyActive 2015; Cymbio 2026 |
| Coinbase/Unbound | ~$150M (2021) | MPC wallet cryptography |
| Kape/ExpressVPN | $936M (2021) | Plus CyberGhost, PIA, ZenMate, Intego, vpnMentor |
| AppsFlyer | ~$500M ARR; 48.51% of Android installs | Market leader; Qumra/Pitango on cap table |
| Taboola/Outbrain | $850M merger (closed 2024) | 20,000 properties; 2.6B claimed reach |
| Salesforce/Israel | $1.9B (Own) + ~$100M (Doti) | ~900 staff; Slack AI in Israel |
| Moon Active/Coin Master | $6B+ lifetime | #9 global game revenue H1 2024 |
| Match Group | $1.73B Hyperconnect (2021) | Clean ledger — no Israeli acquisitions |

---

## 18. Glossary

- **SDK (software development kit):** pre-built code an app developer bolts into their app — analytics, ads, payments, maps. The AppsFlyer SDK is inside roughly half of Android apps.
- **Attribution:** the analytics discipline of determining which ad caused an app install — AppsFlyer's business.
- **Mediation / monetization:** the auction system that decides which ad network fills an app's ad slots — ironSource's business.
- **Chumbox:** the "around the web" sponsored-content module at the bottom of articles — Taboola/Outbrain's business.
- **MPC (multi-party computation):** cryptography that splits a secret key into pieces so no single party holds it — Unbound's technology, now inside Coinbase's wallet security.
- **RAM-only servers:** VPN servers that keep no data on disk — ExpressVPN's architectural defense (cited in the counterweight).
- **R&D center:** an engineering office that writes production code, distinct from a sales office.
- **BRS / Tier:** OpenIntel's 1,000-point complicity score and bands (E minimal through B severe).
- **AUP:** acceptable-use policy — Anthropic's rules against weapons-development use.
- **FOSS:** free and open-source software — the F-Droid catalog, Organic Maps, Signal's stack.
- **Entity List:** the US Commerce blacklist (NSO added November 2021).

---

## 19. The Conclusion, in One Paragraph

An app is the one layer of the phone stack where the user holds real power — ninety seconds to delete and replace — and this audit maps exactly where that power reaches. The apps themselves divide into three camps: Israeli-authored category leaders (Viber, eToro, the Lightricks suite, Waze, Via, and a remarkable share of top-grossing games), deeply tied Western services (Meta, PayPal, Slack, Spotify, Coinbase, Booking, Uber), and a genuine clean column (Signal, Telegram, the Match dating portfolio, Proton, Mullvad, Duolingo, Canva, Notion, X, Robinhood, Binance, Zelle, and — by deliberate choice — OpenAI, which manages Israel "from abroad"). Below the apps sits the layer no choice reaches: AppsFlyer inside half of Android installs, ironSource inside free games, and Taboola/Outbrain underneath the news — three invisible pillars, all Israeli-founded. And the cautionary tale of the category is Kape: four of the world's most recommended VPNs, plus the review sites that recommend them, owned by one Israeli billionaire's holding company — the place where a user trying to escape the layer most visibly landed inside it. Every claim above carries a source; every ambiguity is marked; and everything unresolved is listed in Part 16, because an honest map of what cannot be known is worth more than a confident one.

---

*Compiled 2026-09-20. Three research passes; audit-grade, filing-grade, and on-record sources separated throughout; self-reported figures labeled; "no evidence found" statements preserved for what they are.*
