# References and Reading List

[Previous: Exercises](11-exercises.md) | [Back to README](README.md)

This page lists starting points for deeper study. Some references are theoretical, while others are better for implementation or standards context.

## Foundational Paper

### Erdal Arikan, "Channel Polarization: A Method for Constructing Capacity-Achieving Codes for Symmetric Binary-Input Memoryless Channels"

This is the original polar-code paper. It introduces channel polarization, the polar transform, and successive cancellation decoding.

Useful for:

- understanding the original theoretical contribution;
- seeing how polarization is formalized;
- learning the asymptotic capacity-achieving result.

Suggested search terms: `Arikan channel polarization 2009 polar codes`.

## Introductory Tutorials

### Tutorial Articles on Polar Codes

Look for tutorial papers and survey introductions that explain polar codes with small examples before proving theorems.

Useful for:

- bridging from digital communications to coding theory;
- seeing examples of encoding and decoding;
- learning common notation.

Suggested search terms: `polar codes tutorial`, `introduction to polar codes`, `polar codes explained`.

## Lecture Notes

### University Lecture Notes on Coding Theory and Polar Codes

Many coding theory courses include one or two lectures on polar codes. Lecture notes often contain concise derivations and worked examples.

Useful for:

- seeing the material in a teaching sequence;
- practicing mathematical derivations;
- finding small exercises.

Suggested search terms: `polar codes lecture notes`, `channel polarization lecture notes`, `coding theory polar codes`.

## 5G NR Resources

### 3GPP 5G NR Physical Layer Specifications

The official 5G NR specifications define how polar codes are used in the standard, including rate matching, interleaving, CRCs, and channel-specific processing.

Useful for:

- standards-compliant implementation;
- understanding practical engineering layers;
- checking exact indexing and interleaver rules.

Suggested search terms: `3GPP TS 38.212 polar codes`.

### Explanatory 5G Polar-Code Articles

Vendor white papers, tutorials, and engineering articles can provide accessible explanations of why polar codes were selected for certain 5G control channels.

Useful for:

- high-level practical motivation;
- understanding deployment context;
- connecting polar codes to LDPC and other channel codes.

Suggested search terms: `5G NR polar codes control channel CRC aided SCL`.

## Implementation-Focused Resources

### Open-Source Polar-Code Simulators

Search for small educational implementations before diving into optimized libraries.

Useful for:

- checking encoder and decoder conventions;
- comparing simulation results;
- learning test-vector strategies.

Suggested search terms: `polar code SC decoder Python`, `polar code MATLAB implementation`, `polar code simulation AWGN`.

> **Implementation warning:** Do not mix code snippets from different implementations unless you understand their indexing, bit-reversal, frozen-set, and LLR conventions.

### AFF3CT and Other Communication-System Libraries

Advanced simulation frameworks often include polar codes and multiple decoders.

Useful for:

- benchmarking;
- comparing decoder variants;
- studying optimized implementations.

Suggested search terms: `AFF3CT polar codes`, `polar code list decoder implementation`.

## Advanced Research Surveys

### Surveys on Polar-Code Construction and Decoding

Survey papers collect developments after Arikan's original work, including list decoding, CRC-aided decoding, construction methods, and hardware.

Useful for:

- understanding the research landscape;
- finding references by topic;
- identifying open problems.

Suggested search terms: `polar codes survey decoding construction`, `CRC aided SCL polar codes survey`.

## Specific Topics to Search Next

- `Tal Vardy list decoding polar codes`
- `CRC aided successive cancellation list decoding`
- `Gaussian approximation polar code construction`
- `density evolution polar codes`
- `fast polar decoders`
- `multi-kernel polar codes`
- `quantum polar codes`
- `finite length polar code performance`

## Suggested Next Steps

Use this wiki in cycles: read one concept page, work one small exercise, then implement or test the idea. Start with \(N=4\) or \(N=8\), make the encoder and decoder agree in a noiseless setting, then add AWGN and measure BER and BLER. Once your simulation works, revisit channel construction and SCL decoding; that is where polar codes become both subtle and powerful.

