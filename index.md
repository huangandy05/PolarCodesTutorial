# Polar Codes: Overview and Learning Path

Welcome to this tutorial wiki on **polar codes**. It is designed for a motivated reader who knows the basics of probability, linear algebra, binary arithmetic, and digital communications, but is new to coding theory beyond the general idea of error correction.

Polar codes are error-correcting codes that add carefully structured redundancy to a message so that the receiver can recover the message even after noise corrupts the transmission. Their central idea is **channel polarization**: by combining many uses of a noisy channel in a recursive way, polar codes create a set of new, artificial, or **synthetic**, bit-channels. Some of these synthetic channels become very reliable, while others become very unreliable.

The encoder sends information bits through the reliable synthetic channels and fixes the unreliable ones to known values called **frozen bits**.

> **Key idea:** Polar codes do not try to make every bit equally protected. They intentionally separate bit positions into "good" and "bad" synthetic channels, then use only the good ones for information.

## Why Polar Codes Matter

Polar codes are important because they were the first family of codes proven to achieve the capacity of a broad class of channels using practical, structured encoding and decoding algorithms. Here, **capacity** means the highest rate at which information can be sent over a channel with arbitrarily low error probability, in the limit of large block length.

They also matter in practice:

- Polar codes are used in **5G New Radio (5G NR)** control channels.
- They have a clean recursive mathematical structure.
- They connect theory, algorithms, and hardware implementation in a unusually direct way.
- Their modern decoders, especially **CRC-aided successive cancellation list decoding**, perform very well at short and moderate block lengths.

> **Common confusion:** "Capacity-achieving" is an asymptotic statement. It means performance approaches capacity as the block length grows under suitable construction and decoding assumptions. It does not mean every short polar code automatically outperforms every other code.

## Where Polar Codes Are Used

Polar codes are especially relevant in systems that need reliable transmission of relatively short control messages. Their most famous practical deployment is in 5G NR, where they are used for selected control-channel coding tasks. They are also studied for storage, satellite links, quantum communication, and future wireless systems.

## Prerequisites

You will get the most from this wiki if you are comfortable with:

- binary arithmetic, especially XOR and modulo-2 addition;
- vectors and matrices;
- probability distributions and likelihoods;
- basic digital modulation such as BPSK;
- the idea of a noisy communication channel;
- reading simple pseudocode.

You do not need to know advanced coding theory before starting.

## Suggested Learning Path

1. Start with [01-intuition.md](01-intuition.md) to build the mental model.
2. Read [02-mathematical-foundations.md](02-mathematical-foundations.md) to understand the transform.
3. Work through [03-encoding.md](03-encoding.md) and manually encode a small example.
4. Read [04-channel-construction.md](04-channel-construction.md) to learn why frozen-bit selection matters.
5. Study [05-decoding-sc.md](05-decoding-sc.md), then [06-decoding-scl.md](06-decoding-scl.md).
6. Use [07-implementation-guide.md](07-implementation-guide.md) to build a small simulation.
7. Read [08-polar-codes-in-5g.md](08-polar-codes-in-5g.md) for practical context.
8. Explore [09-research-directions.md](09-research-directions.md) and [12-references.md](12-references.md) when you are ready to go deeper.

## Wiki Map

- [01-intuition.md](01-intuition.md): Intuition behind noisy channels, capacity, polarization, frozen bits, and information bits.
- [02-mathematical-foundations.md](02-mathematical-foundations.md): Binary linear codes, generator matrices, Kronecker products, and the polar transform.
- [03-encoding.md](03-encoding.md): How to form the input vector `u`, compute `x = uG_N`, and implement encoding efficiently.
- [04-channel-construction.md](04-channel-construction.md): How reliable positions are chosen.
- [05-decoding-sc.md](05-decoding-sc.md): Successive cancellation decoding, LLRs, recursive updates, and hard decisions.
- [06-decoding-scl.md](06-decoding-scl.md): List decoding, path metrics, pruning, and CRC-aided decoding.
- [07-implementation-guide.md](07-implementation-guide.md): End-to-end simulation with BPSK, AWGN, LLRs, BER, and BLER.
- [08-polar-codes-in-5g.md](08-polar-codes-in-5g.md): Accessible overview of polar codes in practical systems.
- [09-research-directions.md](09-research-directions.md): Open research areas and starter questions.
- [10-glossary.md](10-glossary.md): Definitions of key terms.
- [11-exercises.md](11-exercises.md): Exercises at beginner, intermediate, and advanced levels.
- [12-references.md](12-references.md): Reading list and references.

## A Recurring Mental Model

Imagine a noisy road network with many routes. The polar transform reorganizes those routes so that some become excellent highways and others become terrible muddy tracks. You send valuable traffic on the highways and place predictable dummy traffic on the muddy tracks.

Where the analogy stops: real polar codes do not physically build separate roads. They create synthetic channels through algebraic combinations of bits and recursive probabilistic decoding.

## Short Summary

Polar codes are structured error-correcting codes built from a recursive transform. They work by converting many identical physical channel uses into synthetic channels of unequal reliability. Information bits go into the reliable positions, frozen bits go into the unreliable positions, and a decoder uses the known structure to recover the message.

> **Check your understanding:** Before continuing, try to explain in one sentence why a polar code has both information bits and frozen bits.

