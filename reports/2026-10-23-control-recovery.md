# Control recovery follow-up — 2026-10-23

**Observed outcome: direct phone control recovered, Calculator results were verified, a local sampled-frame demonstration was prepared, and projection closure was visibly confirmed.**

This continues the [earlier blocked reproduction](2026-10-23-blocked-reproduction.md). It records one owner's environment, not independent replication or unattended reliability. The earlier report describes an earlier stage and is retained as evidence. Dates use America/New_York; the late follow-up crossed into 2026-10-24 UTC.

## Successful continuation — 2026-10-25

After the owner opened the full Home screen+ mirror and brought it forward, the original CUA interface completed consecutive coordinate clicks and drag gestures. The assistant independently navigated usage statistics, system information, storage, notifications and battery pages, inspected fresh states, and returned to the phone Home screen. No `noWindowsAvailable` error was observed in this continuation. The owner did not have to click through each of these pages.

The **My device** page visibly reported **HyperOS 3.0.5.0.VMRCNXM**. Calculator version and phone interconnectivity component versions remain unverified. This section publishes only the navigation chain and public software version: no usage durations, notification counts or contents, storage occupancy, accounts, screenshots or private logs are included.

Foregrounding preceded success in this run; it was not isolated as a causal variable and is not established as a sufficient or lasting fix. The earlier failures remain relevant. This does not demonstrate unattended reliability, automatic recovery, or cross-device compatibility. Returning to Home ended the navigation task; it is separate from the earlier demonstration's verified projection closure.

The owner also authorized sharing the reviewed, sanitized 40-second Calculator short video. The supported browser file chooser required an additional extension permission to access local file URLs. No permission was changed, and no video was uploaded. The text delivery proceeds while the local video remains available for a later authorized upload path.

2026-10-25 续测中，本人打开完整投屏并置前后，原 CUA 连续点击和拖动成功；助手独立进入使用统计、系统、存储、通知、电池页面，最后返回主屏幕，本次未出现此前的窗口错误。My device 核验系统版本为 HyperOS 3.0.5.0.VMRCNXM，计算器版本仍未核实。置前只是成功前发生的条件，不能据此确认根因或保证以后恢复，也不承诺无人值守。公开记录仅保留导航链和系统版本，不包含任何用户使用数值、通知、存储占用、账号或截图。

## Later reliability follow-up — 2026-10-24

After the completed demonstration, coordinate input failed again. The owner reported placing both windows on the same ordinary desktop and later enabled the mirror pushpin; fresh click attempts still returned `noWindowsAvailable`. Menu-driven Home navigation and keyboard search visibly reached the phone. The earlier recovery is therefore a phase-specific result, not a durable repair. The current root cause remains unconfirmed.

A local read-only diagnostic initially filtered ordinary windows only. Removing that filter revealed the pinned projection at a nonzero window layer; its visibility flag was absent. This demonstrates a limitation of the diagnostic, not proof that pinning caused the input failure or that the window was off-screen. The owner then temporarily disabled the pin: the same projection changed from layer 3 to layer 0, but a fresh click on the same harmless target still failed before dispatch. Both pin states failed in this comparison. The owner subsequently restored pinning; this is not evidence that pinning causes or repairs the failure.

