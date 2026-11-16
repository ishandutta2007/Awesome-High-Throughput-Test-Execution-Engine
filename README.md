# Awesome-High-Throughput-Test-Execution-Engine

## Top High-Throughput Test Execution Engine Ecosystem

**Curated List of SaaS Platforms & Open-Source GitHub Projects**  
*Focused on Distributed Test Orchestration, Runner Parallelism & Self-Hosted Execution Engines*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **High-Throughput Test Execution Engines**. These tools provide the runtime and orchestration layer for running large test suites at speed—covering everything from commercial cloud grids that scale to thousands of parallel sessions to open-source runners with native sharding, worker management, and CI-native test splitting.

**Examples** include Playwright Test Runner, Cypress Cloud Runner, LambdaTest HyperExecute, Sauce Labs Test Runner, BrowserStack Test Execution Engine, GitHub Actions Runner, CircleCI Runner, and Aerokube Moon (the category leaders).

**Open-source emphasis**: This section highlights every major active project for self-hosted test execution, open-source runner parallelism, and community-driven orchestration—ideal for teams seeking data sovereignty and avoiding per-parallel-session SaaS pricing that compounds as test volume grows. The open-source landscape is genuinely mature: **Playwright** provides native sharding and worker parallelism with zero additional cost [citation:1], **Testkube** offers Kubernetes-native orchestration for any test type, and **Selenium Grid** remains the reference distributed execution architecture.

