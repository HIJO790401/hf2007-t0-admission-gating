# Reproduce the HF2007 public experiment

## Requirements

- Python 3.10 or later.
- No third-party Python packages are required; the experiment uses the standard library.
- Approximately 5 MB of temporary working space.

## 1. Verify the distributed artifacts

From this repository root:

### PowerShell

```powershell
(Get-FileHash .\paper\HF2007_CameraReady_MinorRevision_CLEAN.pdf -Algorithm SHA256).Hash.ToLowerInvariant()
(Get-FileHash .\experiments\HF2007_Major_Revision_Experiment_Pack.zip -Algorithm SHA256).Hash.ToLowerInvariant()
```

Expected values:

```text
ffca3677f1a36b38825f081ca9b3fa77ad1b2b66715ba7987b27531a6f8b34e4
958d880c5d82f895c0687c18a55392040e66356b82b3a47f2a32195b10047118
```

### Linux / macOS

```bash
sha256sum -c SHA256SUMS.txt
```

## 2. Extract a working copy

The replay regenerates result files. Extract the experiment ZIP into a disposable working directory instead of running inside an archival copy.

```powershell
Expand-Archive .\experiments\HF2007_Major_Revision_Experiment_Pack.zip .\hf2007-replay
Set-Location .\hf2007-replay\HF2007_Major_Revision_Experiment_Pack
```

or:

```bash
unzip experiments/HF2007_Major_Revision_Experiment_Pack.zip -d hf2007-replay
cd hf2007-replay/HF2007_Major_Revision_Experiment_Pack
```

## 3. Execute the one-command replay

```bash
python run_all.py
```

The expected invariant fields in the final summary are:

```json
{
  "status": "PASS",
  "cases": 51,
  "exact_vector_matches": 51,
  "outcome_matches": 51,
  "independence_audit": "PASS",
  "source_commit_sha": "f19c9f2c79a41046eb13c03c51a24c567a8ffa07"
}
```

The `python_version` field records the local interpreter and may differ. The replay also records `predicted_relations_sha256`. The accepted archive was produced with LF line endings and records `3b405323a76f0788aba1d8bbb8bd627cce750da9fb3d050c615e00c671a2fb7f`. A native Windows replay writes the regenerated JSONL/CSV rows with CRLF line endings and can record `baab82df52e43b0e66a28b865ab6a764e4e15dd9b91adb16582c2abde669b01b` while preserving the same 51 parsed rows, relation vectors, outcomes and passing isolated-execution audit.

The two immutable distributed artifacts must always match the repository-level checksums. For regenerated outputs, treat the case counts, vector/outcome results, source identities and same-run isolation audit as the cross-platform invariants; do not mistake a newline-serialization difference for a changed T0 result.

## What the replay checks

`run_all.py` verifies the three bundled InjecAgent source files by Git blob identity, recreates the fixed 51-case raw interface, assembles the frozen author reference, runs the raw-only deterministic extractor in normal and isolated environments, and recomputes comparison, Wilson intervals, coverage, co-failure and ablation outputs.
