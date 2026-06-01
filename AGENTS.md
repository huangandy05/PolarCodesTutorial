You are an expert technical educator and wiki author. Create a comprehensive Markdown wiki on **polar codes** with a strong focus on pedagogy, clarity, and progressive learning.

## Goal

Write a self-contained learning resource that helps a motivated reader understand:

- what polar codes are,
    
- why they matter,
    
- how they work mathematically,
    
- how they are implemented,
    
- how they are decoded,
    
- how they are used in practice,
    
- and how to continue researching them.
    

Assume the reader has basic knowledge of probability, linear algebra, binary arithmetic, and digital communications, but is new to polar codes.

## Output Format

Produce a Markdown wiki with multiple linked pages or sections. Use clear headings, internal links, diagrams in Mermaid where helpful, equations in LaTeX, examples, pseudocode, and implementation notes.

The wiki should be structured as if it will live in a GitHub repository or documentation site.

## Style Requirements

Write pedagogically. Prioritize intuition before formalism.

Use:

- simple explanations before equations,
    
- small worked examples,
    
- recurring mental models,
    
- “common confusion” callouts,
    
- implementation warnings,
    
- short summaries at the end of major sections,
    
- glossary entries for important terms,
    
- suggested exercises,
    
- references for deeper reading.
    

Avoid assuming the reader already understands coding theory jargon. Define terms when first introduced.

## Required Wiki Structure

Create the following Markdown pages or sections:

### 1. `index.md` — Overview and Learning Path

Include:

- what polar codes are,
    
- why they are important,
    
- where they are used,
    
- prerequisites,
    
- suggested learning path,
    
- repository/wiki map.
    

### 2. `01-intuition.md` — Intuition Behind Polar Codes

Explain:

- channel coding in plain language,
    
- noisy channels,
    
- the idea of channel capacity,
    
- the high-level idea of channel polarization,
    
- why some synthetic channels become reliable while others become unreliable,
    
- frozen bits versus information bits.
    

Use analogies, but clearly mark where the analogy stops being exact.

### 3. `02-mathematical-foundations.md` — Mathematical Foundations

Cover:

- binary linear block codes,
    
- generator matrices,
    
- modulo-2 arithmetic,
    
- Kronecker products,
    
- recursive structure,
    
- the polar transform,
    
- code length (N = 2^n),
    
- code dimension (K),
    
- code rate (R = K/N).
    

Include a worked example for (N = 4) or (N = 8).

### 4. `03-encoding.md` — Polar Encoding

Explain:

- construction of vector (u),
    
- information-bit positions,
    
- frozen-bit positions,
    
- generator matrix (G_N = F^{\otimes n}),
    
- encoding rule (x = uG_N),
    
- butterfly-style implementation,
    
- (O(N \log N)) encoding complexity.
    

Include pseudocode for an encoder using XOR operations.

### 5. `04-channel-construction.md` — Choosing Frozen Bits

Explain:

- why frozen-bit selection matters,
    
- reliability ordering,
    
- Bhattacharyya parameters,
    
- Gaussian approximation,
    
- density evolution,
    
- universal reliability sequences,
    
- finite-length effects.
    

Include a beginner-friendly explanation of why this is one of the hardest practical parts.

### 6. `05-decoding-sc.md` — Successive Cancellation Decoding

Explain:

- decoding as estimating bits one at a time,
    
- frozen-bit decisions,
    
- information-bit decisions,
    
- likelihoods and log-likelihood ratios,
    
- recursive decoding tree,
    
- (f) and (g) update functions,
    
- min-sum approximation,
    
- hard decisions.
    

Include pseudocode for a basic SC decoder.

### 7. `06-decoding-scl.md` — List and CRC-Aided Decoding

Explain:

- limitations of SC decoding,
    
- successive cancellation list decoding,
    
- list size (L),
    
- path metrics,
    
- pruning,
    
- CRC-aided SCL decoding,
    
- why CRC improves practical performance.
    

