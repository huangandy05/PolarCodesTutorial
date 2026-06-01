# Glossary

[Previous: Research Directions](09-research-directions.md) | [Next: Exercises](11-exercises.md)

## Polar Code

A binary error-correcting code built from a recursive transform that polarizes synthetic channels into reliable and unreliable positions.

## Channel Polarization

The phenomenon where recursive channel combining and splitting turns many identical physical channel uses into synthetic channels that become either very reliable or very unreliable as block length grows.

## Synthetic Channel

An artificial bit-channel created by the polar transform and decoding order. It is not a separate physical channel; it describes how reliably a particular \(u_i\) can be decoded.

## Frozen Bit

A bit placed in an unreliable position of \(u\), usually fixed to 0 and known to both encoder and decoder.

## Information Bit

A message bit placed in a reliable position of \(u\).

## Generator Matrix

A matrix used to map an input vector to a codeword. For polar codes in this wiki:

\[
G_N = F^{\otimes n}
\]

and:

\[
x = uG_N
\]

## Kronecker Product

A matrix operation that builds larger matrices from smaller matrices. Polar generator matrices are built by repeated Kronecker products of the kernel \(F\).

## SC Decoding

Successive cancellation decoding. A low-complexity polar decoding algorithm that estimates bits of \(u\) one at a time.

## SCL Decoding

Successive cancellation list decoding. A decoder that keeps multiple candidate paths to reduce the risk of early wrong decisions.

## CRC-Aided Decoding

A method that appends CRC bits before encoding and uses the CRC after list decoding to choose the most plausible valid candidate.

## LLR

Log-likelihood ratio. For a bit \(b\):

\[
L = \log \frac{P(y\mid b=0)}{P(y\mid b=1)}
\]

Under the convention used here, positive LLR favors bit 0.

## BER

Bit error rate. The fraction of decoded information bits that are wrong.

## BLER

Block error rate. The fraction of decoded message blocks that contain at least one bit error.

## AWGN

Additive white Gaussian noise. A channel model where independent Gaussian noise is added to transmitted symbols.

## BPSK

Binary phase-shift keying. A modulation scheme that maps binary bits to two real or complex symbols, often \(0\mapsto +1\) and \(1\mapsto -1\).

## Code Rate

The ratio of information bits to transmitted coded bits:

\[
R = \frac{K}{N}
\]

## Channel Capacity

The maximum reliable information rate of a channel, usually measured in bits per channel use.

## Bhattacharyya Parameter

A channel reliability measure often denoted \(Z(W)\). Smaller values indicate more reliable channels.

## Density Evolution

A method for tracking message probability distributions through recursive coding or decoding operations.

## Gaussian Approximation

A practical method that approximates LLR distributions as Gaussian to estimate synthetic-channel reliability.

## Rate Matching

Adapting a code of natural length \(N\) to a required transmitted length using operations such as puncturing, shortening, or repetition.

## Short Summary

These terms are the core vocabulary for reading polar-code papers and implementations. When confused, return to the distinction between \(u\), \(x\), physical channels, and synthetic channels.

