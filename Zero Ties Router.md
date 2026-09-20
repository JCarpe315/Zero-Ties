# The Zero-Ties Router: A Complete Audit of Israeli Entanglement in Home Routers and Mesh Wi-Fi

αΩ∞

*A fully-sourced investigation into the device that sees everything your home does online — home routers and mesh Wi-Fi systems — and the closest configurations to a zero-ties-to-Israel standard, with the protections that matter, as of September 2026.*

---

## 1. Why the Router Is Different

Every investigation in this series has circled the same truth from a different angle: the most important device is the one you never think about. The laptop, the phone, and the apps have all been audited. But every one of them, in every home, passes through a single box — **the router** — and that box sees everything: every website request (as DNS lookups), every device that joins the network, every hour of use, every smart-TV binge and camera feed. If a phone is a diary, the router is the librarian who reads every checkout slip.

A router is also three devices in one: a **modem or gateway** (talks to the ISP), a **router** (directs traffic), and a **Wi-Fi radio** (speaks to your devices). Each layer can be entangled independently. And in most American homes, the ISP chose at least one of those layers for you.

### How to read this document

- **Part 2** gives the short answer.
- **Part 3** orients new readers (router/mesh/cloud basics).
- **Parts 4–8** are the audit: the corporate ledger, the silicon layer, the software layer, the mesh cloud-dependency spectrum, and the attack-surface record.
- **Part 9** is the regulatory shock: the FCC's 2026 router ban and what it does to your choices.
- **Part 10** is the protections chapter — the practical hardening stack.
- **Part 11** is the minimum-entanglement build.
- **Parts 12–15** cover method, open questions, key figures, glossary.
- **Part 16** is the conclusion.

---

## 2. The Short Answer

**No mainstream home router is fully clean — but the router is the one device category where a near-clean, locally-controlled, non-cloud configuration genuinely exists, and where the 2026 US regulatory environment has accidentally narrowed the market to exactly one clean mainstream choice.** The findings:

