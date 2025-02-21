# Redis Binaries 🚀

[![GitHub Actions Workflow Status](https://img.shields.io/github/actions/workflow/status/josslab/redis-server-binaries/manual-tag.yml)
](https://github.com/josslab/redis-server-binaries/actions)
[![Latest Release](https://img.shields.io/github/v/release/josslab/redis-server-binaries)](https://github.com/josslab/redis-server-binaries/releases)
![GitHub Downloads (all assets, all releases)](https://img.shields.io/github/downloads/josslab/redis-server-binaries/total)

This repository provides pre-compiled Redis binaries for various platforms, built using GitHub Actions.  We aim for transparency and reproducibility in our build process, allowing you to easily obtain and verify your Redis distributions.

## About

We leverage GitHub Actions to automatically compile the latest Redis releases.  This ensures you have access to up-to-date binaries without the need for local compilation.  Our build process is fully automated and auditable, giving you confidence in the integrity of the provided distributions.

## Key Features

* **Automated Builds:**  Binaries are built automatically upon new Redis releases, ensuring you always have access to the latest versions.
* **Multiple Platforms:** We support a range of operating systems and architectures (see Supported Platform below).
* **Transparent Build Process:** The entire build configuration is available in the [.github/workflows/](https://github.com/josslab/redis-server-binaries/tree/main/.github/workflows) directory. You can review the exact steps involved in creating the binaries.
* **Verifiable Builds:**  We include checksums (hashes) of the built binaries in the release notes and build logs. This allows you to verify the integrity of the downloaded files and ensure they haven't been tampered with.  Compare the checksum of your downloaded file against the one in the release page.
* **Open Source and Community Driven:** Contributions and feedback are welcome!

## Supported Platforms

| OS       | Architectures               |
|----------|-----------------------------|
| Windows  | `x86_64`                    |
| Linux    | `x86_64`, `i386`, `aarch64` |
| macOS    | `x86_64`, `aarch64`         |

## Usage

1. **Releases:** Download the desired binary for your platform from the [Releases](https://github.com/josslab/redis-server-binaries/releases) page.
2. **Verification:**  Verify the integrity of the downloaded binary by comparing its checksum against the one provided in the release notes.
3. **Deployment:** Deploy the Redis binary as needed in your environment.

## Build Process Details

The build process is orchestrated by GitHub Actions workflows defined in the [.github/workflows/](https://github.com/josslab/redis-server-binaries/tree/main/.github/workflows) directory.  The `check-new-release.yml` workflow checks for new Redis releases and triggers the `manual-tag.yml` workflow to build the binaries.

The `manual-tag.yml` workflow performs the following steps for each platform:

1. Downloads the Redis source code.
2. Sets up the build environment (including dependencies like OpenSSL).
3. Compiles Redis using appropriate flags and optimizations.
4. (Linux) Uses `upx` for binary size reduction.
5. Uploads the resulting binary as a GitHub Actions artifact.

Finally, the `release` job combines all artifacts and creates a new GitHub release, including the binaries and release notes.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request if you have any suggestions, bug fixes, or new platform support.

## License

This project is under the MIT License.  See the [LICENSE](LICENSE) file for details.

## Contact

If you have any questions or feedback, please feel free to open an issue.
