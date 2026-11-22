# SQCD-1 · Errata record

Published against **SQCD-1 · Settlement Quality Compute Data, Version 1.1**,
issued by PSYCHE, identified by the SHA-256 digest of
`SQCD-1-settlement-quality-compute-data.pdf`:

    65b026d4eea0da653f647271779d47bc480bae514990dd258d50d6988cd2e7c4

Each entry below names the clause, the defect, and its disposition under L6.
The version's digest is unchanged. A record armed under Version 1.1 stays armed
under it. L6.3 makes this record part of the standard, and a reader holding
the version without it holds an incomplete document.

## Entries recorded 2026-11-21

Each defect below changes what its clause requires, so under L6.1 only a new
version corrects it. Version 1.2, issued 15 November 2026, corrects every one,
and each disposition names where. Clause numbers are those of Version 1.1; a
disposition gives those of Version 1.2.

### 1 · B7.2; C5.1 to C5.5; J1

**Defect.** C5 places each interval in a row by whether both, one or neither
Filing Party observed it, and B7.2 decides delivery across every covered Layer
together. No clause said whether a party that read some covered Layers of an
interval and not others observed it.

**Disposition.** Corrected in Version 1.2. Section 3 defines Observed. J1
finds an evidence fault Layer by Layer, C5.2 turns on that fault, and the rows
of C5.5 turn on who observed the interval and whether a fault falls on it.

### 2 · C2; C4

**Defect.** C2 made a record carrying a cause outside the vocabulary not
conforming, while C4 made a signature the condition of a declaration. Neither
clause said whether a signed declaration with a cause outside the vocabulary
counts as declared.

**Disposition.** Corrected in Version 1.2. C4: a gap counts as declared only
when it is signed and its cause is drawn from the vocabulary in C2, and the
sentence of C2 making such a record not conforming is deleted. A defective
declaration reaches C5.5 only through an evidence fault under J1.

### 3 · C5.2; C5.4

**Defect.** No clause said whether a gap declaration signed after W+2 moves an
interval into the row for intervals every required party declared.

**Disposition.** Corrected in Version 1.2. C5.2: an interval is Unresolved
only where no Filing Party observed it and none bears an evidence fault on it
under J1, so the W+2 deadline of J1 governs.

### 4 · C5.1; J1; Annex 2.5.1; Annex 8.2

**Defect.** Under EF-05, and under EF-01 after W+30, a party could remove an
interval the other party had observed in time by filing nothing. The general
sentence of Annex 2.5.1 would refuse that selection, and the three cases it
named omitted it.

**Disposition.** Corrected in Version 1.2. An interval one Filing Party
observed carries that observation (C5.1, C5.5). J1 records an evidence fault
whether or not another Filing Party observed the interval, and its allocation
under Annex 2.5 reaches only intervals no Filing Party observed. Annex 2.5.1
names two closed cases, and Annex 8.2 points to it.

### 5 · Annex 2.5.1

**Defect.** The test in Annex 2.5.1 turned on the party holding the required
evidence, and the standard did not say who holds it or who decides that.

**Disposition.** Corrected in Version 1.2. Annex 2.5.1: EF-02 is not
conforming where the provider's Filing Plan reads a covered Layer of the
obligation, and EF-03 where the customer's does. The defect is detectable when
the Profile is armed and must be reported then (Annex 2.5.1).

### 6 · C5.1; C5.5; J1; Annex 2.5

**Defect.** C5.1 and the second row of C5.5 valued every unilateral interval
by the Annex 2.5 selection, while J1 and Annex 2.5 addressed only intervals
carrying an evidence fault.

**Disposition.** Corrected in Version 1.2. A unilateral interval carries the
observation that exists, and any fault is recorded under J1. Annex 2.5 reaches
only intervals no Filing Party observed.

### 7 · Annex 2.5 EF-04; Annex 3.3

**Defect.** For a unilateral interval under EF-04, the form charged the
interval to the party C5.4 attributes it to, while Annex 3.3 valued it by the
observation that exists. Where that observation is non-conforming, the two
give opposite results.

