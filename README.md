Create a container image with all Python versions supported by Spack.

The [spack.yaml][spack.yaml] file contains a list of Python versions and their hashes (as they are built in Gitlab CI).

To publish a new container image, update the `spack.yaml` file and run

```console
spack -e . buildcache push \
    --tag YYYY-MM-DD \
    --unsigned \
    --base-image ubuntu:24.04 \
    --without-build-dependencies \
    ghcr
```
