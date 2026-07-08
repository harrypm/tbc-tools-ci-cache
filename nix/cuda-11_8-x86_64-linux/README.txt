tbc-tools CUDA 11.8 closure cache
=================================
Pinned source: nixpkgs nixos-24.11 (rev 50ab793786d9de88ee30ec4e4c24fb4236fc2674)
Target: GTX-1000-series (Pascal) CUDA support for ld-decode-tools.

This directory is a Nix binary cache (narinfo + nar/ files). Any nar larger
than 95 MiB was split into chunks under <nar>.parts/ with an index, so the
whole tree fits GitHub's 100 MiB per-file limit and can be committed to the
tbc-tools-ci-cache repo.

Restore on a fresh machine:
  scripts/cuda-closure-cache.sh pull   --out ./cuda-cache
  scripts/cuda-closure-cache.sh restore --out ./cuda-cache

Verify without restoring:
  scripts/cuda-closure-cache.sh verify --out ./cuda-cache

See pin.txt for the exact nixpkgs rev + package versions, and manifest.txt for
the full list of store paths in the closure.