**Disposition.** Corrected in Version 1.2. Unilateral intervals no longer pass
through Annex 2.5. EF-04 values an interval no Filing Party observed, and
Annex 3.3 records the fault against the customer and values the interval by
the provider's record.

### 8 · C5.5; Annex 2.5 EF-04, EF-06

**Defect.** The standard gave no value for a unilateral interval under EF-04
where no party could be attributed, or under EF-06, and did not say whether
the interval stays in the denominator.

**Disposition.** Corrected in Version 1.2. Every unilateral interval carries
the observation that exists (C5.1). EF-06 states that the interval leaves
numerator and denominator and that the ratio applies to the consequence under
A7.

### 9 · Annex 2.5 EF-01

**Defect.** Under EF-01 the standard did not say whether a suspended interval
stays in the denominator before W+30, which Fraction counts it, or whether the
Window yields a figure at all.

**Disposition.** Corrected in Version 1.2. EF-01 is deleted, with its
references in Annex 2.5.1, Annex 2.5.2 and the paragraph on EF-07. Edge case
EV-18, which tested it, is retired.

### 10 · C5.1; J2

**Defect.** A sole observer that filed late was better placed than one that
filed in time: the timely unilateral observation took the Annex 2.5 value, and
the late one took its own reading.

**Disposition.** Corrected in Version 1.2. A unilateral interval carries the
observation that exists, so a late sole observation and a timely one carry the
same value. The late filing still bears an evidence fault under J1.

### 11 · J2

**Defect.** Where a late first measurement conflicted with the other party's
timely observation, the standard did not say whether the interval was then
observed by both parties or by one, or which reading valued it.

**Disposition.** Corrected in Version 1.2. J2: a late first measurement that
conflicts with the other party's on-time reading of that Layer is admitted for
a pass only if that party accepts it by the pass's date, and then displaces
that reading.

### 12 · J2; I.1, W+30 row

**Defect.** The standard did not say what happens to a correction filed before
the correction window opens.

**Disposition.** Corrected in Version 1.2. J2: no pass uses a correction filed
before the correction window opens under the W+30 row.

### 13 · I.1, W+30 row; I.1.3

**Defect.** The standard did not say whether an amendment both parties sign
before W+90 moves the figure, or whether an amendment signed by one party, or
not naming I.1.3, becomes part of the record. I.1.3 also let an amendment move
a Period Figure that 4.3 recomputes from the filed samples.

**Disposition.** Corrected in Version 1.2. I.1.3 and the amendment in the W+30
row are deleted. A difference the correction establishes is claimed by a
credit Claim under I.1.4.

### 14 · E2; Annex 8.1 row 28

**Defect.** A deadline can be proven only by a log head, and the minimum in
row 28 was one head per Window close. Where the next head came after a
deadline, the standard gave no way to tell whether a filing was in time.

**Disposition.** Corrected in Version 1.2. E2: a record counts as filed by a
date only where a head published by the end of that date includes it. Row 28
requires at least one head at the end of each day under I.1.

### 15 · E2; Annex 8.1 row 28

**Defect.** The standard did not say who operates the log, whether the
operator is independent of both parties, how soon it includes a filing, or how
readers holding different heads compare them.

**Disposition.** Corrected in Version 1.2. Row 28: the Profile fixes the log
operator, which is neither Filing Party and includes each filing in its next
head, publishes at least one head at the end of each day, and makes every head
readable by any grantee under K3.

### 16 · C5.3; J5; K4; Annex 2.3

**Defect.** The conditions under which a Period Figure is not conforming were
spread across C5.3, J5, K4 and Annex 2.3. The standard did not say whether a
figure is conforming where an upstream record fails for another reason, or
where no Unresolved Fraction is stated under UC-04.

**Disposition.** Corrected in Version 1.2. C5.3: a Period Figure is not
conforming only where the Unresolved Fraction exceeds the ceiling in A6 or J4
applies, and no other clause makes it not conforming. J5 of Version 1.1 is J4
of Version 1.2.

