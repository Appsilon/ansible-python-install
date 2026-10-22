# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [Unreleased]

### Changed
- Python installation now uses [`uv`](https://docs.astral.sh/uv/) instead of Posit's prebuilt binaries, which are no longer being built by Posit for new Python versions.
- `uv` itself is installed by downloading a pinned release archive from GitHub releases, rather than running the upstream install script.
- The symlink from `/opt/python/{{ version }}` to the actual `uv`-managed install directory is now created with the `ansible.builtin.file` module instead of a raw shell command.
- Installation tasks shared between Debian and RedHat families were extracted into a common `tasks/install-python.yml`, included by both `tasks/debian/main.yml` and `tasks/redhat/main.yml`.
- `pip` calls that install directly into the `uv`-managed Python now set `PIP_BREAK_SYSTEM_PACKAGES`/`PIP_ROOT_USER_ACTION` as environment variables (needed for PEP 668 "externally managed environment" enforcement on newer Python/pip versions).

### Added
- New `uv_version` variable controlling which `uv` release gets installed.
- `curl` added to the system dependencies list (needed by the `uv` install process).

### Removed
- `python_download_url` variable (no longer used now that Python isn't downloaded as a distro-specific package).
