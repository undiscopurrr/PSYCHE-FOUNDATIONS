# PSYCHE

**Delivery accounting for contracted compute.** A neutral, reproducible record
of whether a delivery obligation was met — and of who agreed to it.

---

## The problem

A GPU cloud invoices a customer for 1,000 H100-hours delivered over thirty
days. The customer's scheduler shows 972 hours of usable capacity, 28 hours
during which memory bandwidth ran below the contracted floor, and three nodes
that never matched the contracted SKU at all.

Both parties have logs. Each set of logs is internally consistent. Neither party
can compel the other to accept its numbers. Six weeks later a number is agreed
on a call, and nobody writes down how it was reached.

This is the ordinary case, in a market that has grown faster than the
institutions that would normally govern it. Several neocloud providers offer no
standing uptime SLA in default terms. Where an SLA exists, the measurement
period, the exclusion list, and the definition of availability itself differ
between the contract a provider signs with the facility beneath it and the one
it signs with the customer above — so an operator can recover a fraction of
monthly rent upstream while owing credits computed against far larger service
commitments downstream. The market has no settled practice and no neutral
record. It has bilateral reconciliation conducted in spreadsheets.

## What PSYCHE does

Both sides' evidence goes in. A signed, replayable record comes out. It states
what that evidence supports and where it falls short, and whether to accept it
is decided by the party who pays.

For a single delivery period:

**1 · Pin the contract.** The obligation is compiled into a machine-checkable
profile — the channels under measurement, their thresholds, and the sample and
tolerance each one requires. Commercial terms sit outside that profile, in a
registry the evaluation path cannot reach, so the component that decides *what
happened* never sees *what it would cost*.

**2 · Admit the evidence.** Provider telemetry, customer scheduler logs,
third-party probes. Each item is checked: where it came from, whether it covers
the window it claims to cover, and whether it contradicts what the other side
filed. A coverage gap is an outcome in its own right, and so is a conflict
between the parties. Neither is a crash, and neither is quietly dropped.

**3 · Seal it.** The admitted set is assembled into a signed bundle. Anyone
holding that bundle can replay the evaluation and obtain the same result,
without access to the original system.

**4 · Evaluate.** The result has four values. The claim is supported; the claim
is not supported; the *evidence* is at fault, so no verdict on the claim is
available; or the case requires human review. A verifier holding only yes and no
has to guess whenever it cannot decide, and that guess silently becomes money.

**5 · Stop.** Evaluation produces an assertion about evidence and no authority
to settle anything. A case reaches a settled state only when a counterparty with
standing signs a review, inside a valid grant, and that signature is what the
record carries.

**6 · Price the remedy without paying it.** Credits owed under the contract are
quoted from a separate commercial registry. The quote names an amount and
settles nothing.

What changes for the parties: the six-week email thread becomes an artifact both
sides can independently re-derive, and the argument moves from *whose numbers
are right* to *what the shared evidence supports*.

## Why it stops before settlement

The obvious engineering response to this problem is to compile the contract into
machine-checkable obligations, verify automatically, and settle on the verdict.
The paper in this repository accepts nearly all of that and parts company at the
final step.

> Verification establishes **evidentiary sufficiency** — whether a body of
> evidence supports a stated claim under a stated standard.
>
> Acceptance is an exercise of **delegated commercial authority** — whether a
> party agrees to be bound and to pay.
>
> The two have different correctness conditions, and a verdict produced by the
> first cannot discharge the second. Systems that conflate them generate a
> result no counterparty is obliged to honor.

This is a claim about authority. A verifier may be entirely correct and still
lack the standing to bind anyone. No finance function will delegate acceptance
to a third party's algorithm, which is why a design that requires it does not
survive contact with a real procurement process.

## The paper

**[Verification Is Not Acceptance: Evidentiary Sufficiency and Settlement
Authority in Contracted Compute Delivery](yang-verification-is-not-acceptance.pdf)**
· 44 pages · September 2026

- a threat model in which the fabric operator is untrusted, alongside the two
  commercial counterparties
- a formal model of the system as a fold over an append-only signed log.
  Acceptance soundness is the central theorem: a settled case implies a
  counterparty-signed review issued inside a valid grant. Four supporting
  properties make it usable — confluence under causally consistent reordering,
  terminal monotonicity, equivocation detectability, and temporal binding — and
  the last two hold against an untrusted log operator
- a grant constitution that lives inside the contract profile, under the same
  digest that pins the standard, bounding what an accepting agent may be
  delegated. Its default admits one verification outcome, so a buyer who wants
  an agent to accept whatever the evaluation supports has to write that into the
  standard in advance, where the counterparty reads it and can decline
- six enumerated non-derivation invariants, enforced in the event model rather
  than asserted in prose
- a decomposition of finality into four finalities established independently —
  evidence, measurement, counterparty, commercial — and an account of how
  verification-driven settlement acquires its authority by substituting the
  first two for the third
- an evaluation over a 1,760-case corpus spanning twenty-two conditions

Every table in the paper is emitted by a harness rather than typed in. §8 of the
paper states what a reader can and cannot check independently.

## The standard

**[SQCD-1 · Settlement Quality Compute
Data](SQCD-1-settlement-quality-compute-data.pdf)** · 38 pages · version 1.0

