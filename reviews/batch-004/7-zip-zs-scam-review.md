# 7-Zip ZS review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-17  
**Category:** Open-source file archiver and compression codecs  
**Method:** Source-led desk review; no hands-on testing is claimed.

7-Zip ZS is a community-maintained fork of 7-Zip that adds support for Zstandard, Brotli, Fast-LZMA2, Lizard, LZ4 and LZ5. The project publishes source code, a release page, a separate homepage and instructions for a full Windows setup or optional codec integration. It is free to use under a multi-part open-source license; binary redistribution must preserve the applicable license information. The latest GitHub release checked was 26.05, while the upstream 7-Zip site had moved to 26.06 and the fork README still listed 26.04, so version information should be read from the exact release page. The maintainer’s README says code-signed installers were planned again; verify the signature and checksum of the specific downloaded Windows asset. Public evidence identifies a real project and does not substantiate a scam claim, but this fork is best for users who understand archive compatibility and installer verification.

## Editorial verdict

The sources identify 7-Zip ZS as a real open-source fork of 7-Zip, with a specific purpose: add several compression codecs to a familiar 7-Zip workflow. The reviewed evidence does not substantiate calling it a scam. Its value is practical for someone who needs Zstandard, Brotli, LZ4, LZ5, Lizard or Fast-LZMA2 support in the project’s archive workflow. The tradeoff is that it is not the upstream 7-Zip release, its own README and release page showed different version numbers, and archive interoperability depends on the format and codec used. The project says it plans to resume code-signed installers, so a user must verify the publisher signature and file hash rather than treating a signed Git tag as proof that the Windows binary is signed. The source repository and license are public, and the project states that it is free to use. No installer was downloaded, no archive was benchmarked and no security audit was performed.

## 7-Zip ZS review: extra compression methods in a familiar archiver

7-Zip ZS is a fork of 7-Zip maintained through the mcmilk/7-Zip-zstd project. Its central purpose is easy to state: add support for Zstandard, Brotli, Fast-LZMA2, Lizard, LZ4 and LZ5 to an archiver that already handles common archive workflows. The project homepage points to downloads hosted on GitHub, shows example command lines and describes the supported codecs. For someone whose scripts or desktop work already revolve around 7-Zip, that can be a more direct route to these methods than adopting an entirely separate archiving tool.

The fork is useful because codec support is not just a checkbox. A user must choose the compression method, understand the archive format that contains it and confirm that the person receiving the archive has a compatible decoder. A filename ending in .7z does not guarantee that an older stock archiver can decode a newer or less common codec. The decision is therefore about the whole exchange: the computer that creates the archive, the software that opens it and how the receiver can obtain a matching version.


## What the added codecs mean in a practical workflow

The README lists six added methods: Zstandard, Brotli, Fast-LZMA2, Lizard, LZ4 and LZ5. They offer different speed, compression-ratio and memory tradeoffs, so the useful choice depends on the file type and the job. A very fast transfer archive, a long-term backup and a small software distribution package do not have identical goals. The project documents command-line examples such as selecting Zstandard with a level parameter and provides benchmark results for several methods.

Treat these as options to evaluate, not a promise that one codec will always produce the smallest or fastest result. The README’s benchmark is project-authored and specifies its hardware, operating system, corpus and single-threaded test method. Those details make the results more interpretable, but they do not substitute for a test with your own files, storage and target machines. Try representative text, media, already-compressed assets and executable files, measure the result and keep the command settings with the archive process so a teammate can reproduce it.


## Codec support and archive compatibility are different things

The project README describes a full application setup and a narrower plugin option for mainline 7-Zip. The plugin notes state that the codecs work within the 7z container and that the plugin does not cover standalone .zst, .lz4 or .lz5 files. This is a meaningful distinction: installing a plugin can extend a host archiver for the documented use case without turning that host into a general-purpose tool for every standalone compressed file.

Before sending a .7z archive to another person, confirm that their extractor recognizes the codec you selected. Test the archive on a clean machine with the recipient’s normal software, especially if the content is time-sensitive or must be kept for years. For a broad audience, prefer widely supported formats and avoid using a specialized method unless the receiver can install the compatible build. Keep the original files until extraction has been verified; a successful archive-creation message is not proof that every file will restore correctly elsewhere.


## Full setup versus plugin: choose the integration you can maintain

