# R2 Research Closure — AI Model Provenance Integrity

**Decision date:** 2026-11-14  
**Decision:** NO-GO — close as an independent research candidate  
**Scope reviewed:** model provenance, artifact integrity, transformation traceability, evaluated-to-deployed continuity, and the narrower hypothesis of security-property preservation across model transformations.

## 1. Executive decision

The broad R2 framing does not establish an independent research contribution. Its central mechanisms substantially overlap with established software-supply-chain provenance and attestation approaches, including SLSA and in-toto, and with AI/ML lifecycle provenance and model identity attestation.

The narrowed residual hypothesis — certifying preservation of security properties across transformations such as pruning, quantization, adapter merging, and format conversion — also fails the current originality gate. Direct prior work already verifies equivalence of pruned neural networks against original networks and reports verification of security properties. Work on compressed LLM trustworthiness evaluates how compression affects security/trust dimensions, and 2026 work specifically studies security-aware post-training quantization for MoE LLMs with preservation of safety-relevant expert capabilities.

This decision closes R2 as an independent research candidate in its current scope. It does **not** claim that every possible problem in AI model provenance or transformation assurance has been solved.

## 2. Candidate formulations reviewed

### R2-A — broad provenance and continuity

Verifiable model provenance, artifact integrity, transformation traceability, and continuity between evaluated and deployed model artifacts.

**Reduction:** provenance attestations, signed build provenance, artifact digests, supply-chain verification, and model identity attestation already cover the central chain-of-custody and identity claims. Repackaging these mechanisms for AI models is not, by itself, a distinct scientific contribution.

### R2-B — narrowed security-property preservation

Certify that selected security properties established for a source model remain valid after a sequence of model transformations.

Let source model be M0, transformations be T1...Tn, and derived model Mn = Tn(...T1(M0)). The proposed question was whether a certificate could establish P(Mn) from evidence about P(M0) and the transformations, without simply rerunning the complete target-model evaluation.

**Reduction and direct overlap:**

- Wang et al., *VeriPrune: Equivalence verification of node pruned neural network* (Neurocomputing, 2024), directly verifies equivalence between node-pruned and original neural networks. Its experiments include 1,272 security properties, with 1,067 verified within the reported time limit. This is a direct antecedent to security-property preservation under at least one important transformation class.
- Hong et al., *Decoding Compressed Trust: Scrutinizing the Trustworthiness of Efficient LLMs Under Compression* (ICML/PMLR 2024), empirically studies how compression methods affect trustworthiness dimensions of LLMs and reports that pruning can degrade trustworthiness even where benign task performance remains acceptable.
- Liu et al., *Security-aware post-training quantization for Mixture-of-Experts large language models* (Pattern Recognition, 2026; DOI: 10.1016/j.patcog.2026.114286), explicitly addresses safety effects of quantization and preservation of safety-relevant expert capabilities.
- A 2025 systematic review of model transformation and property preservation in rigorous software development identifies transformation verification and preservation of model properties as established research themes.

The remaining gap — a general, economically useful certificate for arbitrary security properties and heterogeneous AI transformations — is too broad and under-specified to constitute a defensible candidate. No nontrivial theorem, certificate semantics, or transformation class was established that is demonstrably outside the cited verification and preservation literature.

## 3. Prior-art references

1. Wang, W. et al. (2024). *VeriPrune: Equivalence verification of node pruned neural network*. Neurocomputing. https://doi.org/10.1016/j.neucom.2024.127347
2. Hong, J. et al. (2024). *Decoding Compressed Trust: Scrutinizing the Trustworthiness of Efficient LLMs Under Compression*. PMLR 235. https://proceedings.mlr.press/v235/hong24a.html
3. Liu, B. et al. (2026). *Security-aware post-training quantization for Mixture-of-Experts large language models*. Pattern Recognition. https://doi.org/10.1016/j.patcog.2026.114286
4. *Model transformation and property preservation in rigorous software development: A systematic literature review* (2025). Journal of Systems and Software. https://doi.org/10.1016/j.jss.2025.112508
5. SLSA specification. https://slsa.dev/spec/
6. in-toto project/specification. https://in-toto.io/

## 4. Rejection rationale

R2 is closed because:

- provenance and artifact continuity reduce to established supply-chain attestation and identity-binding mechanisms;
- transformation traceability is not equivalent to preservation of security properties;
- the narrowed preservation hypothesis has direct prior art in neural-network equivalence verification and security-property verification;
- empirical trustworthiness evaluation under compression is already established;
- no independent, nontrivial certificate or theorem was defined that survives these reductions.

The decision is based on the current formulation and the identified prior art, not on a claim of exhaustive coverage of all publications.

## 5. What is preserved

- Original repository scaffold and all pre-existing files.
- Original research scope and candidate framing.
- This negative decision record and its references.
- The distinction between artifact provenance, artifact identity, transformation traceability, and semantic/security-property preservation.

No source code, prototype, benchmark, dataset, or experimental claim is authorized by this closure.

## 6. Final status

**CLOSED — NO-GO as an independent research candidate (2026-11-14).**

Reopening requires a materially different research question, a focused prior-art review, a formal property and certificate definition, and a demonstrated non-reduction to model equivalence, neural-network verification, supply-chain attestation, and existing compression-safety evaluation.

No novelty claim is made.