Include a small conceptual example showing how multiple decoding paths are maintained.

### 8. `07-implementation-guide.md` — Implementation Guide

Provide a practical guide to implementing a simple polar code simulation.

Include:

- choosing (N) and (K),
    
- selecting frozen positions,
    
- generating random messages,
    
- encoding,
    
- BPSK modulation,
    
- AWGN channel,
    
- LLR computation,
    
- SC decoding,
    
- BER and BLER measurement.
    

Include clean pseudocode and implementation pitfalls.

Mention common mistakes such as:

- using normal addition instead of XOR,
    
- inconsistent bit ordering,
    
- wrong frozen-bit index convention,
    
- incorrect LLR sign convention,
    
- forgetting that encoder and decoder need the same frozen set.
    

### 9. `08-polar-codes-in-5g.md` — Polar Codes in Practice

Explain:

- why polar codes are relevant in modern communication systems,
    
- high-level role in 5G NR,
    
- control-channel usage,
    
- rate matching,
    
- interleaving,
    
- CRC-aided decoding,
    
- practical constraints such as latency and hardware complexity.
    

Keep this section accessible and avoid turning it into a standards document.

### 10. `09-research-directions.md` — Further Research Directions

Organize research directions into categories:

- theory,
    
- code construction,
    
- decoding algorithms,
    
- hardware implementation,
    
- finite-length performance,
    
- machine learning aided decoding,
    
- quantum polar codes,
    
- non-binary and multi-kernel polar codes,
    
- applications beyond 5G.
    

For each direction, include:

- a short explanation,
    
- why it matters,
    
- suggested keywords to search,
    
- one or two starter questions.
    

### 11. `10-glossary.md` — Glossary

Define terms including:

- polar code,
    
- channel polarization,
    
- synthetic channel,
    
- frozen bit,
    
- information bit,
    
- generator matrix,
    
- Kronecker product,
    
- SC decoding,
    
- SCL decoding,
    
- CRC-aided decoding,
    
- LLR,
    
- BER,
    
- BLER,
    
- AWGN,
    
- BPSK,
    
- code rate,
    
- channel capacity.
    

### 12. `11-exercises.md` — Exercises

Create exercises at three levels:

- beginner,
    
- intermediate,
    
- advanced.
    

Include exercises such as:

- manually encode a small vector for (N = 4),
    
- identify frozen and information positions,
    
- implement a polar encoder,
    
- implement an SC decoder,
    
- compare SC and SCL decoding conceptually,
    
- simulate BER versus SNR,
    
- investigate the effect of changing frozen positions.
    

Provide short hints, but not full solutions unless explicitly marked.

### 13. `12-references.md` — References and Reading List

Include references to:

- Arıkan’s original polar code paper,
    
- introductory tutorials,
    
- lecture notes,
    
- 5G NR polar code resources,
    
- implementation-focused resources,
    
- advanced research surveys.
    

For each reference, briefly explain what it is useful for.

## Pedagogical Features to Include

Throughout the wiki, include callout blocks such as:

```markdown
> **Key idea:** ...
```

```markdown
> **Common confusion:** ...
```

```markdown
> **Implementation warning:** ...
```

```markdown
> **Research note:** ...
```

```markdown
> **Check your understanding:** ...
```

## Technical Accuracy Requirements

Ensure the wiki correctly distinguishes between:

- the information vector (u) and encoded vector (x),
    
- information bits and frozen bits,
    
- physical channels and synthetic channels,
    
- SC and SCL decoding,
    
- BER and BLER,
    
- theoretical capacity-achieving behavior and finite-length practical performance.
    

When presenting formulas, define every symbol before using it heavily.

## Final Output Requirements

Return the full wiki content in Markdown.

Use clear file boundaries like:

```markdown
# index.md
...
# 01-intuition.md
...
```

Make the result ready to copy into a GitHub repository.

End with a short “Suggested Next Steps” section explaining how the reader should use the wiki.
