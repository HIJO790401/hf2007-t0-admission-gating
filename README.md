# HF2007 — T0 Admission Gating

## Public verification checkpoint

**From Sample Safety to Path Legitimacy: T0 Admission Gating for Unauthorized Reasoning Transitions in LLM-Integrated Systems**

**Author:** Wen-Yao Hsu (許文耀／沈耀888π)  
**Manuscript affiliation (as filed):** Independent Researcher, Silent School Studio  
**Current official studio:** SERENE SCHOOL STUDIO  
**Paper ID:** HF2007  
**External-review status:** Formally accepted by ICAISG 2026 on 9 September 2026

> The system did not begin with this paper. HF2007 is the minimum externally verifiable layer extracted from a system already under engineering development at that checkpoint.

This repository preserves the exact public evidence package that corresponds to that reviewed checkpoint: the final camera-ready manuscript and the major-revision experiment pack used in the acceptance process. The two original artifacts are distributed byte-for-byte unchanged. Their SHA-256 digests are fixed in [`SHA256SUMS.txt`](SHA256SUMS.txt).

[繁體中文說明](README.zh-Hant.md)

## Official verification links

- [Official research record — English](https://silentschool.studio/en/research/hf2007-t0-path-legitimacy)
- [Official research record — Traditional Chinese](https://silentschool.studio/zh/research/hf2007-t0-path-legitimacy)
- [ICAISG 2026 formal acceptance evidence](https://silentschool.studio/media/icaisg/HF2007-ICAISG-2026-Acceptance-Notification.pdf)
- [Final camera-ready paper](https://silentschool.studio/media/research/hf2007/HF2007_CameraReady_MinorRevision_CLEAN.pdf)
- [Reviewed experiment pack](https://silentschool.studio/media/research/hf2007/HF2007_Major_Revision_Experiment_Pack.zip)
- [Complete public evidence release](https://silentschool.studio/media/research/hf2007/HF2007_Public_Evidence_Release_v1.0.zip)

The official-site record provides the public narrative and acceptance evidence. This repository provides the immutable paper, experiment package, provenance, replay instructions and version record for the same checkpoint.

## What this checkpoint establishes

HF2007 moves the safety question from isolated sample classification to reasoning-path admission. Before a proposed transition can enter ordinary reasoning, T0 checks whether the required relationships among definer, domain, evidence, causality, boundary, unresolved gaps, output authority and responsibility are legally established for the current task.

The accepted public checkpoint contains an executable, deterministic and replayable realization of that admission path:

- **51/51** exact relation-vector matches between the separately frozen reference and prediction paths.
- **51/51** T0 outcome agreement.
- **17/17** pre-tool user transitions admitted.
- **34/34** injected tool-output transitions stopped before normal reasoning.
- **0** false stops on the 17 authorized controls in this fixed slice.
- **0** false admissions on the 34 injected transitions in this fixed slice.
- Fixed upstream commit, Git blob identities, source-byte hashes, selected-row identities, per-case comparison, coverage, ablation, replay and machine-readable receipts.

This is not a concept waiting to be implemented. It is the minimum public layer that was extracted from the engineering work, made reproducible, submitted for external review and formally accepted.

## Artifacts

| Artifact | Role | SHA-256 |
|---|---|---|
| [`paper/HF2007_CameraReady_MinorRevision_CLEAN.pdf`](paper/HF2007_CameraReady_MinorRevision_CLEAN.pdf) | Final camera-ready manuscript | `ffca3677f1a36b38825f081ca9b3fa77ad1b2b66715ba7987b27531a6f8b34e4` |
| [`experiments/HF2007_Major_Revision_Experiment_Pack.zip`](experiments/HF2007_Major_Revision_Experiment_Pack.zip) | Exact reviewed reproducibility package | `958d880c5d82f895c0687c18a55392040e66356b82b3a47f2a32195b10047118` |

See [`REPRODUCE.md`](REPRODUCE.md) for the one-command replay, [`PROVENANCE.md`](PROVENANCE.md) for source identity, and [`LIMITATIONS.md`](LIMITATIONS.md) for the exact validated scope.

## Relationship to the current system

HF2007 is a historical public verification checkpoint, not the full private system and not the current endpoint of T0 engineering. The paper exposes only the layer required for external inspection and reproducibility. Development of T0, SCBKR, AICC and their runtime integration continues beyond this release. Future public versions will be issued as new, separately identified checkpoints; they do not rewrite this evidence record.

## Publication state

The work was formally accepted after review, and the camera-ready files were acknowledged as received. This repository is an independent author release of the accepted public evidence. It does not claim completed conference publication, DOI assignment, IEEE Xplore publication or database indexing. See [`STATUS.md`](STATUS.md).

## Rights and third-party material

The experiment pack contains fixed source records from the InjecAgent project at commit `f19c9f2c79a41046eb13c03c51a24c567a8ffa07`. Those third-party files remain under the upstream MIT License. See [`THIRD_PARTY_NOTICES.md`](THIRD_PARTY_NOTICES.md) and [`licenses/InjecAgent-MIT.txt`](licenses/InjecAgent-MIT.txt). No third-party endorsement is implied.

Owner-authored material and the third-party material have separate rights boundaries; see [`LICENSE.md`](LICENSE.md).
