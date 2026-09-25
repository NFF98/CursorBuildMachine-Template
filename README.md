# CursorBuildMachine-Template

可重用的 **Generic Cursor Automation Build Machine 母版**。

這個 repository 不承載任何特定產品需求；它提供一套已驗證的 Build Spec → Backlog → Sprint → Cursor → Test/Evidence → Release 治理與自動化框架。

## Role

```text
ROLE = TEMPLATE
PRODUCT_TRUTH = NONE
IMPLEMENTATION = HOLD
STATUS = READY_FOR_PROJECT_CONFIGURATION
```

**不要直接把產品需求或產品 code 長期放在這個母版 repo。**  
正確用法是從此母版建立/複製一個專案專屬 Build repo，再做 Project Configuration。

## Authority Model

```text
External Product Design / Working Current Truth
        ↓
Human approval
        ↓
Immutable Build Spec
        ↓
Backlog
        ↓
Approved Sprint / Task
        ↓
Cursor implementation
        ↓
Test / Evidence / Review
        ↓
Release
```

Build repo 不創造 Product Truth。Raw demand 不能直接變成 implementation truth。

## Project Setup

建立新專案 Build repo 後至少要：

1. 在 `harness/policy/repo-policy.json` 設定 `design_source_repo`。
2. Review `implementation_roots`、`hold_exceptions` 與 governance paths。
3. Review deployment profile。此母版目前保留經驗證的 Cloudflare / Supabase adapter；若專案使用其他 stack，應先替換/擴充 deployment adapter 與 Release validator，再跑 Demo/Attack E2E。
4. 套用 GitHub Ruleset 與 required checks。
5. 視團隊情況設定 CODEOWNERS；單一 owner repo 不應要求作者自己 approve。
6. 執行 Governance / Attack / CI / CodeQL 驗證。
7. 通過 Build Freeze Gate 後，才建立第一份正式 `BS-*`。

## Clean State

母版預設維持：

- Active Build Spec: `null`
- Implementation enabled: `false`
- Active Sprint: `null`
- Active Task: `null`
- Backlog: `HOLD / empty`
- Release: `HOLD`

## Provenance

Generic machine derived from NFF98/NFFBuild@2187ed3ee365bc7b1f50c7196012fe5080583d71, whose full Fake Sprint E2E and hardening gates passed before extraction.

這個 provenance 只說明機器來源，不會把 NodeFF/NFFBuild 的 Product Truth 帶進本 repo。
