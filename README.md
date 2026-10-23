# Xiaomi Home screen+ × Computer Use

[简体中文](README.zh-CN.md)

A practical record of operating a Xiaomi phone from a Mac through **Xiaomi Interconnectivity → Home screen+ → a computer-use assistant**. The useful part is the verification loop and recovery procedure: observe the live window, take one action, then check the phone's new state.

**Status:** documentation-only initial edition. The supplied field notes report successful operations on one setup. No reusable phone-control source code was supplied, and no hardware run was repeated while preparing this edition. This repository contains no SDK, driver, proprietary tool implementation, or ready-to-run automation. See [the evidence and test record](docs/validation.md).

## What you need

| Dependency | Requirement and evidence |
| --- | --- |
| Host | A Mac with Xiaomi Interconnectivity installed from the [official App Store listing](https://apps.apple.com/us/app/xiaomi-interconnectivity/id6673908449?platform=mac). Exact original Mac model and macOS version were not recorded in the supplied field notes. |
| Phone | A Xiaomi phone on which Home screen+ actually works. Exact original phone model and OS version were not recorded. Do not infer universal Redmi/POCO support. |
| Vendor compatibility | The listing checked on 2026-10-23 states HyperOS 2, Device interconnectivity services ≥16.00.50 and Xiaomi Share ≥3.3.0. These are published prerequisites, **not the measured versions of the original test** or a guarantee of compatibility. Check the current listing for your device. |
| Connection | The owner must first make the vendor's normal connection and Home screen+ work manually. This project does not replace pairing or authentication. |
| Assistant | An already-authorized computer-use environment that can observe and interact with **native Mac windows**. A text-only chat or browser-only controller is insufficient. The original CUA client/version was not recorded; access is not supplied here. |
| Permission | Owner consent to phone control, vendor pairing/screen-sharing prompts, and the screen-capture/accessibility permissions required by that specific computer-use client. Exact original permission toggles were not recorded. The owner reviews prompts; do not grant broad permissions automatically. |

No ADB, root, app API integration, or chat-database access was used in the recorded method. This does not mean those are the requirements of other products or platforms.

## Smallest reproduction: launch and verify one harmless app

This procedure is derived from the recorded full-screen workflow. This exact harmless acceptance case has **not** been rerun for this edition.

1. Use your own devices, remain present, and put the phone on a non-sensitive home page. Choose a harmless target such as Calculator; avoid exposing notifications, private chats, or account pages to the assistant.
2. Open Xiaomi Interconnectivity on the Mac. Complete its normal connection yourself if needed. Choose **Home screen+ → On / 开启** to open the **full phone home screen**. In the recorded setup, launching an individual app from the interconnectivity home page was unreliable.
3. Manually confirm that the mirrored phone responds before delegating. If it does not, fix the vendor connection first. Do not change network security or bypass compatibility checks to follow this guide.
4. Give the assistant [the bounded task prompt](examples/task-prompt.md). Ask only to open the chosen app and verify its landing screen. This repository deliberately specifies no private CUA function names or saved coordinates.
5. For each step: inspect the current live window → identify one target → perform one click or swipe → inspect a fresh image. Prefer accessible controls where present. The recorded phone content generally required visual targeting.
6. Confirm that the intended app actually opened. If the screen did not change, report an unconfirmed action; do not treat a successful tool return as task completion. Stop if the app/target is ambiguous.
7. End the assistant's task and disconnect as below. Record pass/fail using [the blank report](examples/test-report.md). Keep personal evidence local.

**Pass:** the intended app's landing screen is visibly confirmed after the action, no sensitive operation occurred, and the session is ended. **Fail/blocked:** no native window access, pairing/authentication pending, frozen mirror, ambiguous target, or no observable result. Never fill missing evidence with a guessed success.

For a later, separately authorized write test, the original notes describe creating a calendar reminder, saving it, reopening it, and checking its date/time and alarm switch. No reminder title/date or private account example is published here. No new calendar write was performed for this edition.

## Failure modes observed in the field notes

| Symptom | Practical response |
| --- | --- |
| Individual-app projection stalls or displays incorrectly | Return to the vendor app and try the full Home screen+ window. This is one setup's observation, not a universal fix. |
| An app has multiple account/clone icons | Have the owner identify the intended account. Badge conventions are device-specific; never assume an unbadged icon is always the main account. |
| Pasted Chinese text is stale | Inspect the entire field before committing anything. The original setup sometimes pasted previous clipboard contents. Ctrl+A worked in its phone form; Cmd+A was unreliable. These shortcuts are not universally tested. |
| Window missing, screenshot failure, or `noWindowsAvailable` | Reinspect the current windows. Do not infer phone lock from an error alone. Stop blind actions; if necessary close the projection and reconnect through Home screen+. |
| Layout, scale, page, or connection changed | Observe again. Coordinates from an earlier frame are invalid evidence. |
| Password/Touch ID, screen-time restriction, or other block | Stop and let the owner handle it. This guide does not require changing restrictions or circumventing authentication. |

## Safety and privacy boundaries

- Use only authorized devices and a narrow task. A screenshot may reveal more than the target app; consider the assistant provider's data handling before exposing content.
- Never auto-send messages, make purchases, reveal credentials, change security/network settings, or operate physical access controls as a demonstration.
- Verify complete text and account identity before any separately authorized submission. For physical effects, UI success is insufficient; the owner must confirm the real-world outcome. No physical-control reproduction is included.
- Do not read pairing files, tokens, cookies, chat databases, or device identifiers. Do not publish screenshots, personal logs, notification contents, or clipboard history.
- Remain present. This is unsuitable as a reliable unattended phone agent. Repeated screenshots also cost time and assistant usage; no latency, reliability, or usage benchmark was recorded.

## End control, disconnect, and revoke access

1. Tell the assistant to stop; verify no further input occurs. End its computer-control session through that client's own controls.
2. Close/stop the Home screen+ session in Xiaomi Interconnectivity. Confirm the mirror is gone and further Mac input is not reaching the phone. Do not assume window closure revokes the persistent device relationship.
3. If you no longer want the relationship, use the vendor's current device-removal/unpairing UI. For lasting removal of assistant access, review and revoke that client's screen-capture/accessibility permissions in macOS System Settings. Exact labels vary by version.
4. These disconnect/revocation steps are a recommended owner checklist, **not a recorded successful teardown test**. If disconnection is uncertain, stop the client/vendor apps and verify on the phone before leaving it unattended.

## Verified and unverified

The supplied notes report app launching, reading app information, and a saved calendar reminder reopened for verification. They also report an owner-confirmed physical result, which is deliberately excluded from the example. They do not provide raw traces, version metadata, repeat counts, timings, or a teardown test.

No new Mac/phone interaction, independent device reproduction, unattended operation, Windows/Linux/iOS support, or general app compatibility is claimed. [Validation details](docs/validation.md) distinguish historical reports from preparation-time checks.

## Contents and contribution

Start with this README or the [Chinese version](README.zh-CN.md), then use the two templates in `examples/`. [CONTRIBUTING.md](CONTRIBUTING.md) explains how to report a reproduction without sharing private material. [Provenance and third-party notices](docs/provenance.md) define what is licensed.

## License

[MIT](LICENSE) applies to the original documentation and templates in this repository. Xiaomi, Apple, OpenAI and their products remain subject to their own terms; no vendor software, branding assets, private tool documentation, or third-party source code is redistributed. This is an independent practice record and carries no vendor endorsement.