The project documents a full Windows setup that installs a 7-Zip ZS environment and a plugin route for an existing 7-Zip installation. The README also distinguishes command-line variants: one can load codec modules through 7z.so, while a standalone 7zz binary is built and distributed differently. Those alternatives are helpful for different technical audiences, but they require a deliberate choice rather than a single generic “download 7-Zip ZS” click.

The full setup is more appropriate when you want the fork’s full application and integrated behavior. A plugin can be enough when your existing mainline 7-Zip workflow only needs the supported codec additions, but it changes files in an existing installation and needs architecture-matched components. Follow the project instructions for the exact host version, check which DLLs are replaced or added, and record a rollback path. If a machine is managed by an IT team, ask before replacing system-wide archive components. Do not mix releases or architecture variants just because their filenames look similar.


## Release versions and documentation do not line up perfectly

The GitHub Releases page checked November 17, 2026 lists 7-Zip ZS 26.05 as its latest release, published November 2. The upstream 7-Zip site lists 26.06, published November 6. The fork’s README still identifies version 26.04 and is marked October 6. That does not establish that the fork is unsafe or unusable; it means its homepage, README and latest binary release are not synchronized at the same version. A buyer should use the release page for the actual package version and consult the release notes rather than relying on the README’s static version line.

The release history also shows why this matters: 26.02 Release 1 is explicitly marked obsolete because files were missing, and Release 2 supersedes it. The project has a visible correction path, which is useful, but users should not install an older build simply because it appears first in a search result or remains in an old download folder. Record the release tag and date with any deployment, and re-check the official page when you update a backup server or long-lived workstation.


## Installer integrity needs a separate check from GitHub’s signed tag

The latest release page shows a verified signature for its Git tag, while the project README says that a code-signed installer was planned again. These are different trust signals. A signed tag helps establish who signed the source tag; it does not by itself prove that a Windows setup executable has a valid publisher signature or that a mirror served the same bytes. The README also describes comparing SHA-256 hashes for release files, which provides a practical verification step when the expected hash is published.

For a Windows download, start at the project homepage and follow its direct link to the official Releases page. Confirm the exact version and architecture, check the file hash against the project’s published value, and inspect the Windows digital-signature details before installing. If a publisher signature is absent or its identity differs from the maintainer’s guidance, pause and verify the release notes or ask in the official project channel. This review did not download or scan any asset and does not certify any particular binary.


## Security fixes make version tracking part of archive safety

The release notes show that earlier versions included security fixes to compression and decompression code, including memory-safety issues in codec paths. That is not evidence that the current release is compromised; it is a reminder that archive software processes complex, externally supplied data and should be kept current. An archive can come from email, a customer, a source repository or an old backup, so the extractor is part of the organization’s attack surface.

Use the current release linked from the project page, avoid opening an archive with an obsolete build, and treat files from unknown senders with the same caution you would apply to any executable or document. For shared workstations, test updates with representative archives before a broad rollout. In a managed environment, maintain an approved package, record the version and remove superseded installers from deployment folders so users do not accidentally reinstall a release that the project has marked obsolete.


## Licensing is open source, but redistribution still has conditions

The COPYING file says that most of the code is under LGPL 2.1 or later, with specific components using additional terms, including an unRAR restriction and BSD-licensed portions. It also says that redistribution in binary form must reproduce related license information. The project describes use in a commercial organization as permitted without registration or payment. That is useful for an individual or business evaluating the tool, but it is not a blanket statement that every component can be redistributed without notices or review.

If you are only installing the official package for internal use, follow the exact release terms. If you bundle 7-Zip ZS in another product, redistribute modified binaries or ship a plugin with commercial software, read the complete license file and preserve the required notices. Confirm that the particular source file and dependency you use are covered by the assumptions in your distribution. This is a practical software-license check, not legal advice. The public repository makes the terms available, but each distributor remains responsible for honoring them.


## Benchmark claims are useful context, not a universal winner

The project README describes a benchmark run on a named Linux server using the Silesia corpus, single-threaded compression commands and a test of the created archive. It identifies the measuring script and publishes compression-speed, decompression-speed and memory plots. That is stronger documentation than a bare “fastest” slogan because a reader can see which hardware and test method produced the results.

The measured hardware is a high-core server with ample memory, and the reported runs use one thread per method. Your laptop, NAS, server, power limit, file mix and concurrency will produce different results. Media files may already be compressed; source code, logs and databases may respond differently. Re-run a small controlled benchmark on the actual workload before selecting a default. Keep compression level, thread count, archive type and sample set constant when comparing with upstream 7-Zip or another tool. We did not repeat the project’s benchmark or independently validate its plots.


