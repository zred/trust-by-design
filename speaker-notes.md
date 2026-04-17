# Security Awareness Primer – Speaker Notes (1 Hour)

---

# Opening (5 minutes)

Frame the session around protection, not restriction. The goal is operational
discipline, not paranoia. Most incidents don't start with advanced attacks — they start
with a decision made under pressure or a device trusted on appearance.

---

# Section 1 – Our Risk Landscape (10 minutes)

Establish why this organization is a target. As a second-party partner, we hold access
across multiple client environments — that makes us a higher-value target than a single
dealership and a potential vector into all of them.

Anchor the safe harbor point early: we are custodians of client data, not just users of
it. Contractual and regulatory exposure follows the data, not just the breach.

Close with the key message: breaching a vendor is often easier and more productive than
breaching a dealer directly.

---

# Section 2 – How Social Engineering Works (10 minutes)

Establish the core principle that carries through the rest of the session: attackers
don't break in, they get invited in. Every section that follows is a variation on that
mechanism.

Keep this section conceptual. The techniques listed are a preview — the room doesn't
need to understand each one yet, they need to internalize that familiar does not equal
safe before the detailed material lands.

---

# Section 3 – RICE (10 minutes)

Move directly from how attacks work to why they work. RICE gives employees a vocabulary
for what they are feeling in the moment, which is more actionable than a checklist of
red flags they may not recognize under pressure.

Walk through each element with a concrete example. Ego is often the most surprising —
spend a moment on isolation as a red flag. "Don't loop anyone else in" is not a sign of
trust, it's a sign of manipulation.

Close by telling the room that so far the attacks covered arrive as messages or
requests. The next section covers attacks that arrive as objects — and some that don't
require anyone to act at all.

---

# Section 4 – Tactics You May Not Expect (15 minutes)

Open by noting the shift: everything covered so far assumes the attacker initiates
contact. This section covers what happens when they don't need to.

Move through littering, cloning, conversation hijacking, and environmental trust
exploitation at a steady pace — these extend the social engineering discussion and most
of the room will find them intuitive once framed correctly. The detail lives in the
reference documents; the talking points are the anchor.

Conversation hijacking is worth an extra beat. The attack inherits trust from a real
conversation — the person responding isn't suspicious because they've been working with
this contact for weeks. That's the mechanism. Payment instruction changes mid-thread
are the most common manifestation in this environment.

Transition to hardware by noting the contrast: everything above required someone to act.
The next three items do not.

## Consumer Marketplaces

Spend a moment on commingled inventory — it's the least intuitive mechanism and the
most important. A customer orders from a trusted listing and receives a unit from a bad
actor's stock because they were stored together in the fulfillment center. The listing
looked right because it was right. The product wasn't.

Practical framing for the room: ordering a cheap cable or hub from a marketplace for
office use is a procurement decision, not just a convenience. Anything that touches a
USB port or a network jack is in scope.

## Hardware Implants

The O.MG Cable is the clearest illustration. Describe it plainly: a cable that looks,
charges, and passes data exactly like the one that came with a phone — but contains a
wireless radio and microcontroller that can inject keystrokes, exfiltrate data, and
open a remote access channel without any network connection.

Key message: these are not custom builds. They are sold commercially, documented
publicly, and inexpensive. The Rubber Ducky looks like a thumb drive. The LAN Turtle
looks like a network adapter. The form factors are designed to pass a visual check.

If a physical example is available, this is the moment to show it.

## BADBOX

Anchor this with the FBI PSA from June 2025: millions of devices, mainstream retail
channels, compromise present before first power-on.

Two points worth emphasizing clearly:
- Factory resets don't fix it — the malware is in firmware, below the OS layer
- The device works normally throughout — there is no visible symptom

The most actionable warning sign from the FBI: a device that requires disabling Google
Play Protect during setup should be treated as suspect immediately.

Scope for this room: streaming devices, conference room displays, digital signage, any
Android-based hardware on corporate networks including guest segments.

Close the section by returning to the key point: this threat class doesn't require
user error. What employees can do is report anomalies, apply physical handling habits,
and escalate hardware questions to IT before connecting anything unfamiliar.

---

# Section 5 – High-Risk Scenarios (10 minutes)

Keep this grounded and practical. The room has the conceptual framework — this section
is about recognition and response in the specific scenarios most likely to occur here.

Vendor payment changes and executive urgency requests are the two highest-probability
scenarios. DMS export requests are the highest-consequence. Make sure those land before
moving on.

---

# Section 6 – Data Classification & Safe Harbor (5 minutes)

Reinforce that uncertainty is not a reason to proceed — it's a reason to escalate.
The cost of a false positive is a short delay. The cost of a false negative is
contractual, regulatory, and reputational.

---

# Section 7 – Operational Response Model (5 minutes)

Pause, verify, escalate applies to both digital and physical threats. Make sure the
room leaves knowing that hardware incidents have their own response steps:
don't touch it, don't use the connected machine to report it, call IT from somewhere
else.

Speed of reporting matters more than avoiding embarrassment — this applies equally to
clicking a link and to plugging in a found device.

---

# Section 8 – Cultural Expectations (5 minutes)

Close by reestablishing permission. Employees often hesitate to slow down or push back
because it feels obstructive. Reframe verification as the professional response, not
the cautious one. Slowing down is the job.

---

# Closing

Bring it back to the opening frame: most incidents begin with something that felt
normal. The discipline is in the pause before acting on that feeling.

Pause. Verify. Escalate.

Security awareness is operational maturity.
