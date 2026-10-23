# AI Phone Control on Mac with Xiaomi Home screen+

**Mac 控制小米手机 · AI 手机操作实践**

[简体中文](#简体中文) · [Before you start](#before-you-start) · [Quick reproduction](#smallest-reproduction-launch-and-verify-one-harmless-app) · [Report a result](#sanitized-reproduction-report)

A practical record of operating a Xiaomi phone from a Mac through **Xiaomi Interconnectivity → Home screen+ → a computer-use assistant**. The useful part is the verification loop and recovery procedure: observe the live window, take one action, then check the phone's new state.

**Status:** documentation-only initial edition. The supplied field notes report successful operations on one setup. No reusable phone-control source code was supplied, and no hardware run was repeated while preparing this edition. This repository contains no SDK, driver, proprietary tool implementation, or ready-to-run automation. See [the evidence and test record](#evidence-and-validation).

## Before you start

This guide is for **Mac users with a compatible Xiaomi phone who already have an authorized AI client capable of controlling native Mac windows**. It describes AI phone control through an existing Home screen+ mirror; it does not install or supply that AI capability.

| Check | Ready to try when… | If unavailable |
| --- | --- | --- |
| Phone mirroring | You can manually open and use the full Home screen+ window in Xiaomi Interconnectivity. | Follow the vendor’s supported setup first. |
| Native computer use | Your AI client can observe the live native Mac mirror and perform a bounded input action with your permission. | A normal chat subscription or browser-only tool is not proof of this access. This guide has no universal installer or verified client onboarding path. |
| Owner presence | You can identify the intended app/account, handle authentication and confirm the result yourself. | Keep the task blocked until the owner is present. |

The original AI client build and its public availability were not recorded. **Do not buy a subscription based on this guide alone.** Confirm current native computer-use availability in that client’s official documentation and your own installation. Client compatibility and access are unverified here.

**Recorded setup metadata:** Mac model/macOS, phone model/OS, Xiaomi Interconnectivity version, and AI client/build remain **not recorded**. The dependency table below separates published vendor requirements from those missing measurements. If you try the workflow, complete the [sanitized report](#sanitized-reproduction-report); a blocked attempt is useful evidence too.

For readers searching for **AI control of an Android phone on Mac**, this practice note covers Xiaomi Home screen+ specifically. Other Android brands, iPhone workflows, remote unattended control, and universal Android automation are outside its verified scope.

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
4. Give the assistant [the bounded task prompt](#bounded-task-prompt). Ask only to open the chosen app and verify its landing screen. This repository deliberately specifies no private CUA function names or saved coordinates.
5. For each step: inspect the current live window → identify one target → perform one click or swipe → inspect a fresh image. Prefer accessible controls where present. The recorded phone content generally required visual targeting.
6. Confirm that the intended app actually opened. If the screen did not change, report an unconfirmed action; do not treat a successful tool return as task completion. Stop if the app/target is ambiguous.
7. End the assistant's task and disconnect as below. Record pass/fail using [the blank report](#sanitized-reproduction-report). Keep personal evidence local.

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

No new Mac/phone interaction, independent device reproduction, unattended operation, Windows/Linux/iOS support, or general app compatibility is claimed. [Validation details](#evidence-and-validation) distinguish historical reports from preparation-time checks.

## Contents and contribution

Start with this README or the [Chinese version](#简体中文), then use the two prompt/report templates below. [contribution guide](#contributing) explains how to report a reproduction without sharing private material. [Provenance and third-party notices](#provenance-and-third-party-boundaries) define what is licensed.

## License

[MIT](LICENSE) applies to the original documentation and templates in this repository. Xiaomi, Apple, OpenAI and their products remain subject to their own terms; no vendor software, branding assets, private tool documentation, or third-party source code is redistributed. This is an independent practice record and carries no vendor endorsement.

---

## 简体中文

[English](#)

基于真实 **Mac → 小米互联服务 → Home screen+ 完整手机投屏 → CUA 电脑操作助手** 的实践记录。核心价值是每一步都核验：看实时窗口，做一个动作，再看新画面。

**当前仅交付实践文档与模板。** 提供的现场说明记录了单套环境上的成功操作；没有附独立控制源码，本次整理也没有重新操作 Mac 或手机。项目不提供 SDK、驱动、厂商软件、专属 CUA 实现或可直接运行的自动化程序。详见[验证记录](#evidence-and-validation)。

### 开始前：先确认这三项

适用人群：**使用 Mac、兼容小米手机，并已拥有原生 Mac 窗口操作能力的 AI 客户端的用户。** 本文分享“小米互联完整投屏 + AI 观察、操作与核验”的方法。

1. 先手动打开并操作 Home screen+ 完整投屏，确认厂商连接正常。
2. 确认自己的 AI 客户端确实能观察并操作 Mac 原生投屏窗口。普通聊天订阅或浏览器控制能力，不能证明具备这项权限；本文尚无已验证的通用安装和开通流程。
3. 本人在旁，负责身份验证、辨认账号与确认结果。

原实测的 AI 客户端版本和公开可用性没有记录。**不要仅凭本指南购买订阅**；先核对该客户端的官方说明及自己安装环境中的实际能力。

待补实测信息：Mac 型号与 macOS、手机型号与系统、小米互联版本、AI 客户端名称与版本。当前均标为“未记录”，不把其他设备经历当成本次环境证据。复现成功或遇到阻塞，都可以按[测试模板](#sanitized-reproduction-report)反馈。

### 依赖与权限

| 项目 | 要求与证据边界 |
| --- | --- |
| Mac | 安装[小米官方 App Store 应用](https://apps.apple.com/us/app/xiaomi-interconnectivity/id6673908449?platform=mac)。现场说明未记录原 Mac 型号和 macOS 版本。 |
| 手机 | 需要能实际运行 Home screen+ 的小米手机。原机型、系统版本未记录，不能推断所有 Redmi/POCO 都支持。 |
| 厂商兼容要求 | 2026-10-23 查到的应用说明列出 HyperOS 2、跨设备互联服务 ≥16.00.50、小米互传 ≥3.3.0。这是厂商要求，不是原实测版本，也不保证你的设备可用；以当前官方说明为准。 |
| 连接 | 先由本人通过厂商正常流程完成连接，确认能手动操作完整投屏。本项目不替代配对和身份验证。 |
| AI 环境 | 必须已经具备观察与操作 Mac 原生窗口的电脑操作能力。纯文字聊天、只能控制网页的工具不足以复现；原 CUA 客户端及版本未记录，本项目不提供该能力。 |
| 权限 | 本人同意控制手机，审阅厂商配对/屏幕共享提示，以及具体电脑操作客户端要求的屏幕录制、辅助功能权限。原权限开关清单未记录，不自动授予广泛权限。 |

原方法未使用 ADB、Root、App 接口或聊天数据库读取。不要据此推论其他产品的实现。

### 最小复现：打开一个无敏感内容的 App 并核验

此案例从原有完整投屏流程整理而来；这个具体的低风险验收案例在本次交付中尚未重测。

1. 使用自己的设备，本人在旁。将手机停在无敏感内容的桌面，选计算器等简单目标；避免让 AI 看见通知、私人聊天或账号页。
2. 在 Mac 打开小米互联服务，按正常方式连接。选择 **Home screen+ → On／开启**，进入完整手机桌面。原环境直接点击互联首页的单 App 图标曾卡连接或显示异常。
3. 先手动确认投屏能响应。不能响应就先处理厂商连接，不改安全网络设置，不绕过兼容限制。
4. 给 AI [限定任务提示词](#bounded-task-prompt)，只要求打开目标 App 并确认首页。本项目不使用内部专属工具名称或预存坐标。
5. 每步执行：查看实时窗口 → 识别一个目标 → 单次点击或滑动 → 查看新画面。有可访问控件时优先使用；原环境的手机内部界面主要靠截图识别。
6. 看到目标 App 首页后才算完成。工具没报错不等于手机响应；目标不明确或画面未变就停止，报告未确认。换页、缩放、重连后重新观察，旧坐标作废。
7. 结束任务并按下文断开。用[空白测试报告](#sanitized-reproduction-report)记录结果，私人证据留在本地。

**通过条件：** 动作后确认了目标 App 首页，没有发生敏感操作，控制会话已结束。没有原生窗口权限、配对未完成、投屏卡住、目标不明确或结果不可见，都应记为阻塞/失败。

后续如另行授权写入，可以参考原说明中的日历案例：建立提醒 → 保存 → 重新打开 → 核对日期时间与闹钟开关。本项目不附私人提醒内容，本次也没有新建日历事件。

### 原实测中的问题

| 问题 | 处理方式 |
| --- | --- |
| 单 App 投屏卡住或异常 | 原环境改用完整 Home screen+ 后跑通；不是通用修复保证。 |
| 双开 App／多个账号 | 先请本人识别正确账号。角标含义依设备而定，不能照搬原机规则。 |
| 中文粘贴成上一次内容 | 提交前核对完整输入。原手机表单 Ctrl+A 可用、Cmd+A 不可靠；其他界面未验证。 |
| `noWindowsAvailable`、窗口丢失、截图失败 | 先重新查看当前窗口，不能直接判定锁屏；停止盲点，必要时关闭投屏并从 Home screen+ 重连。 |
| 密码、Touch ID、屏幕使用时间限制 | 停止，由本人处理。本指南不要求修改限制或绕过验证。 |

### 安全边界

- 只操作已授权设备与明确任务。截图可能包含任务以外内容，先考虑 AI 服务的数据处理方式。
- 演示不发消息、不购买、不读凭据、不改安全网络设置，也不操作门禁等实体设备。
- 另行授权的提交操作，仍要先核对完整文本和账号；实体效果需现场确认，不能把界面成功当成实体完成。
- 不读取配对文件、令牌、Cookie、聊天数据库、设备标识；不上传截图、通知、私人日志或剪贴板历史。
- 适合本人在旁、几步能结束的辅助操作。无人值守稳定性未验证；反复截图耗时并消耗 AI 额度，没有速度、成功率或额度测量数据。

### 断开与撤销

1. 明确要求 AI 停止，确认没有继续输入，并通过其客户端结束电脑控制会话。
2. 在小米互联服务关闭/停止 Home screen+，确认投屏消失，Mac 输入不再传到手机。关闭窗口不等于撤销长期配对。
3. 不再需要互联时，通过厂商当前设备移除/取消配对界面处理。不再需要 AI 控制时，在 macOS 系统设置检查并撤销对应客户端的屏幕录制、辅助功能权限，名称依版本而异。
4. 以上是建议的本人核验步骤，原说明没有记录断开与撤权实测。若不能确认断开，先停止相关客户端与互联应用，并在手机端核实，再离开设备。

### 已验证与未验证

提供的现场说明报告过：打开 App、读取 App 信息、创建日历提醒并重新打开核对；也报告过现场确认的实体结果，但本项目不提供该操作路线。原始逐步记录、确切环境版本、重复次数、耗时及断开测试均未提供。

本次整理只做离线文件检查，没有重新实测硬件，不宣称跨设备通用、稳定无人值守或支持 Windows/Linux/iOS。详见[测试与证据边界](#evidence-and-validation)。

### 贡献与许可

复现反馈请按[贡献指南](#contributing)提供无敏感信息的环境版本和结果。[来源与第三方说明](#provenance-and-third-party-boundaries)列明权属范围。原创文档与模板采用 [MIT](LICENSE)；厂商应用、品牌、AI 服务和工具仍受各自条款约束，未随项目分发，也无厂商背书。

---

## Bounded task prompt

This is a human-readable prompt template, not executable code. Replace only `<APP_NAME>` with a harmless app you own. Do not paste account details, device identifiers, pairing material, or credentials into it.

### English

Use the already connected full Home screen+ window in Xiaomi Interconnectivity on my Mac to open `<APP_NAME>` and verify its landing screen. I am present. Inspect the current live window before acting, perform only one click or swipe at a time, and inspect a fresh image after every action. Prefer accessible controls where available; never reuse old coordinates after a layout or connection change. If multiple app/account icons exist, stop for my identification. Stop if the target is unclear, authentication is requested, the window disappears, or the image does not establish the result. Do not send messages, submit forms, make purchases, change settings, or operate physical devices. End with the observed result and stop control. I will handle disconnection and verify it.

### 简体中文

通过 Mac 上已经连接的小米互联服务 Home screen+ 完整投屏，打开 `<APP_NAME>` 并确认首页。我本人在旁。每步先看实时窗口，每次只点击或滑动一次，动作后查看新画面；有可访问控件时优先使用，布局或连接变化后不复用旧坐标。多个 App／账号图标先停下让我辨认。目标不明确、要求身份验证、窗口消失或结果无法确认时立即停止。不发消息、不提交表单、不购买、不改设置、不操作实体设备。最后只报告实际看到的结果并停止控制，由我处理并核验断开。

---

## Sanitized reproduction report

Blank template. Nothing below is a completed hardware test. Use public product/version names only; do not attach screenshots or raw logs.

- Date and timezone: `<DATE_AND_TIMEZONE>`
- Mac model family / macOS version: `<PUBLIC_MODEL_AND_VERSION>`
- Phone model family / OS version: `<PUBLIC_MODEL_AND_VERSION>`
- Xiaomi Interconnectivity Mac app version: `<VERSION>`
- Phone interconnectivity / Xiaomi Share versions: `<VERSIONS>`
- Computer-use client / version and native-window capability: `<PUBLIC_CLIENT_AND_VERSION>`
- Existing permission categories used (no identifiers): `<PERMISSION_CATEGORIES>`
- Manually working full Home screen+ before AI input: `<YES_NO_BLOCKED>`
- Harmless target app: `<APP_NAME>`
- One action and fresh observation, summarized without private contents: `<OBSERVATION>`
- Intended landing screen confirmed: `<YES_NO_UNCONFIRMED>`
- Assistant control stopped: `<YES_NO_UNCONFIRMED>`
- Mirroring stopped and input no longer reaches phone: `<YES_NO_UNCONFIRMED>`
- Optional persistent pairing/permission revocation verified: `<YES_NO_NOT_TESTED>`
- Overall outcome: `<PASS_FAIL_BLOCKED>`
- Limitations / recoveries: `<SANITIZED_SUMMARY>`

Never include serial numbers, personal account names, local paths, IP/MAC addresses, pairing codes, tokens, private notifications, conversations, or clipboard content. A pass requires observed app launch and verified session ending; skipped checks remain skipped.

---

## Evidence and validation

Prepared 2026-10-23. Historical operations and preparation-time checks are different evidence classes.

### Supplied field-note evidence

The maintainer supplied a Chinese practice note describing Mac + Xiaomi Interconnectivity + full Home screen+ + the CUA available in that session. Its private original and correspondence are not included. The note reports the following; raw traces and screenshots were not supplied for public inspection.

| Observation | Status | Limits |
| --- | --- | --- |
| Launching apps in full phone projection | Reported successful in supplied notes | One setup; exact versions, repeats and timing absent |
| Reading app information | Reported successful | Private values and account/order details omitted |
| Calendar reminder saved, reopened, time/alarm checked | Reported successful | Private contents omitted; delivery of the alarm was not documented |
| Physical outcome confirmed by someone present | Reported successful | No reproduction route published; UI confirmation alone would be insufficient |
| Individual-app projection stall/display trouble | Reported failure | Full Home screen+ later worked; not a controlled comparison |
| Clipboard stale contents; Ctrl+A vs Cmd+A difference | Reported observed | Device/form-specific, no universal shortcut claim |
| Missing windows and screenshot failures | Reported encountered | Not proof of lock state; causes not established |

The field note does not establish the exact execution date, Mac/phone models, OS versions, app/client versions, permission toggle list, reliability rate, latency, usage cost, or successful permission revocation. None is inferred from unrelated device history.

### This edition's preparation checks

- Read the supplied field note and earlier publication handoff; recovered no reusable control scripts. No original implementation was invented to fill the gap.
- Rewrote the method as original English/Chinese documentation plus a bounded prompt and blank report. No private tool schema, personal screenshots, third-party code, application binaries, or pairing artifacts are included.
- Compared the vendor prerequisites with the official App Store listing; these remain vendor prerequisites, not test-environment metadata.
- Performed local file allowlist, text-only, relative-link, sensitive-pattern, and clean Git-history checks. These checks do **not** validate phone control. The final two-file package has no missing local file links; hardware checks remain not run.

### Not performed for this edition

No Mac/phone interaction, live CUA session, Calculator acceptance run, new calendar write, private app inspection, physical-control operation, disconnect/revocation test, or independent device replication. There are no measured success percentages, repeated-run samples, or benchmark results.

### Reproduction acceptance

Follow the README's harmless app-launch procedure and fill in [the blank report](#sanitized-reproduction-report). Confirm the intended screen after the action and verify the control session has ended. Mark blocked or unconfirmed where appropriate. Keep raw evidence local; publish only a sanitized summary. This edition does not yet claim an independently reproducible, version-pinned environment.

---

## Provenance and third-party boundaries

### Original material in this repository

This README and its embedded templates were newly prepared with AI assistance for the maintainer's requested open-source publication. Technical observations were derived from the maintainer-supplied practice note about their own Mac/Xiaomi mirroring session. The private note, addressee, complete conversations, and earlier handoff were not copied into this repository.

No independent phone-control source code was recovered from the supplied files. There is consequently no claim of ownership of a phone-control SDK or of the vendor/CUA implementation. No control scripts were added merely to imply a software framework exists.

The MIT license was selected for this edition's original documentation and templates under the maintainer's current request for an open-source publication. It is not described as a license the maintainer chose in a past conversation. It grants no rights in third-party software or private source material that is absent from the repository.

### Third-party components used externally

| Component | Relationship to this project | Distribution / license boundary |
| --- | --- | --- |
| Xiaomi Interconnectivity and Home screen+ | External mirroring/control dependency | Obtain from the vendor's official channel. No installer, firmware, library, extracted source, logo, or reverse-engineered protocol is included. Vendor terms remain applicable. |
| macOS | External host operating system | Not distributed; Apple's terms apply. |
| Computer-use assistant / CUA | External native-window observation/input capability in the original session | No access entitlement, internal schema, runtime, credentials, or proprietary implementation is supplied. Availability and terms depend on the actual client. |
| Phone apps | External task surfaces | No app code, account content, screenshots, or API access is supplied. App-specific terms remain applicable. |

This edition does not certify every vendor agreement or a particular client's eligibility. Users obtain dependencies legitimately and review their own applicable terms. If access requires accepting new terms or granting permissions, the owner decides; this repository does not automate acceptance or authorize circumvention.

### Primary references checked on 2026-10-23

- [Xiaomi's App Store listing, published by Beijing Xiaomi Co., Ltd](https://apps.apple.com/us/app/xiaomi-interconnectivity/id6673908449?platform=mac): product, published prerequisites and Home screen+ release history. Not evidence of the maintainer's installed versions.
- [MIT license text, Open Source Initiative](https://opensource.org/license/mit): license for original repository material, reproduced in `LICENSE`.

Xiaomi, Home screen+, Apple, OpenAI and Codex are referenced for identification. No affiliation or endorsement is claimed. No program application, third-party terms acceptance, or credential access is part of this documentation release.

---

## Contributing

Useful contributions are small: a sanitized reproduction result, a version-specific correction, or a clearer recovery step grounded in an actual test.

1. Use [the blank report](#sanitized-reproduction-report) and keep observed, unconfirmed, and untested items distinct.
2. Share public model/version names only. Do not upload screenshots, private messages, raw tool logs, device identifiers, network addresses, pairing files, clipboard contents, credentials, or proprietary tool instructions.
3. Do not test by messaging someone, buying anything, changing security settings, or controlling a physical device. Use the README's harmless app-launch case on your own equipment.
4. Keep changes within the Mac + Xiaomi Home screen+ workflow. Proposals for other platforms need separate evidence and must not silently widen compatibility claims.
5. Submit only material you can license under the repository's MIT license; identify and retain any authorized third-party notices. Do not copy vendor software or confidential documentation.

For an accidental secret exposure, do not repeat the secret in a public issue. Stop sharing the affected material and use the relevant service's official revocation procedure. If private vulnerability reporting is available on the repository, use it; no dedicated private contact channel is promised by this initial edition.

---

## Record a short demo

**Status: proposed recording plan; no demonstration video has been recorded or published for this project.**

Record one 30–45 second, owner-supervised run using only a harmless app such as Calculator:

1. Show the public model/version labels for the host OS, phone OS, mirroring app and AI client; exclude device identifiers, pairing information and account names.
2. Show the authorized instruction to open Calculator through the existing full Home screen+ mirror.
3. Show the resulting app screen and the owner’s confirmation. Keep waits or failures visible; label any cuts and do not present a simulated or accelerated action as a real-time hardware result.
4. Stop AI control and verify that mirroring/input has ended. Record any unconfirmed step as unconfirmed.

For a reproduction report, note the versions and the actual outcome using the template above. A recording does not establish broad compatibility or unattended reliability.

录制建议：用 30–45 秒展示“环境版本 → 明确指令 → AI 打开计算器 → 核验画面 → 结束并确认断开”。此处只是录制计划，当前没有已发布演示视频或新增硬件测试。