## A safe adoption test starts with recoverable sample data

Begin with copies of representative files rather than the only copy of a business archive. Create one archive with the default method and one with the codec you plan to use. Record the command line, archive format, compression level, time, output size and memory use. Run the project’s documented integrity test, then extract the files on a second machine using the exact software version planned for the recipient. Compare file counts and hashes after extraction.

If the archive will be kept for years, store a note identifying the codec and tool version alongside it, and keep a copy of the installer or a reference to the signed release. Consider whether the organization’s disaster-recovery process can restore it without internet access or a specialist engineer. Add encryption separately if confidentiality is needed, and validate key handling with the intended recipient. A successful compression benchmark does not prove encryption, long-term readability or recovery readiness; each requires its own test.


## Who should consider the 7-Zip ZS fork

7-Zip ZS is a plausible fit for a technically capable Windows user or administrator who already understands 7-Zip and needs the added compression codecs. Developers and IT teams can benefit from the source, version notes, command examples and release history, especially when a controlled archive format is part of a script or backup process. Users who only need standard ZIP or 7z support may prefer the upstream 7-Zip project, which has its own download page, current release and simpler publisher identity.

It is a weaker fit for someone who wants an installer with a clearly documented signed publisher and no compatibility decisions, or for teams whose recipients cannot install a matching decoder. Compare the full fork with upstream 7-Zip, and consider a codec plugin only if its narrower behavior meets the requirement. The choice should be based on a demonstrated archive-recovery need, not simply on the number of compression methods in a feature list.


## 7-Zip ZS scam review verdict: a real open-source fork with verification duties

The project has a public homepage, a linked GitHub repository, source code, release notes, licensing terms and detailed instructions for the full setup and codec plugin. Those sources describe a real fork that adds specific compression methods to 7-Zip. The reviewed evidence does not substantiate calling 7-Zip ZS a scam. Its most important limitations are product identity and operational fit: it is not the upstream 7-Zip release, a specialized codec archive may not open in a recipient’s stock tool, the README and release page showed different versions, and Windows installer signing must be verified for the exact asset.

This is a source-based desk review, not a download, installation, security audit, license opinion, interoperability test or compression benchmark. Official pages and release records were checked November 17, 2026. Before using it with valuable data, install only the current release from the project’s linked page, verify its hash and publisher signature, test extraction on a second machine and preserve license notices if redistributing. Keep an independent copy of original files until the restore test succeeds.


## Features and decision criteria

- Adds Zstandard, Brotli, Fast-LZMA2, Lizard, LZ4 and LZ5 support to the 7-Zip project
- Provides a full Windows setup and separate codec-plugin instructions for compatible mainline 7-Zip installations
- Documents command-line compression levels and codec selection for .7z archives
- Publishes source code, version notes, build and release history, and multi-part open-source licensing information
- Lists Linux and macOS command-line variants, while distinguishing plugin-capable 7z from the standalone 7zz binary
- Includes project-authored benchmark scripts, test methodology and example results

## Pricing considerations

The project states that use is free and no registration or payment is required. This does not remove license requirements for redistribution or prove the integrity of a binary. Versions change; confirm the latest release, its assets, compatibility and signature at the time you download.

## Sources and further reading

- [7-Zip ZS website](https://mcmilk.de/projects/7-Zip-zstd/)
- [7-Zip ZS source README: codec support, full setup and plugin workflow, benchmark method, version and code-signing note](https://github.com/mcmilk/7-Zip-zstd/blob/master/README.md)
- [Official 7-Zip ZS releases: latest 26.05 release, signatures, release notes and superseded builds](https://github.com/mcmilk/7-Zip-zstd/releases)
- [7-Zip ZS COPYING: license and binary redistribution notices](https://github.com/mcmilk/7-Zip-zstd/blob/master/COPYING)
- [7-Zip ZS issue #473: maintainer discussion about signed releases](https://github.com/mcmilk/7-Zip-zstd/issues/473)
- [Official upstream 7-Zip site: current 26.06 release and upstream format support](https://www.7-zip.org/)
- [7-Zip on Wikipedia](https://en.wikipedia.org/wiki/7-Zip)
- [saashub listing](https://www.saashub.com/7-zip-zs)

For the complete Roseram buyer guide, see [7-Zip ZS review](https://roseram.com/reviews/scams/7-zip-zs-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
