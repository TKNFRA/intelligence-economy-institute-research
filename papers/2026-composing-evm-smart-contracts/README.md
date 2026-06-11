# Composing EVM Smart Contracts: A Seam Calculus

- **Author:** Zakaryae Boudi
- **Affiliation:** Intelligence Economy Institute (IEI)
- **Date:** June 2026
- **Status:** Working paper / preprint — circulated for technical and academic feedback, pending submission to a peer-reviewed journal
- **Manuscript:** [Composing-EVM-Smart-Contracts-A-Seam-Calculus.pdf](Composing-EVM-Smart-Contracts-A-Seam-Calculus.pdf)
- **License:** [CC BY-NC-ND 4.0](LICENSE)

## Abstract

Many high-impact failures in composed Ethereum Virtual Machine (EVM)
applications arise not inside a single contract but at the boundary where one
component silently assumes behaviour that a neighbour does not guarantee. We call
such a boundary a *seam* and give it a precise calculus. We model a standard as a
syntactic interface together with the behaviours the standard explicitly
*requires*, and we model a component's reliance at a seam as a separate set of
*needs* that may be stronger than any interface or standard guarantees. We
separate two phenomena the informal literature conflates: *specification
conflict*, where two requirements are jointly unsatisfiable (rare, and decidable
only within an explicitly chosen decidable logical fragment), and *seam
non-conformance*, where a chosen implementation fails a neighbour's need (common,
and in general undecidable, which is why it is the proper target of heavyweight
verification). For the safety fragment we instantiate a one-directional soundness
theorem in the rely–guarantee tradition: if the assume–guarantee ledger is
acyclic and every relied-upon need is discharged by a concrete guarantee or
external attestation, then the composed system satisfies the conjunction of the
catalogued seam guarantees. We are explicit about what this does *not* establish:
it does not make smart-contract correctness decidable, and ledger
well-formedness is necessary for a complete assurance argument but not sufficient
for system safety, since internal bugs, mis-specified or missing properties, an
incomplete threat model, and false attestations all lie outside the ledger.

We then turn the calculus into practice along three axes. First, a dissection of
the load-bearing EVM standards (tokens, approvals, vaults, signatures, accounts,
flash loans, oracles, proxies) and the six structuring DeFi platforms (Uniswap
v4, Aave V3, Compound III, Morpho Blue, Balancer V3, Curve NG), each read as a
guarantee/need pair with its principal seam and a stated adversary. Second, a set
of guarded design rules for constructing the discharge ledger. Third, a fully
worked case study — a yield router stacking an ERC-4626 vault on Aave V3 behind a
UUPS proxy with a Chainlink oracle, with a concrete normalising adapter — carried
end to end: properties enumerated, seams identified, the ledger built, and two
distinct faults (a token/vault non-conformance and a solvency/liveness cycle)
mechanically surfaced. We connect the engineering layer to a companion formal
substrate: a property catalogue with a five-axis classification and an
assume–guarantee ledger. Our contribution is to make the *assumption ledger* —
the audit artifact, distinct from the audit itself — a mathematical object: a
typed, finite graph that separates decidable bookkeeping from specification
entailment and implementation verification, makes hidden integration assumptions
explicit, and localises the residual verification and trust burden rather than
hiding it. We claim this for the ledger, not for the audit, which remains
socio-technical.

## Keywords

seam calculus, EVM, smart contract composition, assume–guarantee reasoning,
rely–guarantee, formal verification, DeFi, ERC-4626, audit assurance

> Note: the manuscript does not declare an explicit author keyword list; the
> terms above are derived from the title and abstract to aid discoverability.

## Citation

If you reference this work, please cite it as:

> Boudi, Z. (2026). *Composing EVM Smart Contracts: A Seam Calculus.*
> Intelligence Economy Institute. Working paper / preprint.

```bibtex
@techreport{boudi2026seamcalculus,
  title       = {Composing EVM Smart Contracts: A Seam Calculus},
  author      = {Boudi, Zakaryae},
  institution = {Intelligence Economy Institute},
  year        = {2026},
  month       = {6},
  type        = {Working paper / Preprint},
  note        = {Licensed under CC BY-NC-ND 4.0}
}
```

See [CITATION.cff](CITATION.cff) for machine-readable citation metadata.

## License

This work is licensed under the
[Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International
(CC BY-NC-ND 4.0)](https://creativecommons.org/licenses/by-nc-nd/4.0/) license.
The full legal text is in [LICENSE](LICENSE).
