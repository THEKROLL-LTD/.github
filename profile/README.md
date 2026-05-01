<div align="center">

# THEKROLL LTD

**High-stakes engineering for when "good enough" fails.**

Resilient SaaS platforms · Emergency DevOps rescue · Applied AI engineering · Hardened OSS supply chain<br>
Interim CTO & technical leadership for critical projects.

[Website](https://thekroll.ltd) · [LinkedIn](https://www.linkedin.com/company/thekroll-ltd) · `info@thekroll.ltd`

</div>

---

## About

THEKROLL LTD is an independent engineering company based in Cyprus, operating worldwide.
We architect, rescue and operate production systems where downtime, data loss or
compliance failure are not acceptable outcomes.

Our work covers three core domains:

- **Hybrid-Intelligence SaaS** — AI-accelerated implementation under human architectural
  governance. Strict compliance, rigorous review, certified output.
- **Sovereign Kubernetes** — Self-hosted clusters on bare metal (K3s / RKE2). Full
  lifecycle ownership, predictable cost, no vendor lock-in.
- **Applied Deep Tech** — Custom PyTorch models, scalable RAG pipelines and
  distributed compute. Real engineering, not API wrappers.

In addition we accept **Interim CTO and Emergency Leadership** mandates: stabilising
failing projects, restructuring teams and enforcing technical discipline under pressure.

## Doctrine

1. **Resilience First** — We assume failure. Networks lag, disks rot, services crash.
2. **Synthetic Code, Human Governance** — AI generates syntax; we architect logic and audit output.
3. **Critical Path Defense** — We build automated "Iron Domes" around core business logic and data integrity.
4. **Speed Is Security** — Rescue protocols deploy in minutes, not days.

## Open Source & Public Repositories

We publish a small set of **hardened OSS supply-chain tools** that we run in
production for our own internal mirrors. Public repos are provided **as a reference**,
with no SLA. Production users should fork and operate their own copy; the intent is
to make the practice visible, not to run a managed service.

The pipeline now runs in production across multiple upstream shapes with very different
runtime constraints. That diversity forced us to formalise distinct hardening approaches
instead of pretending one Dockerfile pattern fits everything. The table below maps each
fork to its path.

| Repository | Type | Hardening path & purpose |
|---|---|---|
| [`oss-mirror-build`](https://github.com/THEKROLL-LTD/oss-mirror-build) | Template (Apache-2.0) | GitHub Actions pipeline for mirroring, scanning and hardening upstream OSS container images. CycloneDX SBOMs, Trivy filesystem + image scans, automatic CVE issues, override-drift detection on the upstream Dockerfile, digest-pinned PRs as the human review gate. |
| [`mirror-Gokapi`](https://github.com/THEKROLL-LTD/mirror-Gokapi) | Live mirror | **Path 1: distroless rebase** of `Forceu/Gokapi` → `ghcr.io/thekroll-ltd/gokapi`. Static Go binary on `gcr.io/distroless/static`. Image AGPL-3.0. |
| [`mirror-Plausible`](https://github.com/THEKROLL-LTD/mirror-Plausible) | Live mirror | **Path 2: hardened Alpine** mirror of `plausible/analytics` → `ghcr.io/thekroll-ltd/plausible`. Pinned base by digest, certbot stripped, OCI labels stamped. Distroless infeasible: Elixir/OTP needs ERTS plus a shell entrypoint. Image AGPL-3.0. |
| [`mirror-uptime-kuma`](https://github.com/THEKROLL-LTD/mirror-uptime-kuma) | Live mirror | **Path 3: full re-base** of `louislam/uptime-kuma` → `ghcr.io/thekroll-ltd/uptime-kuma`. Userland rebuilt end-to-end on `node:22-bookworm-slim`; chromium / mariadb / apprise / cloudflared / fonts replicated so no upstream feature regresses. Apt-layer CVEs land at Debian's cadence, not louislam's. Image MIT. |

**Engineering principles for everything we publish:** distroless or hardened base images ·
digest pinning · reproducible builds · CycloneDX SBOM per release · continuous CVE scanning
with **Trivy** on built artifacts · supply-chain transparency.

> **Scope: enterprise SBOM & CVE audit.** This pipeline gates every release on known CVEs in
> third-party dependencies that survive into the artifact. Source-level bugs in upstream
> codebases that never reach CVE/GHSA stay in the upstream project's tracker. We mirror,
> we don't fork. The signal we care about is what lands in the public vuln DBs that Trivy
> consumes.
>
> AI-assisted code review, led by Anthropic's **Claude Security** (Enterprise preview,
> rolling out to Claude Code users), is about to widen the funnel feeding those DBs
> significantly. More issues found earlier in major OSS projects, a meaningful fraction
> disclosed and assigned a CVE ID. The CVE volume an enterprise has to triage is going up,
> not down.
>
> That is what this pipeline is for: making rising CVE volume **manageable**. Automatic
> issue filing per finding, waivers with a git-tracked audit trail, scheduled rescans of
> already-published images so newly-disclosed CVEs surface without a rebuild, gated releases
> on every nightly. We don't try to find the bugs ourselves. The moment someone else does,
> you know about it on your own images, with SBOM and audit trail attached.

## Selected Work

- **Sovereign Document Engine** — GDPR-hardened legal document generation platform
  with decoupled, pixel-perfect PDF rendering. Data residency in Germany.
  → [docs101.com](https://docs101.com)
- **Heavy Transport Operations Grid** — Unified TMS / ERP / CRM for heavy-haulage
  logistics. Real-time geospatial route optimisation.
  → [heavylogix.com.cy](https://heavylogix.com.cy)

## Engage

We accept a limited number of mandates per quarter. Typical engagements:
technical due diligence, architecture reviews, disaster recovery, interim
technical leadership, and long-term platform partnerships.

→ **[thekroll.ltd](https://thekroll.ltd)** &nbsp;·&nbsp; **info@thekroll.ltd**

---

<sub>THEKROLL LTD · Registered in Cyprus · Founded 2024 · Architecting scalable SaaS, mastering emergency ops &amp; AI.</sub>
