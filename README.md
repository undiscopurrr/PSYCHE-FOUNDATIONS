# PSYCHE

**PSYCHE provides settlement and Intelligence for contracted compute.** It
produces a neutral, reproducible record of whether a delivery obligation was
met, and of who agreed to it.

Settlement here is the settlement of delivery: the record of what was
delivered, and what it earns under the contract, made final between the
parties. Money moves afterwards, on rails outside PSYCHE, and consumes that
record.

---

## The problem

A GPU cloud invoices a customer for 1,000 H100-hours delivered over thirty days.
The customer's scheduler shows 972 hours of usable capacity, 28 hours during
which memory bandwidth ran below the contracted floor, and three nodes that
never matched the contracted SKU at all.

Both parties have logs. Each set of logs is internally consistent. Neither party
can compel the other to accept its numbers. Six weeks later a number is agreed
on a call, and nobody writes down how it was reached.

This is the ordinary case, in a market that has grown faster than the
institutions that would normally govern it. Several neocloud providers offer no
standing uptime SLA in default terms. Where an SLA exists, the measurement
period, the exclusion list, and the definition of availability itself can differ
between the contract a provider signs with the facility beneath it and the one
it signs with the customer above — so an operator can recover a fraction of
monthly rent upstream while owing credits computed against far larger service
commitments downstream. The market reconciles bilaterally, in spreadsheets.

## What PSYCHE does

Both sides' evidence goes in. A signed, replayable record comes out. It states
what that evidence supports and where it falls short, and whether to accept it
is decided by the party who pays.

For a single delivery period:

**1 · Pin the contract.** The obligation is compiled into a machine-checkable
profile — the channels under measurement, their thresholds, and the sample and
tolerance each one requires. Commercial terms are held apart, in a registry the
evaluation path cannot reach, so the component that evaluates the evidence never
sees *what it would cost*.

**2 · Admit the evidence.** Evidence comes from provider telemetry, customer
scheduler logs and third-party probes. Each item is checked: where it came from,
whether it covers the window it claims to cover, and whether it contradicts what
the other side filed. A coverage gap is an outcome in its own right, and so is a
conflict between the parties. Neither is quietly dropped.

**3 · Seal it.** The admitted set is assembled into a signed bundle. Anyone
holding that bundle can replay the evaluation and obtain the same result,
without access to the original system.

**4 · Evaluate.** The result has four values. The claim is supported; the claim
is not supported; the *evidence* is at fault, so no verdict on the claim is
available; or the case requires review by a party with authority to decide. A
verifier holding only yes and no has to guess whenever it cannot decide, and
that guess silently becomes money.

**5 · Stop.** Evaluation produces an assertion about evidence and no authority
to settle anything. A case reaches `accepted` only through a review signed by the
counterparty, or by a delegate acting under a grant it issued, and the record
carries that signature; without a decision the case expires under the terms both
parties signed before it opened.

**6 · Price the remedy.** Credits owed under the contract are
quoted from a separate commercial registry. The quote names an amount and
settles nothing.

For the parties, the six weeks of reconciliation become an artifact both sides
can independently re-derive, and they argue about *what the shared evidence
supports* rather than *whose numbers are right*.

## Why it stops before settlement

The obvious engineering response to this problem is to compile the contract into
machine-checkable obligations, verify automatically, and settle on the verdict.
The paper in this repository accepts nearly all of that and parts company at the
final step.

> Verification establishes evidentiary sufficiency, a question about whether a
> body of evidence supports a stated claim under a stated standard. Acceptance is
> an exercise of delegated commercial authority, a question about whether a party
> agrees to be bound and to pay. The two have different correctness conditions,
> and a verdict produced by the first cannot discharge the second. Systems that
> conflate them bind the counterparty only as far as it authorized the verifier
> in advance, once, at the level of policy; PSYCHE records that authority per
> case, bounded and revocable.

A verifier may be entirely correct and still lack the standing to bind anyone. A
finance function will not delegate acceptance authority over material spend to a
third-party algorithm. A design that requires it does not survive contact with
a real procurement process.

## The paper