### 17 · H3; F1

**Defect.** The standard did not say what quantity a Claim states where only
one party filed for the Window, or where no party filed.

**Disposition.** Corrected in Version 1.2. H3: where fewer than two Filing
Parties file for the Window, no Divergence is computed, and the Period Figure
the filed record yields carries forward.

### 18 · Annex 2.7 DR-02

**Defect.** Under DR-02 the standard did not say how the quantity is fixed
where the two figures differ by more than the stated bound.

**Disposition.** Corrected in Version 1.2. DR-02: beyond the bound, another
form of Annex 2.7 that the Profile selects governs. The bound and that form
are its parameters.

### 19 · Annex 2.7 DR-03

**Defect.** DR-03 did not say when the third reading is taken or filed,
whether it enters the record as Sections B, D and E require, or what governs
before it exists.

**Disposition.** Corrected in Version 1.2. DR-03: the third reading enters the
record as Sections B, D and E require of a filing, by a date the Profile
states before the review deadline, or decides nothing.

### 20 · Annex 2.7 DR-05

**Defect.** Where a Profile under DR-05 barred appeal and a party appealed
anyway, the standard did not say whether the panel's majority had already
fixed the quantity.

**Disposition.** Corrected in Version 1.2. The appeal parameter is deleted
from DR-05. The panel decides by majority.

### 21 · F2; Annex 2.4 EX-03

**Defect.** Where a Claim carried two candidate figures, the standard did not
say which one an accept accepts, or which one is owed where the Case expires
under EX-03.

**Disposition.** Corrected in Version 1.2. F2: while the quantity is undecided
among candidate figures, an accept names one of them and counts toward the
quorum only with accepts naming the same one. EX-03 prices nothing where the
Case expires with the quantity undecided.

### 22 · F2; Annex 8.1 row 25

**Defect.** The standard did not say whether a quorum counts accepts or
signers.

**Disposition.** Corrected in Version 1.2. Row 25 admits only
order-insensitive forms that count each signer once. A Profile with another
form cannot be armed.

### 23 · I.1.5

**Defect.** The standard did not say whether a credit Claim of zero must be
filed, or which party files a credit Claim where a pass has no figure and the
amount follows the agreement's terms.

**Disposition.** Corrected in Version 1.2. A credit Claim whose amount is
zero, or favours a party other than its claimant, is not conforming (I.1.4).
Where either pass has no figure, the amount and the party it favours follow
the agreement's terms identified under A7.

### 24 · I.1.5

**Defect.** I.1.5 named three ways a credit Claim is not conforming. It did
not address a claimant the amount does not favour, a review deadline other
than the one set for its Case, or an adjusted Claim that has not reached a
terminal state.

**Disposition.** Corrected in Version 1.2. I.1.4 states the conditions as a
table, and a credit Claim is not conforming where any row holds.

### 25 · I.1.5

**Defect.** The deduction for an earlier credit Claim that expired under EX-03
was undefined where its stated amount differed from the amount I.1.5 computes,
where its pass had no figure, or where it was not conforming.

**Disposition.** Corrected in Version 1.2. I.1.4 deducts the amounts stated in
the earlier credit Claims, conforming or not, that ended accepted or expired
under EX-03.

### 26 · I.1.5

**Defect.** A credit Claim that ended disputed and was paid outside the
standard was not deducted from the next credit Claim, and the standard did not
say how the amounts net against what was actually paid.

**Disposition.** Corrected in Version 1.2. I.1.4 deducts only credit Claims
that ended accepted or expired under EX-03. The agreement's terms identified
under A7 set the amount against what was paid on the adjusted Claim or on a
credit Claim not deducted.

### 27 · B8.5; B7.2

**Defect.** The standard did not say whether hours on which a Grade Class
field was read as non-conforming still count as hours of the contracted Grade
Class, or whether the covered Layers count as conforming on the intervals of
that reading.

