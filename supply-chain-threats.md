# Hardware Supply Chain Threats

## Why Hardware Threats Are Different

Social engineering attacks target decisions. Hardware supply chain attacks target the
devices you trust before you ever make a decision. By the time an employee plugs in a
cable or connects a device, the compromise may already be present — not installed by a
user action, but embedded in the manufacturing, shipping, or resale chain.

This document covers three related threat categories: malicious consumer marketplace
listings, hardware implants sold as accessories, and compromised firmware distributed
at scale.

The common thread: the device looks legitimate because, in every visible way, it is.

---

## The Consumer Marketplace Problem

Platforms like Amazon, Walmart Marketplace, and Best Buy Marketplace allow third-party
sellers to list products alongside those sold directly by the platform. This creates a
specific vulnerability: a listing may appear legitimate — correct branding, professional
photos, competitive pricing — while the physical product has been swapped, tampered
with, or sourced through an unauthorized supplier.

**How products get compromised in the channel:**

- **Commingled inventory:** On Amazon in particular, identical products from different
  sellers may be stored together in fulfillment centers. A bad actor listing a
  counterfeit or modified version of a popular item may have their units shipped to
  customers who ordered from a trusted seller.
- **Third-party seller infiltration:** Marketplace sellers with established review
  histories can be acquired or compromised. A high-rated seller is more likely to be
  trusted without scrutiny.
- **Return fraud and repackaging:** Returned items, potentially including modified ones,
  may re-enter the fulfillment chain in some circumstances.
- **Gray market and surplus sourcing:** Items sold as new may have passed through
  multiple undocumented hands, particularly in electronics categories.

**High-risk product categories in this environment:**

USB hubs, charging cables, power adapters, network switches, KVM devices, webcams,
keyboards, streaming devices, and digital display hardware.

---

## Hardware Implants: Commercially Available Attack Tools

Hardware implant tools that were once limited to nation-state actors are now
commercially available, well-documented, and within reach of motivated non-specialists.
The threat model is not that someone will encounter a sophisticated custom implant — it
is that they will encounter a commercially available one that looks entirely ordinary.

### O.MG Cable

Developed by security researcher MG and sold through Hak5, the O.MG Cable is a USB
cable — available in USB-A, USB-C, and Lightning form factors — that contains an
embedded microcontroller and wireless radio. It is physically indistinguishable from a
standard cable and passes power and data normally.

Capabilities include:

- Keystroke injection (the host sees it as a trusted keyboard)
- Wireless access point accessible from nearby, requiring no network connection
- Remote script execution
- Payload staging and geofencing (can be configured to activate only in specific
  locations or environments)
- Data exfiltration over Wi-Fi

The cable is sold openly for penetration testing at approximately $150–$200. Functionally
similar devices can be constructed for a fraction of that cost.