1. **The three companies making essentially all router Wi-Fi chips are Broadcom (entangled at the silicon level, Israeli R&D), Qualcomm (entangled, two Israeli R&D centers since 1993), and MediaTek (the clean audited path — BRS 248, Tier D, no Israeli office or contract).** Realtek is the secondary clean option. Every router you can buy runs on one of these three; the choice of chip is the single biggest determinant of the router's entanglement.
2. **The cloud is the real divide.** Mesh systems are not created equal in who they report to: **Amazon's eero has no local interface at all** — every setting flows through Amazon's cloud on an app-only design with no opt-out for its data collection — while **Netgear's Orbi is the only major mesh system that runs entirely from a local web interface with no account required**. In this category, "no cloud account" is worth more than any brand promise.
3. **The FCC banned foreign-produced consumer routers in 2026**, and as of May 13, 2026 the only exemptions granted are **Netgear and Eero**. The practical choice set for a new US router has collapsed to one clean US brand (Netgear) versus Amazon's eero.
4. **The attack-surface record proves the stakes**: VPNFilter (2018, ~500,000 routers in 54 countries, attributed to Russia's GRU-linked Fancy Bear) and Slingshot targeted virtually every brand in this document — Netgear, Linksys, MikroTik, ASUS, TP-Link, Ubiquiti, ZTE, D-Link, Huawei. The router is the most-attacked device in the home, and the security research industry that defends it is, in significant part, Israeli (Check Point Research publishes major router threat reports).
5. **The protection pattern is consistent and short**: choose a local-first system (Orbi, or an OpenWrt-flashed device, or a Turris Omnia), put it behind a bridged ISP modem, harden the settings, and take your DNS off your ISP entirely (Unbound locally, or Quad9 — the Swiss non-profit with no logging). Every one of those steps is a half-hour of work.

---

## 3. A Thirty-Second Orientation

A **modem** talks to your internet provider over cable, fiber, or phone line. A **router** directs traffic between your devices and the modem. A **mesh system** is several routers working as one, blanketing a larger home in Wi-Fi. A **cloud-dependent router** stores your settings — and often your Wi-Fi password, device list, and usage metadata — on the manufacturer's servers, which means the manufacturer (and, legally, the government where those servers sit) can be compelled to turn them over. A **local-first router** keeps everything on the box in your house. And **firmware** is the router's own operating software — the layer where implants live, and the layer you update (or fail to).

## 4. The Corporate Ledger

- **Netgear (San Jose, founded 1996).** The only US-headquartered major router brand; FCC-exempt under the 2026 rules. **No Israeli ties surfaced in any pass** — its recent R&D expansion is in Chennai, India (via VAAG Systems, 2025). The **Orbi** line runs fully from a local web interface with no Netgear account required — documented across the user community as "the only major home mesh system not tied to the cloud." Netgear Armor (optional security subscription) is Bitdefender-powered — Bitdefender is Romanian, clean at corporate level. Netgear is the cleanest mainstream choice in the category.
- **eero (Amazon).** The category's market leader by simplicity — and its entanglement is deep. eero hardware runs on **Amazon's Annapurna Labs chips — the Israeli-founded, Tel Aviv-designed silicon arm Amazon acquired in 2015** — and the service sits on Amazon's cloud, which co-holds the Israeli government's Project Nimbus contract. The privacy record: **no web interface at all** (app-only), **no opt-out** from data collection; eero collects network speeds, email, device IP addresses, IP-based geolocation, connected-device lists, and stores network settings in the cloud — where, as router-security analysts note, the US government can compel their production. Privacy reviewers' verdict: "a tougher brand to recommend for privacy-focused consumers."
- **Google Nest WiFi.** Inherits the full Google dossier (Israeli R&D, Nimbus, Israeli chip teams) — and is cloud-managed by default.
- **Linksys (Belkin/Foxconn).** Foxconn-owned since 2018; the laptop-audit Foxconn finding (assembly clean, Apple-partnered supply chain) applies; Linksys keeps a web interface (Velop) — middle of the cloud spectrum.
- **ASUS.** Clean corporate ledger from the laptop audit (no Israeli R&D, acquisitions, or subsidiaries found). ZenWiFi mesh runs local web UI. ASUSWRT firmware is mature; MerlinWRT (third-party) exists. A strong clean alternative.
- **TP-Link (Deco).** A security record, not just a corporate one: **Check Point Research (Israeli firm) discovered a firmware implant in TP-Link routers in May 2023**; Microsoft's CovertNetwork-1658 botnet takedown (October 2024) centered on TP-Link devices; the Texas Attorney General opened a probe in October 2025; the company moved its headquarters to Irvine, California the same month. Market-share claims vary wildly (12% per Lansweeper telemetry; ~65% per disputed industry figures). Under the FCC's foreign-router rules, TP-Link's consumer future in the US is the question mark of the category.
- **Ubiquiti (NYSE-listed, US).** No Israeli ties surfaced. Professional-grade gear with a local controller option; steeper learning curve.
- **MikroTik (Latvia).** No Israeli ties found; enthusiast favorite; runs RouterOS with full local control; OpenWrt-flashable models exist. Note: on both the VPNFilter and Slingshot target lists (as was nearly everyone).
- **Firewalla (Santa Clara, 2016, unfunded).** No Israeli ties surfaced; security-first consumer firewall/router.
- **Turris Omnia (CZ.NIC, Czech non-profit).** Open hardware, open software (Turris OS, auto-updating, ~$334). The maximal-cleanliness enthusiast choice.
- **AVM Fritz!Box (Germany).** Clean corporate; the European standard; not a US-market product.
- **D-Link, Tenda, ZTE (Chinese/others).** No Israeli ties surfaced (unverified grade), but FCC-rule exposure.

## 5. The Silicon Layer

Router Wi-Fi chips are a triopoly: **Broadcom, Qualcomm, and MediaTek control essentially 100%** of the market. From the earlier investigations: Broadcom carries Israeli R&D; Qualcomm has run Israeli R&D centers since 1993 with ~700 Israel staff; **MediaTek is the audited clean path (BRS 248, Tier D — venture-portfolio residue only, no office, no contracts)**; Realtek (Taiwan) is the clean secondary. Practical consequence: a MediaTek Filogic-based router (many ASUS, Netgear, and TP-Link models) or Realtek-based unit minimizes silicon-level entanglement; Broadcom-based units (most high-end) carry the deeper tie. ARM and the EDA duopoly floor applies everywhere, as established in the laptop report.

## 6. The Software and Firmware Layer

- **OpenWrt** (open-source router OS, community-governed) and its cousins (DD-WRT, Tomato; Turris OS) are the cleanest software path: inspectable, no vendor telemetry, WireGuard-capable, ad-blocking (AdGuard Home/Pi-hole) installable.
- **Stock firmware** varies: Netgear and ASUS keep local UIs; eero has none; ISP-issued firmware (Technicolor, Compal) is often locked and update-delayed — a standing security risk documented across the ISP-hardware literature.
- **The Wi-Fi protocol itself** has been broken twice in the modern era: **KRACK (2017)** — Mathy Vanhoef's break of WPA2's handshake, patched everywhere; and **Dragonblood (2019)** — Vanhoef and **Eyal Ronen's** five-flaw demolition of WPA3 (downgrade attacks on transition mode, timing and cache side-channels, denial-of-service, and an EAP-pwd invalid-curve authentication bypass), attackable for under $125 of cloud computing and initially downplayed by the Wi-Fi Alliance. Recorded, with the note that Ronen is Israeli — a defensive-research fact and a people-layer footnote, not a corporate tie.
- **DNS** — the router's most intimate data (every domain you visit) — defaults to your ISP. The protection stack: run **Unbound** locally (your router asks the internet's root servers directly; nothing leaves), or **Pi-hole/AdGuard Home** filtering plus **Quad9** (Swiss non-profit foundation; no logging; blocks malicious domains) as upstream; NextDNS (US, configurable) is the runner-up. Every step away from ISP DNS is a step away from a subpoena-able log of your household's life; encrypt the lookups themselves with DoH or DoT so the ISP cannot read them in transit either.