**Disposition.** Corrected in Version 1.2. B8.5: such a reading is its Filing
Party's non-conforming reading, at the Layer the field belongs to, for each
interval in which the measurement ran, unless A9.2 admits the hours as hours
of another Grade Class.

### 28 · B7.4

**Defect.** B7.4 required each failed covered Layer to be named only where
more than one failed, and left the case of a single failed Layer, and the
attribution it pointed to, unstated.

**Disposition.** Corrected in Version 1.2. B7.4 is deleted. The samples filed
for each Layer under B2 show which Layer failed.

### 29 · B8.3

**Defect.** B8.3 did not say whether the minimum observation of B8.2 is judged
by what a customer observed or by what it declared.

**Disposition.** Corrected in Version 1.2. B8.3 is deleted, and no clause
turns on meeting B8.2. A party bears an evidence fault under J1 on an interval
where, for a covered Layer its Filing Plan required it to read, it files
neither conforming measurements of that Layer nor a declaration under C1
through C4 by W+2.

### 30 · Annex 2.5 EF-01

**Defect.** In a pass dated W+30, the standard did not say whether an interval
still suspended under EF-01 had already been treated as under EF-05.

**Disposition.** Corrected in Version 1.2. EF-01 is deleted, as entry 9
records.

### 31 · C5.5; Annex 2.5.2

**Defect.** Annex 2.5.2 stated for some forms only that an interval no party
observed counts in the Unresolved Fraction, and left EF-02, EF-03, EF-07 and
EF-01 before W+30 unstated.

**Disposition.** Corrected in Version 1.2. The table in C5.5 has a column
Counted in, and both rows for an interval no party observed count it in the
Unresolved Fraction.

### 32 · J2

**Defect.** Under EF-07 final on filing, J2 archived late measurements on
every interval, including intervals that carried no estimate, such as
Unresolved intervals under C5.2.

**Disposition.** Corrected in Version 1.2. J2: a first measurement filed after
W+2 and by W+30 is archived, with the estimate standing, only where the
interval carries an EF-07 estimate final on filing.

### 33 · J2

**Defect.** Corrections fell outside the rule that a late measurement does not
displace a timely observation, so a party could file a placeholder in time and
correct it after reading the other party's filing.

**Disposition.** Corrected in Version 1.2. J2: no pass uses a correction
contrary to the other party's timely observation unless that party accepts it
by the pass's date.

### 34 · D3

**Defect.** D3 treated two readings from one trust root as one reading,
without defining a trust root or saying where C5.5 then places the interval.

**Disposition.** Corrected in Version 1.2. The sentence is deleted. D3 records
whether two required sources share a trust root, and C5 counts observations by
Filing Party under the definition of Observed in Section 3.

### 35 · I.1; Annex 8.1

**Defect.** Every deadline runs in business days, and the standard named no
calendar and no hour at which a day ends.

**Disposition.** Corrected in Version 1.2. Annex 8.1 row 26: the agreement
fixes the calendar of days under I.1 and the hour and time zone at which each
day ends.

### 36 · 4.3; 4.6

**Defect.** The standard did not say whether a Period Figure that fails to
recompute under 4.3 also fails the completeness test of 4.6.

**Disposition.** Corrected in Version 1.2. 4.3: a stated figure or named
quantity that does not recompute fails that condition alone.

### 37 · K4; 4.6

**Defect.** K4 made a Period Figure resting on a confidential value not
committed before the Window not conforming, and 4.6 did not address that case.

**Disposition.** Corrected in Version 1.2. Those words of K4 are deleted. A
value not committed before the Window leaves its rows of Annex 8.1 unfixed,
and the Profile cannot be armed.

### 38 · Annex 2.1.4

**Defect.** Annex 2.1.4 did not say which undefined quantity it names where
the subject set is empty under F-04, or whether it also names a zero
denominator where A4 excludes every interval.

**Disposition.** Corrected in Version 1.2. Annex 2.1.4 states its conditions
and the names it gives as a table, and every row that holds is named.