**Reference:** [Hak5 O.MG Cable](https://shop.hak5.org/products/omg-cable)

### Related Commercially Available Implant Classes

Hak5 produces and sells a range of hardware implant tools used in authorized penetration
testing. The same capabilities make them viable attack tools when planted without
authorization.

- **USB Rubber Ducky** — Presents as a keyboard and executes a pre-loaded keystroke
  injection payload. Current generation supports conditional logic, exfiltration, and
  environment fingerprinting. Retail ~$60.
- **Bash Bunny** — Multi-mode USB platform capable of presenting as multiple device
  types simultaneously (keyboard, network adapter, mass storage). Supports scripted
  attack sequences. Retail ~$120.
- **Shark Jack** — Small network implant designed for insertion inline in a wired
  connection. Performs network reconnaissance and can exfiltrate results wirelessly.
  Retail ~$60.
- **LAN Turtle** — A USB-to-Ethernet adapter containing a covert Linux system.
  Provides persistent remote access, man-in-the-middle capability, and network
  intelligence gathering. Retail ~$60.
- **WiFi Pineapple** — Wireless auditing platform capable of rogue access point
  creation, traffic interception, and credential capture. Retail ~$100–$200.

**Reference:** [Hak5 Shop](https://shop.hak5.org/)

A Bash Bunny looks like a USB thumb drive. A LAN Turtle looks like a generic network
adapter. An O.MG Cable looks like the cable that shipped with your phone. These tools
are sold legally and their documentation is public. Their form factors are deliberately
inconspicuous.

---

## BADBOX: Firmware-Level Compromise at Scale

BADBOX refers to a class of attacks where consumer IoT devices arrive with malware
pre-installed in firmware, before they reach a retailer or end user. The FBI issued a
Public Service Announcement in June 2025 warning that the successor campaign, BADBOX
2.0, consists of millions of infected devices across mainstream retail channels.

Affected device categories include TV streaming boxes, digital projectors, digital
picture frames, and aftermarket vehicle infotainment systems. Most affected devices
were manufactured in China. Compromise occurs either during manufacturing (prior to
purchase) or during initial setup when the device is directed to download applications
containing backdoors.

**Reference:** [FBI IC3 PSA I-060525-PSA — Home Internet Connected Devices Facilitate
Criminal Activity](https://www.ic3.gov/PSA/2025/PSA250605)

**What compromised firmware can do:**

- Enroll devices in a botnet used for ad fraud, credential stuffing, or residential
  proxy services sold to other threat actors
- Maintain persistent backdoors that survive factory resets
- Forward or intercept network traffic
- Install additional payloads after the device reaches the internet

**Why this is hard to detect:**

- The device works as advertised
- Standard antivirus tools operate at the app layer, not firmware level
- Compromise may predate the device's first power-on
- Affected devices often ship in legitimate-looking retail packaging

**FBI-identified indicators of BADBOX 2.0 activity:**

- Device requires disabling Google Play Protect during setup
- Apps are sourced from unofficial marketplaces rather than verified storefronts
- Device is advertised as "unlocked" or capable of accessing free streaming content
- Brand is unrecognizable or difficult to attribute to a verifiable manufacturer
- Android device is not Play Protect certified
- Unexplained outbound network traffic from the device

---

## The Common Thread

These three threat categories — compromised marketplace hardware, hardware implants, and
firmware-level compromise — share a mechanism with the physical littering attacks covered
in social engineering training: a physical object in a trusted context becomes the
delivery vehicle.

The difference is scale and deniability. A dropped USB drive requires someone to find it
and plug it in. A compromised cable ordered from a marketplace ships directly to the
target, pre-trusted, in original packaging. A BADBOX device may have been enrolled in a
botnet before it was ever powered on.

---

## Mitigation

**Procurement controls:**

- Prefer hardware sold and shipped directly by the manufacturer or an authorized
  distributor rather than third-party marketplace sellers
- Verify the actual seller name on marketplace listings, not just the product listing or
  brand name
- Be skeptical of significantly lower prices on commodity hardware (cables, adapters,
  hubs, chargers)
- Source streaming and display hardware from vendors with documented firmware update
  processes and Play Protect certification
- Treat any device advertised primarily on price or "free content" access as elevated
  risk
- Consult IT before connecting new media or display hardware to corporate infrastructure

**Physical handling:**

- Only use charging cables and adapters from known, controlled sources
- Treat found, gifted, or unexpectedly delivered cables and adapters as untrusted
  regardless of appearance
- Use USB data blockers when charging from unknown or shared ports
- Do not connect unknown USB devices to any corporate endpoint, even briefly
- Treat small unidentified plug-in devices on existing network drops as potential
  implants and report them to IT immediately

**Network controls:**

- Isolate consumer-grade Android and IoT devices on separate network segments with
  restricted egress
- Monitor for unexplained outbound traffic from streaming, display, and IoT device
  classes
- Do not place untrusted devices on network segments with access to DMS data, platform
  credentials, or internal systems

---

## Remediation

If a potentially compromised device is identified:

1. **Disconnect** the device from all networks immediately — wired and wireless
2. **Do not power cycle** before IT has evaluated it; some volatile indicators may be
   lost
3. **Preserve** the device and any packaging or documentation for IT review
4. **Report** to IT and security leadership using known contact information, not through
   any system the device may have had access to
5. **Audit** other devices in the same procurement batch or from the same seller
6. **Review** network logs for the period the device was active to identify any
   anomalous traffic it may have generated

If a hardware implant (cable, adapter, or inline device) is found on or connected to
corporate hardware:

1. **Do not remove it yourself** — note its location and photograph it if possible
2. **Report immediately** to IT
3. **Treat the connected endpoint as potentially compromised** pending investigation
4. **Do not use that endpoint** to report the incident — use a separate device

---

## Key Reminder

Hardware supply chain threats do not require a user to make a mistake. They require
only that a device be trusted because it looks legitimate. Procurement discipline,
physical handling habits, and network segmentation are the controls — not user
vigilance alone.
