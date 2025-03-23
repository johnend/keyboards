# Libs

This group of projects uses the following 3rd party repos within KiCad for both
component footprints and models for the 3D view:

- https://github.com/johnend/scottokeebs/tree/extras-only (upstream: https://github.com/joe-scotto/scottokeebs)
  N.B. the upstream repo contains a lot of keyboard designs so my fork
contains only the KiCad footprints etc.
- https://github.com/foostan/kbd - more footprints etc.
- https://github.com/rroels/kicad_pro_micro_rp2040 - contains a footprint for
the Pro Micro RP2040 MCU (e.g. this from [Mechboards](https://mechboards.co.uk/products/pro-micro-5v?pr_prod_strat=e5_desc&pr_rec_id=daff50a5e&pr_rec_pid=6809708036301&pr_ref_pid=7132326723789&pr_seq=uniform))

## Note:
When Extras updates in the original repo:

1. Fetch and merge original repo:
```sh
git remote add upstream https://github.com/joe-scotto/scottokeebs.git
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```

2. Re-run the filter for the extras branch:
```sh
git checkout extras-only
git filter-repo --path Extras --force
git push origin extras-only --force
```

3. Update submodule:
```sh
cd /path/to/your-main-repo/libs/scottokeebs
git pull origin extras-only
cd ../..
git add libs/scottokeebs
git commit -m "Update scottokeebs Extras submodule"
```

