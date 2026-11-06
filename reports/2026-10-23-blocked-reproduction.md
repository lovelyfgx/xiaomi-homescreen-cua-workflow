# Hardware reproduction follow-up — 2026-10-23

**Historical stage:** this report preserves the earlier failed attempt. Later same-day recovery, Calculator verification, local video preparation and projection closure are recorded in the [control recovery follow-up](2026-10-23-control-recovery.md). The statements below describe this earlier stage only.

**Outcome: BLOCKED.** A live Home screen+ mirror was observable, but coordinate input failed with `Computer Use server error -10005: noWindowsAvailable`. Calculator was not opened and no demonstration video was recorded.

This is a sanitized maintainer-side follow-up to the initial documentation edition at commit `43d191ad6be6424941b2797a02cfea5060cd0144`. It is one environment's observation, not independent replication or a compatibility guarantee.

## Measured environment

Date: 2026-10-23, America/New_York. Installed host metadata was read at approximately 08:51 local time; this follow-up's UI observations occurred immediately before and after that check.

| Item | Observation | Evidence / limit |
| --- | --- | --- |
| Mac model family | MacBook Pro, model identifier `MacBookPro17,1` | Public model identifier from the host; no serial number collected |
| macOS | 26.6.2, build 25G83 | Installed system metadata |
| Xiaomi Interconnectivity | 3.0.200, build 566 | Installed application metadata |
| Phone model family | Redmi Note 12 Turbo | Current mirroring application UI; phone Settings was not opened |
| Computer-use host | Installed app metadata label: ChatGPT; version 26.1016.62342, build 21477 | Label/version read from the installed host application; current session exposes native Mac window observation and input tools |
| Phone OS | Not verified | No version inferred from vendor prerequisites |
| Phone interconnectivity / Xiaomi Share versions | Not verified | Not inspected |
| Calculator version | Not verified | App was not opened |
| Existing capture / accessibility permission toggles | Not inspected | Tool behavior does not establish the exact permission configuration |
| Manual phone input before the test | Not verified in this follow-up | A visible mirror alone does not prove manual or automated control |

The host build records this test environment only. It does not establish public availability, subscription eligibility, or a supported onboarding route.

## Observations in this follow-up

1. Bound the existing Xiaomi Interconnectivity full Home screen+ window and obtained a fresh screenshot of the phone's home screen.
2. Attempted one low-risk click in an empty home-screen area. The input tool returned `Computer Use server error -10005: noWindowsAvailable`.
3. Inspected the application's native Shortcuts menu and invoked Return to Home screen. The phone was already on its home screen, so that action's phone-side effect was **not independently distinguishable**.
4. Used the native window zoom control. A fresh screenshot visibly showed the mirror at a changed size. This confirms a host-window operation, not a successful phone input.
5. Using the new screenshot, attempted one horizontal home-screen swipe. The tool returned the same `noWindowsAvailable` error. No further coordinate input was attempted.
6. Closed the mirror with its native close control. The current UI returned to the Xiaomi Interconnectivity main window and showed **Home screen+ → Turn on**. The application still reported its device connection; closing the projection did not unpair the device.
7. Stopped assistant input. No additional phone actions were sent.

## Acceptance result

| Check | Result |
| --- | --- |
| Live phone mirror observable | PASS |
| Native window resize | PASS, visibly observed |
| Phone coordinate click | FAILED: `noWindowsAvailable` |
| Phone coordinate swipe after resizing | FAILED: `noWindowsAvailable` |
| Calculator landing screen | NOT REACHED |
| Arithmetic execution and result check | NOT RUN |
| Assistant input stopped | YES |
| Home screen+ window closed / Turn on shown | YES, observed in current UI |
| Physical confirmation that later Mac input cannot reach the phone | NOT TESTED; no post-close input was attempted |
| Persistent device pairing or permissions revoked | NOT TESTED / NOT CHANGED |
| 30–45 second demonstration video | NOT PRODUCED |

**The full reproduction acceptance case did not pass.** Closing the visible projection is narrower evidence than revoking permissions or proving every possible input route is disconnected.

## Earlier same-day recovery record

An existing local record from approximately 08:39 in America/New_York reports that rebinding, raising/selecting the mirror, reconnecting Home screen+, and resetting the tool runtime did not restore coordinate input. It also reports visually confirmed Open Recents and Return Home menu navigation.

Those are earlier recorded observations. They were not all repeated in this follow-up and must not be counted as repeated successful trials here. The new native resize attempt above also failed to restore coordinate input.

## Interpretation and next verification gate

Observation and coordinate input currently have different outcomes: the mirror can be captured and native window controls respond, while coordinate operations report no available window. The root cause is **unconfirmed**. This result does not prove a phone lock, a network failure, a missing permission, or a general Home screen+ incompatibility.

Before recording a demonstration, first recover one bounded phone input and confirm its expected effect in a fresh frame. Only then open Calculator, execute a harmless calculation, verify the result, end control, and record the actual outcome. A short video remains pending; historical successes, host-window actions, or simulated frames must not be substituted for this run.

## Privacy and publication

This report contains only public model/version labels and a summarized outcome. It includes no screenshot, video, personal device name, serial number, account, address, raw session trace, notification, clipboard content, credential, or private tool schema. No settings or permissions were changed for the test. No messages were sent and no video was published.

## 中文摘要

本次复测结论为**受阻**：能够读取实时手机桌面，也能够通过原生窗口控件缩放及关闭投屏；手机画面的坐标点击、缩放后的滑动均报 `noWindowsAvailable`。这不足以证明锁屏、网络故障或权限缺失，根因仍未确定。

实测环境：MacBook Pro（公开型号标识 MacBookPro17,1）、macOS 26.6.2（25G83）、小米互联服务 3.0.200（566）、Redmi Note 12 Turbo；宿主已安装应用元数据显示名称 ChatGPT、版本 26.1016.62342（21477）。手机系统、计算器及手机互联组件版本未核实。

计算器未打开，运算与结果核验未执行，30–45 秒视频未录制。结束时已关闭投屏，并看到 Home screen+ 的“Turn on／开启”按钮；没有撤销配对或权限，也没有再次发送输入来测试断开后的手机行为。

下一步门槛是恢复一次可观察到结果的手机输入，再录制真实计算器流程。本报告可以作为失败复现反馈，不能用来宣称演示成功或无人值守可靠性。
