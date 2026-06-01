# Exercises

[Previous: Glossary](10-glossary.md) | [Next: References](12-references.md)

These exercises are grouped by difficulty. Hints are included, but full solutions are intentionally omitted unless marked.

## Beginner

### Exercise 1: Modulo-2 Arithmetic

Compute:

\[
1\oplus 1,\quad 1\oplus 0,\quad 0\oplus 0,\quad 1\oplus 1\oplus 1
\]

Hint: XOR is addition modulo 2.

### Exercise 2: Manual Encoding for \(N=4\)

Use:

\[
G_4 =
\begin{bmatrix}
1 & 0 & 0 & 0 \\
1 & 1 & 0 & 0 \\
1 & 0 & 1 & 0 \\
1 & 1 & 1 & 1
\end{bmatrix}
\]

Compute \(x=uG_4\) for:

\[
u=(0,0,1,1)
\]

Hint: Work column by column, using XOR.

### Exercise 3: Identify Frozen and Information Positions

Let \(N=8\), \(K=4\), and suppose:

\[
\mathcal{A}=\{3,5,6,7\}
\]

List the frozen set \(\mathcal{F}\).

Hint: Frozen positions are all positions not in \(\mathcal{A}\).

### Exercise 4: Build \(u\)

Using the information set \(\mathcal{A}=\{3,5,6,7\}\) and message:

\[
m=(1,0,1,1)
\]

construct \(u\) assuming frozen bits are zero and message bits are inserted in increasing index order.

Hint: Start with eight zeros.

## Intermediate

### Exercise 5: Implement a Polar Encoder

Write a function `polar_encode(u)` that implements the in-place XOR butterfly encoder from [03-encoding.md](03-encoding.md).

Hint: Test it for \(N=4\) against the worked matrix example.

### Exercise 6: Noiseless End-to-End Test

Build a simulation with:

- random messages;
- frozen-bit insertion;
- polar encoding;
- noiseless BPSK observations;
- SC decoding.

Verify that the decoded message equals the original message.

Hint: Use very large magnitude LLRs such as \(+100\) for bit 0 and \(-100\) for bit 1.

### Exercise 7: LLR Sign Convention

Assume BPSK mapping \(0\mapsto +1\), \(1\mapsto -1\), and AWGN variance \(\sigma^2\). Derive:

\[
L = \frac{2y}{\sigma^2}
\]

Hint: Write the Gaussian conditional densities for \(y\mid x=+1\) and \(y\mid x=-1\), then take the log ratio.

### Exercise 8: Implement a Basic SC Decoder

Implement recursive SC decoding using the min-sum approximation:

\[
f(a,b) \approx \operatorname{sign}(a)\operatorname{sign}(b)\min(|a|,|b|)
\]

and:

\[
g(a,b,\hat{u}) = b + (1-2\hat{u})a
\]

Hint: First implement the recursion for \(N=2\), then generalize.

### Exercise 9: Compare BER and BLER

Run a simulation and record both BER and BLER. Find a case where BER is small but BLER is noticeably larger.

Hint: A block error occurs if any message bit in the block is wrong.

## Advanced

### Exercise 10: Investigate Frozen-Set Quality

For fixed \(N\) and \(K\), compare two frozen sets:

- one based on a reliability sequence;
- one chosen randomly.

Plot BER or BLER versus SNR.

Hint: Keep the encoder, decoder, modulation, and random seed strategy unchanged.

### Exercise 11: Conceptual SC versus SCL

For a small code, manually draw a decision tree for two information bits. Show how SC chooses one path while SCL with \(L=2\) can keep two paths.

Hint: Assign artificial path metrics to make the example concrete.

### Exercise 12: Add CRC-Aided Selection

Modify a toy list decoder so candidate messages are checked against a small parity or CRC-like rule.

Hint: You can start with a single parity-check bit before implementing a real CRC.

### Exercise 13: Simulate BER versus SNR

For \(N=64\), \(K=32\), simulate BER and BLER over several SNR values.

Hint: Use enough frames to make the curves stable. At high SNR, errors are rare, so you need more frames.

### Exercise 14: Quantized LLRs

Repeat a simulation using quantized LLRs, such as 4-bit or 6-bit signed values.

Hint: Clip large LLR magnitudes before quantization.

### Exercise 15: Research Reading Exercise

Read Arikan's original polar-code paper and identify:

- the definition of channel polarization;
- the main capacity-achieving theorem;
- the decoding algorithm used.

Hint: Do not try to understand every proof detail on the first pass. Focus on the problem, construction, and result.

## Short Summary

The best way to learn polar codes is to alternate between hand calculations and implementation. If a simulation fails, return to \(N=4\) and verify every bit.

> **Check your understanding:** Which exercise would most likely reveal an indexing mismatch between encoder and decoder?

