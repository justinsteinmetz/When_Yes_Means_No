https://justinsteinmetz.github.io/When_Yes_Means_No/


# When Yes Means No

**An identity instrument for Grades 11–12.**

> What conditions produce a yes that means something else.

---

## Concept

WHEN YES MEANS NO examines the gap between performed willingness and actual desire or feeling. It is not a consent education tool. It is an identity instrument that treats the performed yes as a structural phenomenon — produced by social scripts, power dynamics, gender norms, and the unequal distribution of the cost of refusal.

The central argument, grounded in sociological research on consent (Lévy-Guillain/Sciences Po; Amnesty International; consent.gov.au): the difficulty saying no is not a personal weakness. It is learned. It is unevenly distributed. And the conditions that produce a performed yes — social pressure, relational care, anticipated cost, gendered expectation — operate across many contexts, not only sexual ones.

The instrument moves from low-stakes social situations toward more intimate ones. The sixth and final prompt turns outward: have you ever been the person who misread someone else's yes?

---

## The engine

**Performed/Actual gap mechanic.** Six prompts, two sides each — what the student said, did, or showed (Performed), and what they actually felt or wanted (Actual). Both sides required before proceeding. The gap between the two is submitted to the model as the primary evidence.

This is the gap engine from *SELF v SELFIE*, reoriented from curated/private self to enacted/actual willingness.

---

## The six prompts

| # | Label | What it asks |
|---|---|---|
| 1 | A social agreement | A low-stakes moment of agreeing to something unwanted |
| 2 | Staying past the point | What kept them in a situation past the point of wanting to leave |
| 3 | Performed enthusiasm | A moment of performing willingness, agreement, or enthusiasm they didn't feel |
| 4 | The cost of no | Something agreed to because refusal felt too costly |
| 5 | The no you didn't say | What stopped them from refusing — the specific mechanism |
| 6 | The yes you misread | Whether they have ever been the reader of someone else's gap |

**The sixth prompt is the most important.** It asks the student to examine whether they have been the person who took a yes at face value when it may not have been fully meant. The AI reading gives this prompt special weight: does the student show genuine reflection, or deflection?

**The sequence matters.** Prompts 1–3 establish the pattern in low-stakes territory. Prompts 4–5 name the mechanism directly. Prompt 6 turns the instrument outward — students cannot only be the subject of performed yeses; they are also, sometimes, the person who creates conditions that produce them.

---

## The safeguarding overlay

A full-page overlay appears before the intro screen and cannot be bypassed. It contains:

- What the instrument asks
- An explicit statement that vague or incomplete answers are fine and stopping is always an option
- A plain note about support services for anyone who finds the material distressing

Two buttons: *I understand — continue* or *Leave this page.*

This is not decoration. The instrument touches territory where some students will have real experiences of coercion, pressure, or confusion. The overlay establishes the frame and the exit before anything else.

---

## The reading

After all six prompts, the model reads the full gap record as structural analysis.

**What the model reads for:**

**Pattern** — what conditions appear consistently across the six gaps? Social cost, relational care, fear of conflict, gendered expectation? The pattern names the structural mechanism, not the individual failure.

**The sixth prompt** — does the student show genuine reflection on what they missed or didn't look for in someone else's yes? Or does it read as deflection? Named directly either way.

**Absence** — [empty] and [minimal] answers on prompts 5 and 6 are primary data. What cannot or will not be named is worth naming.

**The structural argument** — the reading does not treat performed yeses as personal weakness. It names the conditions that produced them as they appear in this specific record.

**Output:** headline (4–8 words, names the structural pattern), reading (200–270 words), signature (one sentence grounded in at least two prompts), three discussion questions derived from the pattern, the sixth prompt, and the gap between imagined and real cost of refusal.

**The model is explicitly prohibited from:** using therapeutic language (healing, journey, authentic self, trauma response, boundaries), moralising, reassuring, or praising. It may note once, plainly and without alarm, that support is available if the student's answers indicate genuine distress.

---

## Safeguarding and facilitation

**This instrument requires careful introduction.** Before students open it, the teacher should establish:
- The result is entirely private
- No one will be asked to share
- Stopping at any point is always legitimate
- The instrument is about structural conditions, not personal failure or confession

**The safeguarding overlay does not replace teacher framing.** It supplements it.

**Do not use this instrument in a class where trust has not been established.** The Danger Room and Who Are You, Really can be used in most Grades 11–12 contexts with reasonable preparation. WHEN YES MEANS NO requires more.

**Mandatory reporting obligations apply.** If a student discloses something in person — before, during, or after this instrument — that triggers mandatory reporting requirements, those obligations apply regardless of the digital context.

---

## Pedagogical notes

**The instrument deliberately avoids the sexual register in its prompts.** The questions operate across social, relational, and intimate contexts. Students bring their own experience to the framing. This protects students who are not ready to engage with sexual specificity while keeping the conceptual territory available to those who are.

**The sixth prompt is where the instrument becomes genuinely demanding.** Students who can only see themselves as subjects of coercion — never as the person who failed to read someone else's hesitation — are in the most comfortable position the instrument allows. That comfort is the thing the prompt is designed to disturb.

**Discussion entry points** (generic — the instrument generates three specific ones per student):
- "Which prompt was hardest to fill in the Actual column? Why that one?"
- "What came up for you in prompt 6 — the outward turn?"
- "The reading named a structural condition. Do you recognise it — and where else does it appear in your life?"
- "Is the cost of refusal equally distributed? Who pays it more?"

---

## Research grounding

The instrument is grounded in four sources:

- **Lévy-Guillain (Sciences Po/Ined)** — socialisation into limited freedom; why women find it more difficult to identify desire and say no; the structural rather than individual nature of coerced consent
- **Amnesty International — *Let's Talk About YES*** — the FREELY/INFORMED/SPECIFIC/REVERSIBLE/ENTHUSIASTIC framework; the distinction between absence of refusal and presence of enthusiasm
- **consent.gov.au** — the five dimensions of consent; the explicit statement that not saying no is not the same as saying yes; freezing as non-consent
- **NSW Health / Play Safe Pro** — pedagogy for young people; the role of coercion scripts; practical framing for classroom contexts

The instrument does not reproduce or quote these sources. It uses their conceptual framework to design the prompts and the AI reading instructions.

---

## Abitur Themenfeld relevance

| Themenfeld | Angle |
|---|---|
| The Individual & Society | Gender, identity, conformity, social scripts, the construction of the self through performance; the unequal distribution of the cost of refusal |

WHEN YES MEANS NO is the instrument in this suite most directly addressing the gender dimension of the Individual & Society Themenfeld, which the KMK document names explicitly: *"gender issues"* under *"chances and challenges for society: ethnic, cultural and social diversity."*

---

## Technical architecture

Uses the same Cloudflare Worker proxy as the rest of the suite.

```javascript
const PROXY = "https://anthropic-proxy.justin-steinmetz.workers.dev";
```

One API call per session — the gap reading at the end. See the *Who Are You, Really* README for full Worker deployment instructions.

### Deployment

Single HTML file. No dependencies, no build step. Rename `when-yes-means-no.html` to `index.html` and push to a GitHub Pages repository.

The safeguarding overlay is part of the HTML and cannot be disabled without editing the source. This is intentional.
