# Daily Snapshot Build of XMage

This repository hosts an **automated GitHub Actions workflow** that builds **daily snapshot releases** of [XMage](https://github.com/magefree/mage), the open-source *Magic: The Gathering* game engine.

These snapshots are intended for **testing the latest card implementations, features, and bug fixes**. They can be played locally against AI or by hosting your own server. **Public XMage servers are not supported by these builds.**

---

## What This Repository Does

* Clones the official XMage repository on a schedule
* Builds the latest XMage version using the `build-and-package.pl` script
* Generates a timestamped binary ZIP archive
* Publishes a **GitHub Release** containing the daily snapshot
* Automatically cleans up old releases and tags (keeps the latest 100)

> **Note**
> This repository exists **only** for automated snapshot builds. **No support is provided here.**
> For issues, bug reports, or general XMage questions, please use the official XMage repository.

---

## Workflow Schedule

The GitHub Actions workflow runs **three times per day**:

* **02:00 UTC**
* **10:00 UTC**
* **18:00 UTC**

Although builds run multiple times daily, you **do not need to update your client every time**.

> **Note**
> GitHub Actions schedules are subject to runner availability. Delays or skipped runs may occur, and releases may not always appear exactly on schedule.

---

## Important Notes

* These builds are **snapshot releases for testing only**
* They may include **unfinished features**, **experimental changes**, or **instability**
* They are **not recommended for official or competitive play**

---

## Official XMage Releases

If you are looking for stable, supported versions of XMage, use the official repository:

* **XMage Releases:** [https://github.com/magefree/mage/releases](https://github.com/magefree/mage/releases)
* **XMage Changelog (Commits):** [https://github.com/magefree/mage/commits/master](https://github.com/magefree/mage/commits/master)

---

## Auto-Update via XMage Launcher

You can configure the XMage Launcher to automatically detect and download these daily snapshot builds:

1. Open **XMage Launcher → Settings**
2. Set **XMage Home** to:

   ```
   https://teachua79.github.io/
   ```
3. Click **Check Versions** → **Update**

This allows your XMage client to stay up to date without manually checking this repository.

---

## Manual Update

You may also update manually using the release archives from this repository:

* **Daily Snapshot Releases:** [https://github.com/teachua79/teachua79.github.io/releases](https://github.com/teachua79/teachua79.github.io/releases)

### Steps

1. Download and extract the ZIP archive
2. Overwrite the following folders:

   * `mage-client`
   * `mage-server`
3. **Do not delete** the existing `mage-client` folder before overwriting it
   (it contains card images inside the `plugins` directory)

> **Note**
> Manual updates do **not** change the version number shown in the XMage Launcher. This behavior is expected and can be safely ignored.

---

## Release Naming Convention

Release tags and binary filenames follow this format:

```
daily-YYYY-MM-DD-HHMM
```

**Example:**

```
daily-2026-01-15-1830.zip
```

---

## License & Attribution

All source code and build artifacts originate from the official XMage project:

* **XMage Repository:** [https://github.com/magefree/mage](https://github.com/magefree/mage)

This repository contains **automation and build infrastructure only** and does not modify XMage source code.
