# Morgan Fingerprint Educational Implementation

[日本語版](README.md)

To better understand how Morgan Fingerprints work internally, I created a small Python implementation while studying the RDKit source code.

Although RDKit provides a convenient API for generating fingerprints, many of the underlying steps are hidden behind that interface.

This implementation was built as a way to follow the process step by step, from Atom Invariant generation and Neighborhood expansion to Morgan Identifier calculation and BitInfoMap construction.

It is a personal learning implementation and is intended for understanding the algorithm rather than for production use.

## Why I Built This

While learning about Morgan Fingerprints, I became curious about questions such as:

- How are Atom Invariants generated?
- How are Neighborhoods expanded?
- How are Morgan Identifiers calculated?
- How are redundant local environments removed?
- How is the BitInfoMap constructed?

Reading papers and source code helped, but implementing the algorithm myself turned out to be one of the best ways to understand what was happening internally.

## What Can Be Explored

To make the fingerprint generation process easier to understand, intermediate results can be viewed at each stage of the calculation.

For example, the following information can be inspected:

- Atom Components
- Atom Invariants
- Bond Invariants
- Morgan Identifiers
- Neighborhood Environments
- BitInfoMap

Results are also preserved for each radius:

- radius = 0
- radius = 1
- radius = 2
- radius = 3

This makes it possible to observe how atomic environments evolve during fingerprint generation.

I hope it may be useful to others who are interested in understanding how Morgan Fingerprints are built internally.

## Relationship to RDKit

This implementation was developed with reference to the RDKit source code, while the code itself was independently written in Python to make the internal processing easier to follow.

The purpose of this notebook is to explore and understand the fundamental concepts and mechanisms behind Morgan Fingerprints. It is not intended to be a complete reimplementation or a replacement for RDKit.

## Limitations

This implementation prioritizes readability and learning over:

- Execution speed
- Memory efficiency
- Production-level performance
- Full compatibility with RDKit

For practical cheminformatics applications, RDKit is generally the recommended choice.

## Environment

- Python 3.10.18
- RDKit 2025.03.5
- Pandas 2.3.1

## References

### Morgan Algorithm

Morgan, H. L. "The Generation of a Unique Machine Description for Chemical Structures" Journal of Chemical Documentation, 5, 107–113 (1965)

### RDKit

RDKit Open-Source Cheminformatics https://github.com/rdkit/rdkit

RDKit is distributed under the BSD 3-Clause License.

## License

MIT License

## Acknowledgements

I learned a great deal from the RDKit source code and documentation while working on this implementation.

Many thanks to the RDKit developers and community for making such an excellent open-source project available.

