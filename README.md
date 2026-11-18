# Governance of Delegated Authority Report

## [Latest Editor's Draft](https://identity.foundation/governance-of-delegated-authority-report/)

- [v1.0-rc1 snapshot](https://identity.foundation/governance-of-delegated-authority-report/v1.0-rc1/)

## Getting Started

The report is written in Markdown under [`spec/`](./spec) and rendered with a vendored copy of
[Spec-Up](https://github.com/decentralized-identity/spec-up) (see [SPEC-UP.md](./SPEC-UP.md) for the tool's own docs).

```
git clone git@github.com:decentralized-identity/governance-of-delegated-authority-report.git
cd governance-of-delegated-authority-report
npm ci
npm run dev      # live preview at http://127.0.0.1:5173/
npm run build    # static site in ./build
```

Pushes to `main` are built and deployed to GitHub Pages by `.github/workflows/deploy-spec.yml`.