## 7. The Attack-Surface Record

- **VPNFilter (May 2018):** Cisco Talos and Symantec documented **~500,000 routers across 54 countries** infected by malware attributed to Russia's Fancy Bear (APT28 — the DNC hackers). Targets included Linksys, MikroTik, Netgear, QNAP, and TP-Link models. Three stages: a persistent stage-1 loader that survives reboots, a stage-2 payload for traffic theft and device management, and a **kill switch that could brick half a million devices at once**; a packet sniffer specifically watched **Modbus/SCADA protocols** — Ukraine infrastructure was the evident interest. The FBI seized the command domain (ToKnowAll.com) and publicly advised: reboot, disable remote management, update firmware. CISA later (2022) tracked its successor, **Cyclops Blink** (Sandworm).
- **Slingshot (2018, Kaspersky-discovered):** a second router-implant campaign hitting ASUS, D-Link, Huawei, Linksys, MikroTik, Netgear, TP-Link, Ubiquiti, UPVEL, and ZTE.
- The meta-lesson: **every clean brand in this document was on a nation-state target list** — because routers are the internet's most useful beachhead. Hardening (below) is not paranoia; it is the documented defense against a real, repeated class of attack.

## 8. The Cloud-Dependency Spectrum — the Category's Real Divide

From most to least cloud-bound: **eero** (no local interface exists; app and cloud account mandatory; no data opt-out) → **Deco/TP-Link** (cloud account mandatory; minimal web UI) → **Velop/Linksys** (web interface available) → **Orbi/Netgear** (full local web UI; no account needed — the only major mesh system operable entirely offline) → **OpenWrt/Turris/MikroTik** (fully local, inspectable). The practical rule this document repeats across all three of its companion investigations applies here with special force: **in networking, the clean answer is a shorter wire — the device that works with no account at all.**

## 9. The Regulatory Shock — the FCC's 2026 Ban

On March 23, 2026, the FCC's rules excluding foreign-produced consumer routers from the US market took effect; **as of May 13, 2026, only Netgear and Eero hold exemptions**. Whatever its security rationale (Chinese-manufactured routers were the stated concern), the practical effect on this document's criterion is stark: the new-router choice set has collapsed to **one clean US brand (Netgear) versus Amazon's eero**. Existing routers are unaffected; the used/OpenWrt ecosystem is unaffected; but the mainstream retail shelf is now a two-horse race with exactly one non-Amazon horse.

## 10. The Protections Chapter

In priority order, for any household:

1. **Take the ISP's box out of the driver's seat.** Set the ISP gateway to **bridge mode** (or passthrough/DMZ as fallback) and put your own router behind it. Fiber ONTs usually can't be removed (some GPON SFP workarounds exist); cable modems must come from the provider's approved DOCSIS 3.1 list; DSL needs PPPoE credentials — but the Wi-Fi your family uses can be entirely yours.
2. **Choose local-first hardware.** Orbi (mainstream), ASUS ZenWiFi, MikroTik, Turris Omnia, or any OpenWrt-supported unit. Avoid cloud-mandatory systems if privacy is the criterion.
3. **Harden the settings:** unique admin password; WPA3 (or WPA2-AES minimum); **WPS off** (a brute-forceable design from 2011); **UPnP off** (lets devices punch holes in your firewall); remote management off; firmware auto-update on; guest network for IoT/smart-home devices.
4. **Take DNS off the ISP:** Unbound locally (maximal), or Quad9 upstream (Swiss, no logging, threat-blocking).
5. **Filter at the network:** AdGuard Home or Pi-hole for whole-house ad/malware blocking.
6. **Verify your exposure:** run Gibson's ShieldsUP port scan; check for unexpected open ports.
7. **If you VPN, do it at the router:** WireGuard on OpenWrt/Turris covers every device that joins — with the VPN choices from the apps investigation (Proton, Mullvad, IVPN; avoid the Kape-owned brands).

## 11. The Minimum-Entanglement Build