Contributions welcome! Open an PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [Sector Overview & Market Dynamics](#sector-overview--market-dynamics)
- [SaaS/Hosted Platforms](#saas-products)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## Sector Overview & Market Dynamics

The global test automation and execution orchestration market is estimated at **$35B–$40B** (projected to exceed **$100B+** by the mid-2030s at a ~14% CAGR). The sector is **moderately to highly fragmented** rather than winner-take-all; despite the scale of hyperscalers and cloud giants, the ecosystem remains broadly divided across specialized device cloud grids, CI/CD-embedded execution engines, and rapidly evolving AI-native/open-source testing runtimes.

## SaaS/Hosted Platforms

| Product | Scale (Revenue / Valuation) | Pricing (Starting) | Free Tier Limits / Free Trial | Description |
|---------|-----------------------------|--------------------|-------------------------------|-------------|
| **[AWS CodeBuild](https://aws.amazon.com/codebuild/)** | **~$108B–$129B ARR** (AWS business unit) / Amazon: ~$2T+ market cap | **$0.005/minute** (on-demand `build.general1.small`, 2 vCPU, 3 GB RAM) | **100 build minutes/month** indefinitely on `build.general1.small` (Linux) | Managed build and test runner service with pay-per-minute compute and scalable concurrency. |
| **[GitHub Actions Runner](https://github.com/features/actions)** | **~$2.0B+ ARR** (GitHub subsidiary) / Microsoft: ~$3T+ market cap | **$0.006/minute** (Linux 2-core standard runner; Windows: $0.010/min, macOS: $0.062/min) | **2,000 minutes/month** for free accounts on private repos (unlimited minutes on public repos); self-hosted platform fee is $0.002/min consuming free quota | Native CI/CD runner ecosystem with matrix builds, automated sharding, and self-hosted runners. |
| **[BrowserStack Test Execution Engine](https://www.browserstack.com/)** | **$4.0B valuation** (Series B) / **~$230M–$300M ARR** | **$249/month** (Desktop Automate Pro, billed annually, 1 parallel session with unlimited automated test minutes) | **No permanent free tier**; Free trial provides **100 automated testing minutes** (1-hour max single session duration, 1 parallel test) | Enterprise cross-browser and real mobile device cloud supporting Playwright, Cypress, and Selenium. |
| **[CircleCI Runner](https://circleci.com/)** | **$1.7B valuation** (Series F) / **~$55M–$100M ARR** | **$15/month** (Performance plan base + credit consumption) | **30,000 credits/month** (up to ~3,000 build mins on small containers), 30 concurrent jobs, 5 active users, and 5 self-hosted runners | Cloud CI/CD platform offering dynamic test splitting, timing-based parallelism, and self-hosted runner orchestration. |
| **[Sauce Labs Test Runner](https://saucelabs.com/)** | **~$613M valuation** / **~$92M ARR** | **$149/month** (Virtual Device Cloud, billed annually, 1 parallel session with unlimited automated minutes) | **No permanent free tier**; Free trial provides **28-day access** with **60 total automated/live testing minutes**, up to 3 parallel VMs, and 50 Sauce AI queries | Continuous testing cloud providing virtual device emulators, real mobile devices, and orchestration analytics. |
| **[LambdaTest HyperExecute](https://www.lambdatest.com/)** | **~$400M valuation** (Series D) / **~$120M–$150M ARR** | **$103/month per parallel session** (HyperExecute Linux, billed annually; $159/mo for Windows/macOS) | **300 HyperExecute minutes/month** + **2 concurrent sessions** on the Free forever tier (plus 60 mins/month live browser testing) | High-speed, AI-driven test orchestration platform executing distributed tests across multi-cloud environments. |
| **[Cypress Cloud Runner](https://www.cypress.io/)** | **~$255M valuation** (Series B) / **~$18M ARR** | **$67/month** (Team tier billed annually, or $75/mo billed monthly) | **500 test results/month**, up to 10 user seats, and 30-day run data retention on the Free Starter tier | Cloud orchestration for Cypress tests featuring smart parallelization, flake detection, and test replays. |
| **[Aerokube Moon](https://aerokube.com/moon/)** | **~$1M ARR** / Bootstrapped (unfunded) | **$5/month per parallel session** (Moon on-premise/cloud Kubernetes license) | **4 parallel browser sessions free forever** with no license key required; evaluation keys of custom size available for trials | Kubernetes-native cross-browser test execution grid supporting Selenium, Playwright, Puppeteer, and Cypress. |

## Open-Source GitHub Projects

| Project | Star Badge | Description |
|---------|------------|-------------|
| **[Playwright](https://github.com/microsoft/playwright)** | [![Stars](https://img.shields.io/github/stars/microsoft/playwright?style=social&color=white)](https://github.com/microsoft/playwright/stargazers) | **The most capable open-source runner for high-throughput execution with zero additional cost.** **Apache-2.0**, Microsoft-maintained. **Native `workers`** controls concurrent tests per machine; **`--shard`** splits suites across CI machines. **`fullyParallel: true`** parallelizes within files. **Built-in test isolation** guidance: each test creates its own state—no shared hardcoded users. **Locking for shared resources** (v1.63+): `test('...', { lock: 'resource' }, ...)` prevents specific overlaps without serializing the suite. **Blob report merging** across shards into unified HTML/JSON. **Playwright takes ~65% of new E2E project selection in 2026** and ~5M weekly downloads [citation:1]. **Best for teams wanting native, free parallelism** without a commercial grid. |
| **[Testkube](https://github.com/kubeshop/testkube)** | [![Stars](https://img.shields.io/github/stars/kubeshop/testkube?style=social&color=white)](https://github.com/kubeshop/testkube/stargazers) | **Kubernetes-native test orchestration and execution framework.** **MIT-licensed agent** runs standalone in your cluster. **Orchestrates any test type**—functional, load/performance, security, compliance—without Docker wrapping. **Executors for Postman, Cypress, K6, SoapUI, Artillery, Maven, Gradle, Ginkgo, and custom executors**. **Decouples test execution from builds**; engineers run specific tests on demand via kubectl, API, or CI. **Centralized test results** for QA analytics. **Best for Kubernetes teams wanting vendor-neutral, cluster-native orchestration** across test types. |
| **[Selenium Grid](https://github.com/SeleniumHQ/selenium)** | [![Stars](https://img.shields.io/github/stars/SeleniumHQ/selenium?style=social&color=white)](https://github.com/SeleniumHQ/selenium/stargazers) | **The reference hub-and-node architecture for distributed WebDriver execution.** **Distribute tests across multiple node machines**; each node runs its own allocation. **Selenium Manager** handles driver downloads automatically (v4.6+). **Grid 4** supports distributed tracing and GraphQL status queries. **Best for existing Selenium suites** needing horizontal scale without a commercial grid—the foundation most cloud grids are built upon. |
| **[Selenoid](https://github.com/aerokube/selenoid)** | [![Stars](https://img.shields.io/github/stars/aerokube/selenoid?style=social&color=white)](https://github.com/aerokube/selenoid/stargazers) | **Go-based Selenium hub launching browsers in Docker containers per session.** **`-limit` flag controls total simultaneous container runs** (default 5). **~1 CPU and 1 GB memory per container** as a starting estimate. **Single replica only**—stores session list in memory; use Moon for Kubernetes/OpenShift. **Best for Docker-native Selenium parallelism** on a single host. |
| **[Fairsplice](https://github.com/dashdoc/fairsplice)** | [![Stars](https://img.shields.io/github/stars/dashdoc/fairsplice?style=social&color=white)](https://github.com/dashdoc/fairsplice/stargazers) | **The most focused open-source solution for balanced test splitting on GitHub Actions.** **CircleCI-style test splitting based on timing data**—not just file count. **Three-phase workflow**: split (distribute based on historical timing), convert (extract JUnit XML timings), merge (combine for next run). **Bin packing** assigns heaviest tests first; rolling average keeps last 10 timings per file. **Computes splits once and passes via workflow outputs**—re-running a failed job runs the same tests. **Best for teams on GitHub Actions** struggling with imbalanced partitions. |

### Additional Strong Open-Source Options

| Project | Star Badge | Description |
|---------|------------|-------------|
| **[cypress-parallel](https://github.com/AzizFacilex/cypress-parallel-extended)** | — | **Run Cypress tests in parallel locally—reduce suite execution time by up to 40%.** **Splits spec files across threads** on the same machine. **Weight file support** for balancing based on historical timing. **`CYPRESS_THREAD` environment variable** exposes thread index for per-thread data isolation. **Best for Cypress teams not using Cypress Cloud** wanting local parallelism without cloud costs. |

**Frameworks for building custom systems**: Choose **Playwright** for native, free sharding and worker parallelism with built-in isolation guidance [citation:1], **Testkube** for Kubernetes-native orchestration across any test type, and **Fairsplice** for timing-based balanced splitting on GitHub Actions—all without per-parallel-session SaaS fees.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- High-throughput execution engines execute arbitrary browser automation and code; enforce proper test isolation, environment cleanup, and CI credential scoping to prevent cross-test interference or resource exhaustion.
- **High concurrency without isolation produces flaky tests, not speed.** **Playwright explicitly documents that each test must create its own state and clean up**—shared hardcoded users cause race conditions in parallel runs [citation:1]. **Fairsplice exists because file-count-based splitting produces imbalanced partitions**—timing-based bin packing targets balanced execution time. **Testkube decouples test execution from CI builds**, enabling on-demand test runs rather than waiting for full pipelines. **Selenoid's `-limit` flag is the hard ceiling on parallelism**—default 5 simultaneous containers, and resource consumption scales linearly. **Pricing varies dramatically**: BrowserStack Automate Pro is **$249/month** [citation:15], Sauce Labs Virtual Device Cloud is **$149/month** for 1 parallel with unlimited minutes [citation:2], and CircleCI Free offers **30 concurrent jobs** [citation:5]. **GitHub Actions dropped hosted runner prices up to 39%** but introduced a **$0.002/minute self-hosted platform charge** from March 2026 [citation:4][citation:10]. **Validate whether you need native framework parallelism (Playwright), Kubernetes orchestration (Testkube), or managed cloud grids (BrowserStack, Sauce Labs)** before committing.

---

**Made for QA engineers, CI/CD architects, and teams scaling test execution infrastructure.**  
Let's make high-throughput test execution more open, balanced, and cost-predictable.