**[Signed in Advance: Evidentiary Sufficiency and Settlement
Authority in Contracted Compute
Delivery](yang-signed-in-advance.pdf)** · 54 pages · October 2026

- a threat model in which the host of the log is untrusted, alongside the two
  contracting parties
- a formal model of the system as a fold over an append-only signed log.
  Acceptance soundness is the central theorem: every accepted case names the
  review that settled it, signed by the counterparty or by its delegate inside
  a valid grant. Five supporting properties make it usable — order invariance
  for fork-free logs, terminal monotonicity, equivocation detectability,
  temporal binding, and silence signed in advance — and equivocation
  detectability and temporal binding hold against an untrusted host
- settlement terms both parties sign when a case opens: how long the
  counterparty has to review once the verification result is on the record,
  which of four enumerated forms the case expires under when that window
  closes without a decision, and the price list a credit against the claimant
  is quoted under. Every state a case reaches through silence is `expired`,
  under the form the silent party signed, and no quantity of silence produces
  acceptance
- a grant constitution that lives inside the contract profile, under the same
  digest that pins the standard. It bounds what an accepting agent may be
  delegated. Unless the profile widens it, it admits one verification outcome,
  so a buyer who wants an agent to accept whatever the evaluation supports has
  to write that into the standard in advance, where the counterparty reads it
  and can decline
- six enumerated derivation invariants, enforced in the event model rather
  than in application policy
- a decomposition of finality into four finalities established independently —
  evidence, measurement, counterparty, commercial — and an account of how
  verification-driven settlement acquires its authority by substituting the
  first two for the third
- an evaluation over a synthetic 1,760-case corpus spanning twenty-two
  conditions, including the whole corpus armed under co-signed terms with
  nobody reviewing: every case expired under the form its arming selected,
  and none was accepted

Every table in the paper is emitted by a harness rather than typed in. §8 of the
paper states what a reader can and cannot check independently.

## The standard

**[SQCD-1 · Settlement Quality Compute
Data](SQCD-1-settlement-quality-compute-data.pdf)** · 39 pages · version 1.0

Version 1.0 is identified by the SHA-256 digest of that file,
`eee135a525bf073083834da23e584432999d95807ce0bc1a2edb4430037f9131`. Its errata
record, published against that digest under L6, is
[`SQCD-1-errata.md`](SQCD-1-errata.md); L6.3 makes the record part of the
standard.

SQCD-1 defines the record a delivered compute hour settles on. Two parties name
it in their agreement and it governs the form of the record that settles
delivery between them. Its name follows SQMD — Settlement Quality Meter Data,
the meter data California's grid operator settles its market on — and it answers
the same question for compute: what a meter reading has to carry before money
moves on it.

A Grade Class names the commodity. It fixes nine dimensions of a compute hour —
accelerator, intra-node interconnect, inter-node fabric, host, attached storage,
external network, locality, tenancy, software floor. A rate quoted without one
prices an unnamed good, and two providers printing the same availability number
can be selling different things while both tell the truth.

Every Grade Class field carries a verifiability tier: V1 established by the
customer's own measurement, V2 by a signature from a hardware root of trust, V3
read through an interface the provider operates, V4 by a signed declaration made
before the window opens. Where confidential computing is enabled, the
accelerator model and a separate `isolation_attested` field are V2, and firmware
floors are V2 wherever the report's measurements check against the
manufacturer's published reference values. Exclusive possession of a die stays
V4; A8.10 of the standard states the field assignments and what `tenancy` does
and does not cover.

Delivery is a conjunction of eight layers, from facility to tenant workload. An
interval counts as delivered only where every covered layer was simultaneously
conforming, and the customer's own code never counts against the provider. A
machine can hold its benchmark and deliver nothing, because the scheduler never
placed the work.

What nobody saw is on the face of the record, as two disclosed fractions: how
much of the month neither party observed, and how much of it exactly one party
observed.

Silence resolves, and it never resolves to yes. A case whose review deadline
passes with no counterparty decision expires, and deemed acceptance appears
nowhere in the standard.