### 39 · Annex 2.1.4; C5.3

**Defect.** Where no interval of a Window was eligible before C5 although A4
had not excluded every interval, both Fractions were 0/0, and Annex 2.1.4 gave
a substitute only where A4 excludes every interval.

**Disposition.** Corrected in Version 1.2. Annex 2.1.4: where no interval of
the Window is eligible before C5, the quantity intervals_eligible_before_c5
stands in place of both Fractions under 4.4, and no ceiling is exceeded under
C5.3.

### 40 · Annex 2.2 MT-02; A6; H2

**Defect.** MT-02 compared only the counts of conforming intervals on each
subject, so a difference that moved only the denominator was never material,
while A6 and H2 define the threshold and Divergence on the two figures.

**Disposition.** Corrected in Version 1.2. Annex 2.2.1: under MT-02, both the
numbers of conforming intervals and the numbers of eligible intervals on each
subject are compared, and the Divergence is material where either difference
on any one subject exceeds the parameter.

### 41 · 7.0.2.2; Annex 8.1 row 21

**Defect.** Where two parties read one V1 field, a difference beyond the
reproducibility limit counted as a divergence, while Section H defines
Divergence as the difference between two Period Figures.

**Disposition.** Corrected in Version 1.2. 7.0.2.2: two Filing Parties'
independent readings of the same field reach Section H only through the Period
Figures. The reproducibility limit is no longer a term of Annex 8.1.

### 42 · F1; I.1, W+7 row

**Defect.** The standard did not say which party files the delivery Claim, or
what follows where none is filed, although under the expiry forms who pays
turns on who was silent.

**Disposition.** Corrected in Version 1.2. Annex 8.1 row 29: the Profile names
the party that files the delivery Claim. Under the W+7 row that party files
it, and where it files none, what is owed follows the agreement's terms
identified under A7.

### 43 · F3; Annex 8.1 row 27

**Defect.** The standard did not require a grant and its limits to be on the
record before a Decision signed under it, or say how to correct a Case
recorded as accepted under a grant later found to have been exceeded.

**Disposition.** Corrected in Version 1.2. Row 27: the grant constitution
requires each grant to be filed with its limits before any Decision signed
under it.

### 44 · I.1, W+7 row; F1

**Defect.** Nothing made a second delivery Claim for the same obligation,
Window and pass non-conforming once the first had expired. The limits of one
Claim per pass, and refiling only after withdrawal, were written for credit
Claims alone.

**Disposition.** Corrected in Version 1.2. W+7 row: only the first delivery
Claim the named party files for the obligation opens a Case.

### 45 · Annex 5

**Defect.** Of the four evaluation outputs, the standard stated conditions
only for requires-review and never said when the other three are returned.

**Disposition.** Corrected in Version 1.2. Annex 5: the evaluation output is
requires-review where Annex 2.1.4 applies; its values in every other case are
the reference implementation's, and no clause of the standard rests on them.

### 46 · I.1.5

**Defect.** The credit Claim computation ignored the terminal state of the
adjusted Claim, so an adjusted Claim that ended rejected and was never paid
was still deducted at its quote, and the amount could come out negative.

**Disposition.** Corrected in Version 1.2. I.1.4 keeps the quote-based
computation, and the agreement's terms identified under A7 set the amount
against what was paid on the adjusted Claim.

### 47 · I.1.5

**Defect.** Nothing made a credit Claim that adjusts another credit Claim
non-conforming, so where a Profile stated further passes the same difference
could be claimed along two sequences.

**Disposition.** Corrected in Version 1.2. I.1.4: a credit Claim whose
adjusted Claim is itself a credit Claim is not conforming.

### 48 · I.1.5

**Defect.** The standard did not say who may withdraw a credit Claim or until
when, and a withdrawn credit Claim could be refiled at any time before W+90.

**Disposition.** Corrected in Version 1.2. I.1.4: only its claimant may
withdraw a credit Claim, and only before any Decision on it is filed and
before its review deadline.

