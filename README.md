# Cache action

This action allows caching dependencies and build outputs to improve workflow execution time.

>Two other actions are available in addition to the primary `cache` action:
>* [Restore action](./restore/README.md)
>* [Save action](./save/README.md)

## Documentation

See ["Caching dependencies to speed up workflows"](https://docs.github.com/en/actions/using-workflows/caching-dependencies-to-speed-up-workflows).

## What's New

### v3

* Added support for caching in GHES 3.5+.
* Fixed download issue for files > 2GB during restore.
* Updated the minimum runner version support from node 12 -> node 16.
* Fixed avoiding empty cache save when no files are available for caching.
* Fixed tar creation error while trying to create tar with path as `~/` home folder on `ubuntu-latest`.
* Fixed zstd failing on amazon linux 2.0 runners.
* Fixed cache not working with github workspace directory or current directory.
* Fixed the download stuck problem by introducing a timeout of 1 hour for cache downloads.
* Fix zstd not working for windows on gnu tar in issues.
* Allowing users to provide a custom timeout as input for aborting download of a cache segment using an environment variable `SEGMENT_DOWNLOAD_TIMEOUT_MINS`. Default is 10 minutes.
* New actions are available for granular control over caches - [restore](restore/action.yml) and [save](save/action.yml).
* Support cross-os caching as an opt-in feature. See [Cross OS caching](./tips-and-workarounds.md#cross-os-cache) for more info.
* Added option to fail job on cache miss. See [Exit workflow on cache miss](./restore/README.md#exit-workflow-on-cache-miss) for more info.
* Fix zstd not being used after zstd version upgrade to 1.5.4 on hosted runners
* Added option to lookup cache without downloading it.
* Reduced segment size to 128MB and segment timeout to 10 minutes to fail fast in case the cache download is stuck.

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
