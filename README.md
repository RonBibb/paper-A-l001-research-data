# Paper A: L001 research archive

**Migration pending: GitHub LFS rejected the first data batch because the account exceeded its LFS budget. This remote currently contains the manifest and verification tool, not the complete archive. Do not use it as a replacement for the existing Paper A pipeline yet.**

Complete frozen L001 experiment archive and associated processed manifest/result index extracted from the public Paper A pipeline at commit `d92f2b75724ca77a335beafdb4ad49b4fd7f494c`.

## Contents and scope

`raw/experiments` preserves all 19,416 archived files, including historical sources, failed attempts, controls and result records. `processed/ARCHIVE_MANIFEST.json` preserves their original hashes, lengths and directory inventory. CURRENT_RESULT.json retains its original conditional local-family claim and pipeline-relative references. This archive includes historical experiments; inclusion does not mean every result supports the manuscript.

This is a provenance-preserving archive, not a newly qualified portable scientific campaign. Historical Linux/runtime/absolute-path restrictions remain. Producer code is preserved unchanged; do not interpret identity verification as mathematical or interval-trajectory regeneration.

## Retrieve and verify

Git LFS is required to retrieve large records. From a clone:

```sh
git lfs pull
python3 verify_l001_archive.py --data-dir raw --manifest processed/ARCHIVE_MANIFEST.json --output /tmp/l001-identity-verification.json
```

Run verification and all scientific computation on Linux. The verifier uses the Python standard library and executes no scientific producers. Git does not represent empty directories; their historical inventory remains in the manifest.

## Pipeline integration

The public pipeline pins this archive at `datasets/l001-research-data`. Initialize only when needed:

```sh
git submodule update --init datasets/l001-research-data
git -C datasets/l001-research-data lfs pull
```

The pipeline retains compatibility links at `data/raw/l001` and `data/processed/l001`, preserving source-index and result references. Pipeline documentation and orchestration remain in the parent repository. For those paths, use the initialized pipeline checkout; this standalone archive retains original references rather than rewriting historical evidence.

Large numerical records use Git LFS. Original published pipeline history is not rewritten by this extraction, and no historical LFS objects are pruned automatically.