| Layer | Choice | Residual |
|---|---|---|
| Gateway | ISP modem in bridge mode | ISP firmware layer (unavoidable; minimal exposure) |
| Router/mesh | **Netgear Orbi** (local-first) or Turris Omnia / MikroTik + OpenWrt | Broadcom or MediaTek silicon (prefer MediaTek models; ARM/EDA floor) |
| DNS | Unbound local, or Pi-hole → Quad9 | — |
| Wi-Fi security | WPA3, WPS/UPnP/remote-mgmt off | Protocol-layer history (KRACK/Dragonblood) patched |
| IoT | Guest VLAN/network | — |
| VPN (optional) | WireGuard at router; Proton/Mullvad | — |

**Irreducible floor:** the ISP's modem (you can bridge it, not remove it); the silicon triopoly (choose MediaTek); ARM/EDA; and the fact that the global router-security research ecosystem — including Check Point Research, which published the TP-Link implant finding — is substantially Israeli. The floor here is lower than in any other device category in this series, because the router is the one box you can fully own.

---

## 12. Methodology and Evidence Grading

Five research passes: corporate sweeps (brand by brand), silicon and chipset mapping, software/firmware/cloud-dependency analysis, the attack-surface record (VPNFilter, Slingshot, protocol breaks), and the protection stack. Grades: audit-grade (OpenIntel MediaTek dossier carried from the laptop investigation), S/A-grade (FCC records, Cisco Talos, Vanhoef's papers), community-verified (Orbi local-first, B-grade), no-evidence-found (Ubiquiti, Firewalla), and flagged B-grade (TP-Link market-share disputes). Self-reported claims (eero's data practices as described in its policy) are labeled as such.

## 13. What Remains Unresolved

1. Netgear and ASUS clean status: no-evidence-found, not audit-grade (no OpenIntel dossier exists for either).
2. Ubiquiti/Firewalla: no-evidence-found.
3. The FCC exemption process for further brands: ongoing as of compilation.
4. Whether TP-Link's Irvine restructuring achieves exemption: open.
5. D-Link/Tenda/ZTE corporate: unverified.
6. The identity of Check Point Research's sources for the TP-Link implant: protected, as standard.

## 14. Key Figures at a Glance

| Figure | Value | Context |
|---|---|---|
| Router Wi-Fi chip triopoly | Broadcom / Qualcomm / MediaTek ≈100% | MediaTek = audited clean (BRS 248) |
| VPNFilter | ~500k routers, 54 countries | 2018; Fancy Bear; kill switch |
| FCC foreign-router ban | March 23, 2026 | Exemptions: Netgear, Eero only |
| eero data posture | No opt-out; no local UI | Amazon cloud; Annapurna silicon |
| Orbi distinction | Full local web UI | Only major cloud-free mesh |
| Dragonblood attack cost | <$125 | WPA3's five flaws, 2019 |
| Quad9 | Swiss foundation | No logging; threat-blocking DNS |

## 15. Glossary

- **Modem/gateway:** talks to your ISP; often ISP-owned.
- **Router/mesh:** directs traffic; mesh = multiple units, one network.
- **Bridge mode:** ISP box forwards everything to your router; your router runs the network.
- **WPS/UPnP:** convenience features (button pairing; automatic port opening) that are security liabilities.
- **DNS:** the directory lookups that reveal every site you visit.
- **Unbound/Pi-hole/Quad9:** local resolver / network filter / clean Swiss DNS.
- **OpenWrt:** open-source router operating system; the maximal-control path.
- **KRACK/Dragonblood:** the 2017 and 2019 breaks of WPA2 and WPA3.
- **VPNFilter/Slingshot/Cyclops Blink:** nation-state router malware campaigns.
- **ASIL-D:** automotive safety certification (QNX's domain; relevant to the cars companion document).
- **BRS/Tier:** OpenIntel complicity scoring from the laptop investigation.

## 16. The Conclusion, in One Paragraph

The router is the one device in the home that everything else trusts, and therefore the one where ownership matters most — and it is also, by luck of its open-software heritage, the one device where a private citizen can still achieve near-complete control. The audit finds a category split not by brand virtue but by architecture: cloud-mandatory systems (eero, Deco) that report your household's metadata to a manufacturer's servers by design, versus local-first systems (Orbi, OpenWrt, Turris) that keep it in the house; silicon that is entangled at the top two suppliers (Broadcom, Qualcomm) and audited-clean at the third (MediaTek); and an attack history that proves the box is contested territory among nation-states. The 2026 FCC ban has narrowed the retail shelf to Netgear and Amazon; the citizen's answer is to take the shorter wire — a bridged modem, a local-first router, a private DNS, and thirty minutes of hardening — and thereby turn the most surveilled device in the house into the most defensible one. Every claim above is sourced and graded; every gap is named; the pattern that held across laptops, phones, apps, and the Lebanon file holds here too: the clean answer is never a better company. It is a shorter wire.

---

*Compiled 2026-09-21. Five research passes; grades preserved; self-reported data practices labeled; no-evidence-found statements kept for what they are.*