The record a delivered compute hour settles on. Two parties name it in their
agreement and it governs the form of the record that settles delivery between
them. It is modelled on SQMD — Settlement Quality Meter Data, the standard
California's grid operator settles its market on — and it answers the same
question for a market that has yet to be asked it: what a meter reading has to
carry before money moves on it.

- **the commodity has a name.** A Grade Class fixes nine dimensions of a compute
  hour — accelerator, intra-node interconnect, inter-node fabric, host, attached
  storage, external network, locality, tenancy, software floor. A rate quoted
  without one prices an unnamed good, and two providers printing the same
  availability number can be selling different things while both tell the truth
- **the buyer can check it.** Every Grade Class field carries a verifiability
  tier: V1 established by the customer's own measurement, V2 by a signature from
  a hardware root of trust, V3 read through an interface the provider operates,
  V4 by a signed declaration made before the window opens. Where confidential
  computing is enabled, the accelerator model and a separate `isolation_attested`
  field are V2, and firmware floors are V2 wherever the report's measurements
  check against the manufacturer's published reference values. Exclusive
  possession of a die stays V4; A8.10 of the standard states the field
  assignments and what `tenancy` does and does not cover
- **delivery is a conjunction of eight layers,** from facility to
  tenant workload. An interval counts as delivered only where every covered
  layer was simultaneously conforming, and the customer's own code never counts
  against the provider. A machine can hold its benchmark and deliver nothing,
  because the scheduler never placed the work
- **what nobody saw is on the face of the record.** Two disclosed fractions: how
  much of the month neither party observed, and how much of it exactly one party
  observed
- **silence resolves, and it never resolves to yes.** A window that passes with
  no counterparty decision expires. Deemed acceptance appears nowhere in this
  standard
- **seven terms it refuses to fill.** Materiality, the unresolved ceiling, the
  evidence class behind every V4 field, the price of expiry, who bears an
  evidence fault, how a divergence resolves to one quantity, and how a reading
  that lands close to a limit is decided. Each allocates loss between the
  parties; a value set here would apply to every contract processed under the
  standard, whatever any of them say. Each is instead enclosed in a published
  set of forms the parties select from before the window opens
- **it sits inside the existing ISO framework rather than beside it.** The
  metric registry is an ISO/IEC 19086-2 metric model extended under that
  standard's own extension clause, with the fields settlement needs and
  description does not: what a function does with an interval no sample
  reached, whether two parties running it must reach one figure, and a version.
  ISO/IEC 19086-2 carries no version field, and a metric that can change under a
  fixed name defeats every finality clause in this document
- **it ships something you can run.** Annex 9 publishes the worked month and
  twelve boundary cases as JSON fixtures with a digest manifest. A counterparty
  checks an implementation's conformance claim without asking anyone
- **conformance is permanent.** A later version never revokes conformance
  established under an earlier one, because a facility written against records
  filed in year one is tested in year four

Annex 3 works a month end to end — 69,120 subject-intervals, two filing parties,
one disputed node — and shows the same samples producing $6,681.60 under one
declared period function and $33,408.00 under another. Annex 8 lists all
thirty-two terms an agreement has to fix, so a defect is an arming-time finding
rather than a dispute-time discovery.

The text is under CC BY-ND 4.0 and the forms, schemas and vectors under a
permissive licence, so a counterparty can attach the standard to an agreement
and an implementer can lift the machine-readable parts into code.

**[SQCD-1 in brief](SQCD-1-in-brief.pdf)** · 3 pages · version 1.0

Every clause in one line, with the layer table, the timetable and the seven
terms the parties fix, each pointing into the standard by clause number. It is
an entry document rather than a second specification: conformance is to the
standard alone, and where the two disagree the standard governs.

## Status

The full contract-to-archive pipeline is implemented and runs end to end:
140,000 lines of Python with a browser client, 195 test modules, 2,781 test
functions. The system is not production-hardened and is not deployed anywhere.
§10.1 of the paper states where the evaluated build departs from the release
specification.

It is ready today for exactly one thing, and that one asks nothing of anybody's
infrastructure: taking a dispute that has already closed and reconstructing it
from the material the two parties exchanged at the time. Every case the system
has been tested against so far was generated. It has not yet seen a real one.

## What is not in this repository

The implementation is private for now. The semantics it implements are not. The
profile structure, the seven evaluation gates, the four-valued output, and the
six invariants are specified in full in §5 and §7 of the paper, and the formal
model in §6 is complete enough to reimplement from.

## Looking for

**One design partner.** A compute seller with a service-credit dispute that has
already closed. Send the SLA clause, the telemetry, whatever the customer sent,
and how it ended. Two weeks later you get back a reconstruction: what the
evidence supports, and where the chain broke. Nothing is deployed and nothing
touches production. I am doing three or four of these this quarter.

**One technical cofounder.**

## Where this version lives

SQCD-1 L8 requires each version's deposit location to be published with it. This
repository is it — `github.com/undiscopurrr/PSYCHE-PAPER` — and this version
comprises:

| File | |
|---|---|
| `yang-verification-is-not-acceptance.pdf` | the paper |
| `SQCD-1-settlement-quality-compute-data.pdf` | the standard, version 1.0 |
| `SQCD-1-in-brief.pdf` | the entry document, version 1.0 |
| `sqcd1-vectors/` | conformance vectors and a digest manifest |

---

Fée-Fée Yang · feifei.gelato@gmail.com