The standard refuses to fill seven terms: materiality, the unresolved ceiling,
the evidence class behind every V4 field, the price of expiry, who bears an
evidence fault, how a divergence resolves to one quantity, and how a reading
that lands close to a limit is decided. Each allocates loss between the parties;
a value set here would apply to every contract processed under the standard,
whatever any of them say. Each is fixed by the parties before the window opens,
and all but the V4 evidence class are selected from a published set of forms.

Its metric registry extends ISO/IEC 19086-2. Each registry entry is an ISO/IEC
19086-2 metric extended under that standard's own extension clause, with the
fields settlement needs and description does not: what a function does with an
interval no sample reached, whether two parties running it must reach one
figure, and a version. ISO/IEC 19086-2 carries no version field, and a metric
that can change under a fixed name defeats the standard's finality clauses.

Annex 9 publishes the worked month and fourteen boundary cases as JSON fixtures
with a digest manifest, and a counterparty can check an implementation's
conformance claim against them without asking anyone.

Conformance is permanent. A later version never revokes conformance established
under an earlier one, because a facility written against records filed in year
one is tested in year four.

Annex 3 works a month end to end — 69,120 subject-intervals, two filing parties,
one disputed node — and shows the same samples producing $6,681.60 under one
declared period function and $33,408.00 under another. Annex 8 lists all
thirty-two terms an agreement has to fix, so a defect is an arming-time finding
rather than a dispute-time discovery.

The text is under CC BY-ND 4.0 and the forms, schemas, vectors and registry
entries under the MIT licence (`LICENSE.md`), so a counterparty can attach the
standard to an agreement and an implementer can lift the machine-readable parts
into code.

**[SQCD-1 in brief](SQCD-1-in-brief.pdf)** · 3 pages · version 1.0

It gives the record's fields, A to F, one line each, with the layer table, the
timetable and the seven terms the parties fix, each pointing into the standard
by clause number. It is an entry document: conformance is to the standard alone,
and where the two disagree the standard governs.

## Status

The full contract-to-archive pipeline is implemented and runs end to end, in
Python with a browser client. §6.12 of the paper counts the tests that hold each
stated property, and the invariant harness exits non-zero on any violation, so a
release can be gated on it. The system is not production-hardened and is not
deployed anywhere. §10.1 of the paper states where the evaluated build departs
from the release specification.

It is ready today for exactly one thing, and that one asks nothing of anybody's
infrastructure: taking a dispute that has already closed and reconstructing it
from the material the two parties exchanged at the time. Every case the system
has been tested against so far was generated. It has not yet seen a real one.

## What is not in this repository

The implementation is private for now. The semantics it implements are not. The
paper states the invariants of §5.3, the model of §6 and the design of §7 in
enough detail to reimplement from, and §11 records where they are incomplete.

## Looking for

We are looking for one design partner: a compute seller with a service-credit
dispute that has already closed. Send the SLA clause, the telemetry, whatever
the customer sent, and how it ended. Two weeks later you get back a
reconstruction: what the evidence supports, and where the chain broke. Nothing
is deployed and nothing touches production.

We are also looking for one technical cofounder.

## Where this version lives

SQCD-1 L8 requires each version's deposit location to be published with it. This
repository is it — `github.com/undiscopurrr/PSYCHE-PAPER` — and this version
comprises:

| File | |
|---|---|
| `yang-signed-in-advance.pdf` | the paper |
| `SQCD-1-settlement-quality-compute-data.pdf` | the standard, version 1.0 |
| `SQCD-1-errata.md` | the errata record for version 1.0, with the digest it is published against |
| `SQCD-1-in-brief.pdf` | the entry document, version 1.0 |
| `sqcd1-schemas/` | the record schemas Annex 5 names, as the reference implementation runs them, and a digest manifest |
| `sqcd1-vectors/` | conformance vectors and a digest manifest |
| `sqcd1-registry/` | the seven canonical period functions Annex 2.1 indexes, as `metric_registry_entry` objects, and a digest manifest |
| `LICENSE.md` | CC BY-ND 4.0 for the standard's text, the brief and the paper; MIT for `sqcd1-schemas/`, `sqcd1-vectors/`, `sqcd1-registry/` and Annex 1's Filing Plan form |

---

Fée-Fée Yang · feifei.gelato@gmail.com