### 49 · Annex 5

**Defect.** The syntax of a credit Claim identifier did not say whether its
numbers may begin with 0, such as W+05 or a sequence number 02, so one Claim
could be written two ways.

**Disposition.** Corrected in Version 1.2. Annex 5: neither the sequence
number nor the digits of the pass identifier begin with 0, so the identifier
parses one way.

### 50 · J4; I.2.1

**Defect.** J4 and I.2.1 compared failures to file under H1 with the
unresolved ceiling without saying whether Windows, intervals or shares are
compared. Under UC-04 there is no ceiling to exceed, and the parameter of
UC-02 is a count of intervals.

**Disposition.** Corrected in Version 1.2. J4 and I.2.1 are deleted. The
Period Attestation under I.2 identifies every Window in which the Filing Plan
was not followed.

### 51 · Annex 2.6.3

**Defect.** The paragraph after Annex 2.6.3 said SB-05 cannot be used to
deliver less, while A8 has no field for the number of accelerators on a
subject and SB-05 compares A8 fields only.

**Disposition.** Corrected in Version 1.2. The sentence is deleted. The
comparison rule of SB-05 is unchanged.

### 52 · 7.0.2

**Defect.** The standard did not say whether a reading taken with a coverage
factor k other than the procedure's is admissible, or how its uncertainty is
compared with the bound.

**Disposition.** Corrected in Version 1.2. 7.0.2: U/median is compared at the
k the procedure states, recomputed from the filed runs where a receipt used
another k. Beyond the bound, 7.0.3 applies and there is no reading.

### 53 · 7.0.3

**Defect.** The standard did not define evidence that a field was below its
floor, and 7.0.3 said that a failed run is never such evidence without saying
what is.

**Disposition.** Corrected in Version 1.2. The closing words of 7.0.3 are
deleted. B8.5 decides, by the Profile's Annex 2.8 selection, what a reading
establishes about a floor.

### 54 · Annex 2.8 CD-04

**Defect.** CD-04 said only that the guard band keeps the probability of a
wrong decision within a stated value. It did not say on which side of the
limit the band lies, or how a reading in each region is decided.

**Disposition.** Corrected in Version 1.2. CD-04 is deleted. A guard band
derived from a maximum risk is stated as a parameter of CD-02 or CD-03.

### 55 · A8.10

**Defect.** A8.10 said every field carries a verifiability tier, and gave
neither the tier of a field outside its table nor the route by which such a
field enters the record.

**Disposition.** Corrected in Version 1.2. Annex 8.1 row 21: a departure under
G8 adds no field to a Grade Class, and a Profile that adds one cannot be
armed.

### 56 · Annex 8; K4

**Defect.** The standard said cannot be armed only where it named the case. It
did not say whether a Profile can be armed when it breaks a MUST that no row
of Annex 8.1 carries, such as naming the holder of a value withheld under K4,
or fills a row outside its Drawn from column.

**Disposition.** Corrected in Version 1.2. Annex 8: a Profile missing a
required row, filling a row outside its Drawn from column, or breaking any
other MUST placed on a Profile cannot be armed. Row 37 carries the
requirements of K4.

### 57 · I.1.4

**Defect.** I.1.4 placed further passes between the Claim and quantity
finality without saying whether either end is included, or whether a Profile
dating a pass outside that span can be armed.

**Disposition.** Corrected in Version 1.2. I.1.3: a pass falls after the
delivery Claim is filed and no later than quantity finality, and a Profile
that dates one outside that span cannot be armed.

### 58 · G10; A10

**Defect.** G10 did not say whether a Plan modification filed inside a Window,
a Plan digest that changed without a new effective Window, or a term changed
after the A10 commitment takes effect at the next Window, takes no effect, or
makes the record not conforming.

**Disposition.** Corrected in Version 1.2. G10 states each kind of change with
its effect, and until a change takes effect the party files under the Plan in
force. A10: a term changed after the commitment takes no effect on a Window it
governs.

### 59 · L4; Annex 2.1.3

