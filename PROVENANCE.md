# Provenance and immutable identity

## Owner artifacts

### Final manuscript

- File: `HF2007_CameraReady_MinorRevision_CLEAN.pdf`
- Role: final Camera-ready minor-revision manuscript.
- Organizer receipt state: confirmed received on 28 September 2026.
- Size: 368,582 bytes.
- SHA-256: `ffca3677f1a36b38825f081ca9b3fa77ad1b2b66715ba7987b27531a6f8b34e4`.

### Reviewed experiment pack

- File: `HF2007_Major_Revision_Experiment_Pack.zip`
- Role: reproducibility package submitted during Major Revision and carried into the accepted paper's evidence record.
- Size: 328,685 bytes.
- SHA-256: `958d880c5d82f895c0687c18a55392040e66356b82b3a47f2a32195b10047118`.
- Archive members: 44, including a 43-entry internal `SHA256SUMS.txt` manifest.

The files under `paper/` and `experiments/` are direct byte-preserving copies. The public wrapper adds documentation around them and does not rewrite their contents.

## Upstream public source fixed by the experiment

- Repository: <https://github.com/uiuc-kang-lab/InjecAgent>
- Pinned commit: [`f19c9f2c79a41046eb13c03c51a24c567a8ffa07`](https://github.com/uiuc-kang-lab/InjecAgent/commit/f19c9f2c79a41046eb13c03c51a24c567a8ffa07)

| Upstream path | Git blob SHA | Bundled-byte SHA-256 | Selected records |
|---|---|---|---:|
| `data/user_cases.jsonl` | `6f3dd74a29539ac36c1afec4455fdbfa7870fcb1` | `c840e2b00fdce68e7142d0970220522303d67b2530d6fb36ef1112448cdd8977` | 17 |
| `data/test_cases_dh_base.json` | `976ad4e2108a553a3b885951e8eb119aa91f9445` | `0a8186468d21389af432e8c7b399ae42264d1b93a07b65c7a489468508604305` | 17 of 510 |
| `data/test_cases_ds_base.json` | `16f82d8a34349182eba883871333e569bafc6b93` | `4daab35c62a3845e8b9400f4dca58b9c9f37e57cd33b2337552557fbb26282e9` | 17 of 544 |

The selected slice is deterministic: all 17 published user cases and indices 0–16 from each of the two composite files at the pinned commit.

## Verification chain

1. Verify the two distributed owner artifacts against the repository-level `SHA256SUMS.txt`.
2. Extract the experiment pack.
3. Verify the 43 internal entries against its internal `SHA256SUMS.txt`.
4. Run `python run_all.py`.
5. Confirm the invariant result fields and the platform-aware regenerated-output hash recorded in [`REPRODUCE.md`](REPRODUCE.md).

The accepted archive stores generated text outputs with LF line endings. A native Windows replay can serialize regenerated JSONL/CSV files with CRLF and therefore produce a different byte hash while preserving all parsed rows, vectors, outcomes and the same-run isolation check. The immutable paper and experiment ZIP hashes are platform-independent and must never change.
