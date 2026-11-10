<img src="assets/banner.png" alt="EasyMythic, jimichi, anaba" width="100%">

### Igor Iurtaev

DevOps engineer · Information security at MTUCI, Moscow<br>
[LinkedIn](https://www.linkedin.com/in/syncsyncsync/) · Discord `._sync`

#### DevOps · Sber, Quantum Technologies Center · since Sep 2026

Proposed and led the research lab's move from standalone Docker Compose deployments to a shared
Kubernetes platform in Cloud.ru. Designed and deployed the platform, migrated internal services,
and remain its sole maintainer.

- Built GitOps delivery with Argo CD and GitLab CI, automated image updates, centralized secret
  management with External Secrets, and GitLab SSO. Split 14 research applications into separate
  repositories with independent CI pipelines. Deployed YTsaurus and connected it to the internal
  LLM through MCP.
- Migrated Grafana from Docker Compose to Kubernetes and from SQLite to managed PostgreSQL,
  preserving users, dashboards, alert rules, OAuth and encrypted data source settings. Wrote a
  migration tool, reconciled populated tables after commit, and verified data source access.
- Built backup and recovery workflows with Velero and Kopia, freeze/thaw hooks for consistent
  YTsaurus backups, and cloud S3 storage. Verified recovery after deleting the YTsaurus namespace
  and disks: the service restarted automatically and a 100,000-row table matched its original
  checksum. Separately restored an application from cloud S3 and verified its data with SHA-256.
  Resolved Kopia's incompatibility with the provider's S3 addressing requirements using VersityGW.
- Deployed Prometheus, Alertmanager, Grafana and Blackbox Exporter for nodes, workloads,
  YTsaurus, backup jobs, HTTPS availability and certificate expiry. Verified failure and
  recovery notifications end to end.
- Updated application images and dependencies following a container security audit. Checked
  compatibility, scanned the exact images deployed by CI, and verified service health after rollout.

#### DevOps · fintech platform, remote · May – Sep 2026

Kubernetes, GitOps on GitLab CI, Cloudflare and Imperva in front, 350–400 RPS baseline.

- Layered L7 DDoS protection: geo filter, path allowlist, header rules, challenge on HTML only,
  separate rate limits for pages and login, edge caching. Held up against attacks of up to
  620 million requests a day. Found two bugs in the reference rule set before it went to production:
  one rule never matched, the other blocked every POST from a browser.
- Cloudflare Worker that checks captcha tokens and JWT signatures at the edge, so unauthenticated
  requests never reach the cluster. About $200 a month at full attack volume.
- Edge security review: passwords leaking into ingress logs (proven with a canary password),
  client IP spoofable through `X-Forwarded-For`, load balancers reachable around the CDN,
  secrets in the repository.
- Domain cleanup driven by ingress metrics, not by the list: two domains marked for deletion
  still served 241k and 69k API writes and were kept. Caught a stalled certificate renewal
  that reported `Ready` on a domain with 35 million requests, 25 days before TLS would fail.

<table>
<tr><td><b>Kubernetes</b></td><td>Cloud.ru · Argo CD · External Secrets · cert-manager · Kyverno · ingress-nginx · YTsaurus</td></tr>
<tr><td><b>Edge</b></td><td>Cloudflare WAF, Rate Limiting, Workers, R2, Turnstile · Imperva · CrowdSec · nginx · frp · PROXY protocol</td></tr>
<tr><td><b>Delivery</b></td><td>GitLab CI · GitOps · automated image updates · Docker Compose · Traefik · wrangler</td></tr>
<tr><td><b>Observability</b></td><td>Prometheus · Alertmanager · Grafana · Blackbox Exporter · OpenTelemetry</td></tr>
<tr><td><b>Data &amp; recovery</b></td><td>PostgreSQL · SQLite · Velero · Kopia · S3 · VersityGW</td></tr>
<tr><td><b>Cryptography</b></td><td>AEAD · X25519 · Ed25519 · XChaCha20-Poly1305 · GOST · onion routing</td></tr>
<tr><td><b>Code</b></td><td>Go · Python · C++ · TypeScript · Bash</td></tr>
</table>

<picture>
  <source media="(prefers-color-scheme: light)" srcset="https://skillicons.dev/icons?i=kubernetes%2Cdocker%2Clinux%2Cnginx%2Ccloudflare%2Cgitlab%2Cgithubactions%2Cgrafana%2Cprometheus%2Cpostgres%2Credis%2Cgo%2Cpython%2Ccpp&theme=light">
  <img alt="Kubernetes, Docker, Linux, Nginx, Cloudflare, GitLab, GitHub Actions, Grafana, Prometheus, PostgreSQL, Redis, Go, Python, C++" src="https://skillicons.dev/icons?i=kubernetes%2Cdocker%2Clinux%2Cnginx%2Ccloudflare%2Cgitlab%2Cgithubactions%2Cgrafana%2Cprometheus%2Cpostgres%2Credis%2Cgo%2Cpython%2Ccpp&theme=dark">
</picture>

### Projects

<table>
<tr>
<td width="50%" valign="top">
<img src="assets/easymythic.png" width="64" align="left">
<b>EasyMythic</b> <sub><code>private</code></sub><br>
Mythic+ route planner for World of Warcraft. Pulls top runs from WarcraftLogs, maps noisy
combat-log enemies to dungeon positions with the Hungarian algorithm, exports routes to MDT.<br>
<sub>Go · Gin · PostgreSQL · Redis · React · Leaflet</sub>
</td>
<td width="50%" valign="top">
<img src="assets/jimichi.png" width="64" align="left">
<a href="https://github.com/jimichi-org/jimichi"><b>jimichi</b></a><br>
Messenger with metadata protection: three relays, nested encryption, fixed 512-byte cells,
cover traffic, keys in locked memory outside the Go heap. Includes a traffic-correlation attack to measure it.<br>
<a href="https://jimichi.org">jimichi.org</a> · <a href="https://github.com/jimichi-org">jimichi-org</a><br>
<sub>Go · X25519 · XChaCha20-Poly1305 · Kubernetes</sub>
</td>
</tr>
<tr>
<td valign="top">
<img src="assets/anaba.png" width="64" align="left">
<b>anaba</b> <sub><code>private</code></sub><br>
Aggregator for Japanese underground and archive fashion: one live feed across Mercari, Yahoo! Auctions,
Rakuma and Wunderwelt, 80+ brands, sold-price history, fake-risk flags.<br>
<sub>Go · PostgreSQL · SSE · React</sub>
</td>
<td valign="top">
<img src="assets/mylovelyvn.png" width="64" align="left">
<a href="https://github.com/blsssss/mylovelyvn"><b>MyLovelyVN</b></a><br>
Reading assistant for Japanese visual novels: captures text from the game process, splits it
into morphemes, streams a translation, two-level cache.<br>
<sub>Go · Wails · React · SQLite</sub>
</td>
</tr>
<tr>
<td valign="top">
<img src="assets/oracle.png" width="64" align="left">
<b>Oracle DBA agent</b> <sub><code>private</code></sub><br>
LLM agent that administers Oracle Database: writes and runs SQL, fixes ORA- errors, solves CTF
tasks. 1,000 traces collected, model fine-tuned on the successful ones with QLoRA.<br>
<sub>Python · Ollama · Oracle 26ai · QLoRA</sub>
</td>
<td valign="top">
<img src="assets/polycopy.png" width="64" align="left">
<b>polycopy</b> <sub><code>private</code></sub><br>
Copy-trading bot for Polymarket: fractional Kelly bet sizing, volatility, slippage and daily
loss limits, terminal UI.<br>
<sub>Go · PostgreSQL · Redis · Bubble Tea</sub>
</td>
</tr>
<tr>
<td valign="top">
<img src="assets/mzakon.png" width="64" align="left">
<a href="https://github.com/blsssss/mzakon"><b>MZakon</b></a><br>
Legal reference for GTA5 RP government factions: 1,400+ articles, step-by-step procedures,
Windows overlay and iPhone app.<br>
<sub>Python · Flutter</sub>
</td>
<td valign="top">
<img src="assets/anachan.png" width="64" align="left">
<a href="https://github.com/blsssss/anachan-public"><b>Anachan</b></a><br>
UNIX log analysis with local and remote LLMs.<br>
<sub>Go · Vite · TypeScript</sub>
</td>
</tr>
<tr>
<td valign="top">
<img src="assets/ppshkin.png" width="64" align="left">
<a href="https://github.com/blsssss/PPshkin"><b>PPshkin</b></a> <sub><code>hackathon finalist</code></sub><br>
Finalist at the <a href="https://hackathon-max.vk.company/">MAX Hackathon 2026</a>:
one of 40 finalist teams selected from 442 submitted prototypes. Finals at Kazan Digital Week
in Kazan; no prize placement.<br>
Bot and mini app in the MAX messenger for small cafes and bakeries: food diary from photos,
a dish nearby that fits the calories left for the day, end-of-day items at a discount instead of
write-offs, bookings by code and QR.<br>
<sub>TypeScript · Fastify · PostgreSQL · React · MAX UI</sub>
</td>
<td valign="top">
<img src="assets/mamori.png" width="64" align="left">
<a href="https://github.com/blsssss/mamori"><b>mamori</b></a> <sub><code>coursework</code></sub><br>
Checks that the antivirus and the firewall on a Windows PC react to a test, not only that they
are installed: EICAR and AMSI samples, a temporary firewall rule through UAC, a verdict backed by
the findings. Visual novel interface with Reimu Hakurei.<br>
<sub>Go · Wails · Svelte · TypeScript · WMI · COM</sub>
</td>
</tr>
</table>

Also: Telegram and MAX bots for order tracking, a Mercari watcher, an FL.ru job feed,
[ip-echo](https://github.com/blsssss/ip-echo), [booking-go](https://github.com/blsssss/booking-go),
[online-sub](https://github.com/blsssss/online-sub).

### Contact

[![LinkedIn](https://img.shields.io/badge/LinkedIn-syncsyncsync-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/syncsyncsync/)
![Discord](https://img.shields.io/badge/Discord-.__sync-5865F2?style=flat-square&logo=discord&logoColor=white)