The [official macOS Computer Use guide](https://learn.chatgpt.com/use-cases/use-your-computer-with-codex) supports background use while the owner uses other applications. Keeping the projection constantly frontmost or stopping all owner input is not a normal operating requirement established by this report.

续测再次失败，因此不能把同桌面或图钉写成稳定解决方法。置顶窗口可能不在普通窗口层，诊断不应把这类窗口过滤掉；可见性字段缺失要记为未知。后台使用是产品支持的方式，当前这套投屏环境的点击稳定性仍待解决。

## What restored input in the earlier phase

The phone mirror could be captured even while its Mac window was absent from the current visible desktop. Native menus and some keyboard input also worked in that condition, while coordinate clicks repeatedly returned `noWindowsAvailable`.

A read-only host-window check showed that the phone window existed but was marked off-screen. Existing accessibility trust was present. Raising, rebinding and reconnecting the mirror did not reliably change that state.

The owner first brought the full phone window forward. The visibility flag became true and a coordinate click opened a phone settings page. After switching back to the assistant window, the phone window became off-screen again and the next coordinate click failed.

The owner then exited the assistant's full-screen desktop space and placed the assistant and phone mirror together on one ordinary desktop. The phone remained on-screen even when the assistant was frontmost. Multiple direct phone clicks, a drag gesture, and six consecutive Calculator button presses succeeded through the original computer-use interface. Calculator visibly returned **12 × 34 = 408**.

This before/after sequence supports **current desktop-space visibility** as a major factor in this run. It does not establish the cause of every `noWindowsAvailable` error, nor prove that visibility is the only condition required. No version change or new permission grant was needed for this recovery.

## Demonstration and session ending

After the first calculation, the input tool explicitly reported that the Mac was locked. Input stopped until the owner manually unlocked it and confirmed that both windows remained on the same ordinary desktop. No alternative backend was used to bypass the lock.

The accepted recording attempt then captured **7 + 5 = 12** and the subsequent projection closure. A fresh main-window image showed **Home screen+ → Turn on**. This establishes visible projection closure at the end of that demonstration. It does not establish persistent unpairing, revoked permissions, or a test that every possible later Mac input route is disconnected.

Earlier recording attempts were not accepted: one produced an unintended expression; another had a local capture-state bookkeeping error. Their frames were not mixed into the accepted demonstration. The arithmetic result and projection closure were inspected before the accepted take was processed.

## Checks completed

| Check | Result |
|---|---|
| Full Home screen+ projection | PASS |
| Current desktop visibility check | PASS after owner placed both windows together |
| Direct coordinate click | PASS, multiple observed phone navigation steps |
| Phone drag gesture | PASS, settings list visibly moved |
| Calculator landing screen | PASS |
| Initial arithmetic check | PASS: `12 × 34 = 408` visibly displayed |
| Accepted demonstration arithmetic | PASS: `7 + 5 = 12` visibly displayed |
| Floating color-correction shortcut | Owner requested removal; Off state and disappearance visually verified |
| Color correction itself | Already Off; left Off |
| Experimental native input alternative | NOT VERIFIED; disabled. Native diagnostics are read-only |
| Local 30–45 second demonstration | PREPARED: 40.000-second edited video from real sampled frames |
| Original-timing local video | PREPARED: 65.033-second encoded video preserving the source timeline |
| End-of-demo projection closure | PASS: fresh image showed Home screen+ → Turn on |
| Post-close phone-side input test | NOT TESTED |
| Persistent pairing or permissions revoked | NOT TESTED / NOT CHANGED |
| Video publication | NOT PUBLISHED; excluded from this public package |

The measured host and mirroring versions remain those in the [earlier environment table](2026-10-23-blocked-reproduction.md#measured-environment). Phone OS was subsequently verified on 2026-10-25 as HyperOS 3.0.5.0.VMRCNXM; phone interconnectivity components and Calculator versions remain unverified.

## Video method and evidence limits

The accepted take consists of **81 real screenshot samples over 65.016 seconds**, not a continuous system screen recording. No audio was captured. Only this take was used in the two local videos.

- The **40.000-second short cut** preserves every source sample in order and shortens only three intervals without new samples. Its on-screen caption identifies live sampled frames and shortened pauses.
- The **65.033-second original-timing version** preserves the source sampling timeline and end time, rounded to encoded video frames. Gaps hold the last available real sample; unobserved motion is not reconstructed.
- The unsampled intervals were 11.427, 10.228 and 25.526 seconds. A 30 fps encoding rate repeats sampled images and must not be read as the original acquisition rate. The first sample at 0.081 seconds is displayed from video time zero.
- Phone status areas and prior calculation history were excluded or covered. The final host-window view is restricted to the Home screen+ status area; surrounding device, account and location details are excluded. Local processing notes, encoded-media metadata and checksums accompany the videos.

The videos remain local for owner review. This public package includes no video, raw screenshot, action log, private phone usage report or control implementation. It provides a sanitized account of what was observed, not a speed, success-rate or unattended-operation benchmark.

## Recovery sequence to reuse

1. Open the **full Home screen+** phone projection and complete any normal owner authentication.
2. If input is blocked, inspect the full mirror and current desktop visibility, including nonstandard window layers when pinning is enabled. Same-desktop placement restored an earlier phase but was not sufficient in later tests. A readable screenshot alone is not proof of working input.
3. Read the current window state and a fresh phone image. Verify one harmless action before starting the actual task; do not reuse coordinates after a layout or connection change.
4. When a capture error occurs after an action, inspect the new phone state before retrying. During this run, one capture error occurred after Settings had already opened.
5. Distinguish window visibility from an explicit Mac-lock or password/Touch ID prompt. Authentication requires the owner. After unlock, inspect the current state before continuing.
6. Keep an attempt log with observed result and evidence limits. If recording, isolate failed takes and declare sampling gaps or timing edits.
7. Close the projection when the task is complete and inspect a fresh **Home screen+ → Turn on** state. Record unpairing, permission revocation, or post-close input checks separately if performed.

No new permission, network/security setting change, message sending or video publication was part of this follow-up. The requested color-correction shortcut was the only phone setting changed for the demonstration.

## 中文记录

本轮已恢复真实手机操作。关键对照是：手机窗口虽然能被截图，但不在当前桌面时，坐标点击反复失败；本人退出助手全屏、让助手与完整手机投屏同处普通桌面后，连续点击和拖动恢复。先验证 **12 × 34 = 408**；随后 Mac 明确锁定，由本人解锁后继续。这个恢复结论适用于本轮观察，不能解释所有窗口错误。

合格演示验证了 **7 + 5 = 12**，结束时关闭投屏，并用新画面确认 **Home screen+ → Turn on**。本地已生成 40 秒短版和约 65.033 秒原时序版。两者来自 81 张真实操作的实时截图采样，**不是连续系统录屏**。短版只缩短三段无新采样的等待，全部源帧保留且顺序不变；原时序版在空档保持上一张真实画面。历史计算、账号、位置等内容已从交付视频中遮盖或裁除，失败尝试没有混入合格演示。

用户要求关闭的色彩校正快捷方式已显示 Off，悬浮按钮消失；色彩校正本身原来就是关闭状态。实验性的原生替代输入没有验证成功，已禁用；原生诊断仅保留只读检查。没有新增权限、发送消息、改变网络或安全设置，也没有发布视频。

投屏关闭是已观察结果，不等于取消长期配对、撤销权限或证明所有输入渠道断开。手机系统已于 2026-10-25 核验为 HyperOS 3.0.5.0.VMRCNXM；计算器版本、跨设备兼容性和无人值守可靠性仍未验证。公开包只包含脱敏文档，不包含视频、私人原始记录或手机使用情况。
