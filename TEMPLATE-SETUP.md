# Template Setup Checklist

從此母版建立新專案 Build repo 後：

- [ ] 設定 `harness/policy/repo-policy.json > design_source_repo`
- [ ] Review implementation roots / hold exceptions
- [ ] Review Build Spec IDs / phase convention
- [ ] Review deployment adapter profile
- [ ] 設定 GitHub Ruleset
- [ ] Required checks: `ci`, `attack`, `governance`, `Analyze JavaScript / TypeScript`
- [ ] PR required
- [ ] Conversation resolution required
- [ ] Squash-only merge
- [ ] Block deletion / force push
- [ ] No bypass
- [ ] 單一 owner：approval count 0、Code Owner review off
- [ ] 多 reviewer：再評估 required approval + CODEOWNERS
- [ ] Governance Attack Dry-run PASS
- [ ] Build Machine E2E PASS
- [ ] 第一份正式 Build Spec Freeze 經 Human approval