**Defect.** The standard protected only closed Windows from the retirement of
a registry entry, and did not say when retirement takes effect or whether it
reaches a Window in progress or one opening later.

**Disposition.** Corrected in Version 1.2. L4: retirement takes effect when
published and reaches only Profiles armed after it, which must not name the
entry.

### 60 · Annex 5

**Defect.** The canonical JSON of Annex 5 did not say how numbers other than
integers are written, by what order keys are sorted, or whether escapes use
upper or lower case.

**Disposition.** Corrected in Version 1.2. Annex 5: keys are sorted by code
point, a character outside U+0020 to U+007E is escaped by JSON's two-character
escape where one exists and otherwise as lower-case \uXXXX, and numbers are
integers written without fraction or exponent.

### 61 · Annex 5

**Defect.** Annex 5 gave no head and no path for a spot-check log with no
leaves.

**Disposition.** Corrected in Version 1.2. The sentence of Annex 5 on
spot-check membership proofs is deleted, and the standard no longer specifies
the spot-check tree.

### 62 · K3

**Defect.** K3 said a record disclosed under an access grant remains checkable
without either party's cooperation, which a record carrying only the digest of
a confidential value is not.

**Disposition.** Corrected in Version 1.2. Those words are deleted. K3
requires the record to carry its signatures and inclusion proofs, and whether
it recomputes is a question for 4.6.

### 63 · A10; Annex 8.1 row 12; Annex 5

**Defect.** A10 and Annex 8.1 row 12 placed A1 through A9 under the
commitment, while Annex 5 placed the whole Profile and its version under it.

**Disposition.** Corrected in Version 1.2. A10 and row 12: the commitment
covers the Profile and the digest of its version's text.

### 64 · Annex 8.1 row 26

**Defect.** Row 26, Challenge policy and post-finality window, was required,
and appeared nowhere else in the standard.

**Disposition.** Corrected in Version 1.2. The row is deleted, and the opening
of Annex 8 is rewritten to match.

### 65 · 0.1; A10

**Defect.** Nothing in the record fixed the digest of the standard's text, so
a contract adopting the standard by the sentence in 0.1 relied on the digest
the maintainer published.

**Disposition.** Corrected in Version 1.2. A10 and Annex 8.1 row 12: the
Profile carries the digest of its version's text under the A10 commitment.

### 66 · Annex 5

**Defect.** Annex 5 made validation against the schemas a condition of
conformance, while the parameter_pack schema requires thirteen parameters the
standard never names.

**Disposition.** Corrected in Version 1.2. Annex 5: a parameter in
parameter_pack that this standard does not name decides no outcome under it.

### 67 · Annex 5

**Defect.** In the spot-check tree an odd last node was paired with itself,
and the leaf count a proof carries was not bound by the head, so a tree of
three leaves and a tree of four repeating its last leaf had the same head.

**Disposition.** Corrected in Version 1.2. The sentence is deleted, as entry
61 records.

### 68 · K3

**Defect.** The standard did not require a party disclosing under an access
grant to pass on later disputes, corrections and credit Claims, and gave the
reader no way to check that it holds the latest head.

**Disposition.** Corrected in Version 1.2. K3: an access grant names whether
later filings for its Windows reach the grantee.

### 69 · E2; Annex 5

**Defect.** Annex 5 described the log of E2 as a settlement log opened for
each Case, while the measurements due at W+2 and the A10 commitment precede
any Case, so the standard did not say which head proves their filing dates.

**Disposition.** Corrected in Version 1.2. Annex 5: the head is the signed
head over the log of the operator that Annex 8.1 row 28 names.

### 70 · I.1.5

**Defect.** Where the quantity of the pass a credit Claim rests on was
undecided among candidate figures, the remedy quote was not unique and the
amount under I.1.5 was undefined.

**Disposition.** Corrected in Version 1.2. I.1.4: where either pass's quantity
is undecided among candidate figures, the amount and the party it favours
follow the agreement's terms identified under A7.
