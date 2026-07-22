<h1>Security Issue Check: A Practical Guide to Identifying, Verifying, and Reporting Vulnerabilities</h1>

<!-- wp:heading -->
<h2 class="wp-block-heading">Overview of the <span class="highlight">security issue check</span></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>A <span class="highlight">security issue check</span> is a structured process used to discover, validate, prioritize, and remediate vulnerabilities in systems, applications, infrastructure, and operational practices. This documentation provides step-by-step guidance, tooling recommendations, verification methods, triage criteria, reporting templates, and remediation workflows to help teams establish a reliable, repeatable process.</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table class="has-fixed-layout"><thead><tr><th>Data Point</th><th>Value</th><th>Unit/Type</th><th>Context/Notes</th></tr></thead><tbody><tr><td>Number of distinct process phases described</td><td>4</td><td>count</td><td>Discover, validate, prioritize, remediate</td></tr><tr><td>Scope of targets</td><td>4</td><td>categories</td><td>Systems, applications, infrastructure, operational practices</td></tr><tr><td>Number of support components provided</td><td>7</td><td>count</td><td>Step-by-step guidance, tooling recommendations, verification methods, triage criteria, reporting templates, remediation workflows, process reliability/repeatability</td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">When to run a <span class="highlight">security issue check</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Before production releases and after major code changes</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>On a fixed cadence (e.g., weekly SCA, monthly SAST/DAST, quarterly penetration testing)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>When new dependencies or third-party services are introduced</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>After significant configuration changes in cloud, network, or identity providers</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>In response to emerging threats or new CVEs affecting your stack</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">Scope and asset inventory</span></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Start by defining the <span class="highlight">scope</span> and building an up-to-date <span class="highlight">asset inventory</span> so that checks are comprehensive and compliant.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Applications: web, mobile, APIs, background workers, CLIs</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Infrastructure: servers, containers, Kubernetes clusters, serverless functions</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Networks and endpoints: firewalls, VPNs, desktops/laptops</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Cloud resources: IAM, storage buckets, databases, message queues</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Third-party services: SaaS, open-source dependencies, external APIs</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Data categories: PII, PHI, payment data, secrets</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Prerequisites</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Documented architecture diagrams and data flows</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>An asset register with owners and business criticality</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Access to logging, monitoring, and configuration management systems</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>A vulnerability disclosure and response policy</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Legal approval for scanning and testing target environments</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">Checklist: Core areas to examine</span></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Use this concise, practical checklist to review the most important dimensions of your project or product. Each area includes what to look for, why it matters, and quick examples to help you assess quality with confidence.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Objectives and scope</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li><strong>Clarity:</strong> Are the goals defined in one or two measurable statements? <em>Example:</em> “Reduce average response time from 800ms to 300ms within Q3.”</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Boundaries:</strong> Is it clear what’s in scope and explicitly out of scope? <em>Example:</em> “iOS app only; Android deferred.”</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Success criteria:</strong> Do you have unambiguous acceptance metrics? <em>Example:</em> target NPS, uptime, conversion rate.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Stakeholders and ownership</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li><strong>Accountability:</strong> Is there a single, named owner for decisions and outcomes?</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Engagement:</strong> Are all affected teams identified and included early (engineering, design, support, legal)?</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>RACI coverage:</strong> Are <em>Responsible</em>, <em>Accountable</em>, <em>Consulted</em>, and <em>Informed</em> roles captured and shared?</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">User needs and research</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li><strong>Personas and jobs-to-be-done:</strong> Do you know who the primary users are and the problem they’re solving?</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Evidence:</strong> Do you have data from interviews, surveys, or analytics to validate the need?</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Edge cases:</strong> Have accessibility, localization, and low-connectivity scenarios been considered?</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Requirements and acceptance criteria</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li><strong>Functional detail:</strong> Are requirements testable and unambiguous? <em>Example format:</em> “When X, system must Y within Z ms.”</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Non-functional:</strong> Capture performance, security, reliability, and compliance constraints.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Traceability:</strong> Can each requirement link back to a user need and a test case?</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Architecture and design</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li><strong>Diagram coverage:</strong> Do you have system, sequence, and data flow diagrams with clear boundaries and interfaces?</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Trade-offs:</strong> Are decisions and alternatives recorded with rationale? <em>Example:</em> ADRs in a repository.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Security model:</strong> Threats, trust boundaries, encryption, secrets management, and least-privilege verified.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Data and privacy</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li><strong>Data lifecycle:</strong> Collection, storage, access, retention, and deletion policies defined.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Compliance:</strong> Map data to regulations (GDPR, CCPA, HIPAA) and document lawful bases and consent flows.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Quality:</strong> Validation rules, schema versioning, and migration plans in place.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Security and compliance</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li><strong>Access control:</strong> Authentication, authorization, and audit logging verified.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Vulnerability management:</strong> Static/dynamic scanning, dependency checks, and patch cadence.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Incident readiness:</strong> Runbooks, on-call rotations, and reporting procedures tested.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Performance and reliability</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li><strong>SLOs/SLIs:</strong> Defined metrics for latency, availability, error rate, and throughput.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Capacity planning:</strong> Load testing, peak projections, and autoscaling policies in place.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Resiliency:</strong> Timeouts, retries with backoff, circuit breakers, and graceful degradation.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Observability and operations</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li><strong>Instrumentation:</strong> Logs, metrics, and traces standardized with correlation IDs.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Dashboards and alerts:</strong> Actionable, deduplicated alerts tied to runbooks.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Operational readiness:</strong> On-call coverage, playbooks, and post-incident review process.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Accessibility and inclusivity</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li><strong>Standards:</strong> WCAG conformance level targeted and audited.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Assistive tech:</strong> Keyboard navigation, screen reader labels, color contrast verified.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Inclusive language:</strong> Clear, respectful copy and support for international formats.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Documentation and knowledge transfer</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li><strong>Source of truth:</strong> Centralized, versioned documentation with change history.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Getting started:</strong> Quickstart, examples, and FAQs for new contributors or users.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Continuity:</strong> Handover notes, ownership map, and deprecation policies.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Testing strategy</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li><strong>Pyramid coverage:</strong> Unit, integration, end-to-end, and contract tests balanced.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Test data:</strong> Realistic, anonymized datasets and deterministic seeding.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Automation:</strong> CI execution with clear pass/fail gates and flaky test tracking.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Deployment and release management</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li><strong>Environments:</strong> Parity across dev, staging, and production with configuration as code.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Strategies:</strong> Blue/green, canary, or feature flags with rollback plans.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Change control:</strong> Release notes, approvals, and post-release monitoring.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Cost and scalability</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li><strong>Cost model:</strong> Estimated unit economics and budget thresholds.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Scaling plan:</strong> Horizontal/vertical strategies, sharding, and caching policies.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Efficiency:</strong> Resource utilization targets and autoscaling tests.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Legal and risk</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li><strong>Licensing:</strong> Third-party license compliance and attribution.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Contracts:</strong> SLAs, DPAs, and vendor risk assessments completed.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Business continuity:</strong> Backup, restore, and disaster recovery objectives (RPO/RTO).</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Support and feedback loops</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li><strong>Support readiness:</strong> Troubleshooting guides, escalation paths, and training for support teams.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Feedback intake:</strong> Channels for users and internal teams with triage SLAs.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Iteration cadence:</strong> Roadmap updates informed by data and customer feedback.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Example: quick triage pass</span></h3>
<!-- /wp:heading -->

<!-- wp:list {"ordered":true} -->
<ol class="wp-block-list"><!-- wp:list-item -->
<li><strong>State the goal:</strong> “Improve sign-up conversion by 15% in 60 days.”</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Spot the gaps:</strong> Missing acceptance criteria, no canary plan, no accessibility audit.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Mitigate fast:</strong> Add measurable criteria, define canary + rollback, run WCAG checks.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Confirm ownership:</strong> Assign decision owner, notify support and analytics teams.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Add observability:</strong> Define key events, dashboards, and alerts for conversion drops.</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Pro tip</span></h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Keep the checklist visible in planning meetings and retros. Start with the riskiest areas first (security, data, and deployment). If an item is unclear, create a small spike, document the findings, and move forward with evidence.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Application security</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li><span class="highlight">SAST</span>: Static analysis for code-level issues (e.g., injection, insecure deserialization)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><span class="highlight">SCA</span>: Software composition analysis for vulnerable dependencies and licenses</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><span class="highlight">DAST</span>: Dynamic analysis of running applications for runtime vulnerabilities</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Secret detection: hardcoded credentials, tokens, keys in code and CI logs</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Authentication and authorization: MFA, password policy, session management, RBAC/ABAC</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Input validation and output encoding: XSS, injection, SSRF protections</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Transport security: HTTPS, TLS version/cipher suites, HSTS, certificate hygiene</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Data protection: encryption at rest, key rotation, access patterns, data retention</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Infrastructure and cloud</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li><span class="highlight">CSPM</span> and configuration baselines (e.g., CIS Benchmarks)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><span class="highlight">IaC scanning</span> for Terraform, CloudFormation, Helm, Kubernetes manifests</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Network exposure: public endpoints, security groups, WAF rules, ingress/egress</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Identity and access: least privilege, stale accounts, key rotation, conditional access</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Container security: image scanning, signed images, minimal bases, runtime policies</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Logging/monitoring: centralization, immutability, alert coverage</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Operational security</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li><span class="highlight">Patch management</span> cadence and coverage</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Backup and recovery: encryption, frequency, restore testing</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Incident response: playbooks, on-call, tabletop exercises</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Third-party risk: vendor assessments, SBOMs, SLA/DPAs</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Secure SDLC: gates in CI/CD, code review standards, branch protections</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">Recommended tools and commands</span></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Use a combination of open-source and commercial tools. Adapt versions and flags to your environment.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Code and dependency scanning</span></h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code># SAST examples
semgrep --config p/owasp-top-ten
bandit -r src/

# SCA examples
npm audit --production
pip-audit
trivy fs .
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Secrets and IaC</span></h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code># Secrets scanning
gitleaks detect --source .
trufflehog filesystem .

# IaC scanning
tfsec .
checkov -d .
kube-score score k8s/
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Dynamic and perimeter testing</span></h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code># DAST and perimeter
owasp-zap -cmd -quickurl https://example.com -quickprogress
nmap -sV -Pn example.com
sslscan example.com
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">Verification and false-positive reduction</span></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Validate findings with a clear <span class="highlight">verification</span> procedure to reduce noise and focus on real risk.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Reproduce: follow exact steps or proof-of-concept to trigger the issue</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Corroborate: check logs, APM traces, WAF hits, or separate scanners</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Contextualize: consider exploitability, authentication requirements, blast radius</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Deduplicate: group identical issues across services; track via identifiers (CVE, CWE)</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">Risk rating and triage</span></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Apply a consistent <span class="highlight">risk rating</span> model to prioritize remediation.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Use CVSS v3.1 (Base + Temporal) where applicable</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Overlay business impact: data sensitivity, regulatory exposure, uptime criticality</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Consider threat likelihood: known exploits, internet exposure, required privileges</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Define SLAs: e.g., Critical 24–72h, High 7 days, Medium 30 days, Low 90 days</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Example risk matrix</span></h3>
<!-- /wp:heading -->

<!-- wp:table -->
<figure class="wp-block-table"><table class="has-fixed-layout"><thead><tr><th>Severity</th><th>Exploitability</th><th>Business Impact</th><th>Target SLA</th></tr></thead><tbody><tr><td>Critical</td><td>Active exploit / trivial</td><td>High (PII/PHI/regulatory)</td><td>24–72h</td></tr><tr><td>High</td><td>Reliable / authenticated</td><td>Moderate–High</td><td>7 days</td></tr><tr><td>Medium</td><td>Conditional / limited</td><td>Moderate</td><td>30 days</td></tr><tr><td>Low</td><td>Unlikely / theoretical</td><td>Low</td><td>90 days</td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:heading -->
<h2 class="wp-block-heading">Reporting a <span class="highlight">security issue</span></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Use a standard template so reports are consistent and actionable.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Report template</span></h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Title: &#91;Short, specific issue name]
Severity: &#91;Critical | High | Medium | Low]
Affected Assets: &#91;Service, URL, repo, image, account]
Description: &#91;Clear summary of the vulnerability]
Steps to Reproduce:
1. ...
2. ...
Expected vs Actual Behavior:
Evidence:
- Screenshots, logs, PoCs, scanner output
Impact:
- Data exposure, privilege escalation, integrity risk, availability
Remediation Recommendation:
References:
- CWE/CVE links, vendor advisories
Owner:
Due Date (per SLA):
Status:
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Disclosure and communication</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Internal: file a ticket, assign an owner, notify stakeholders and on-call</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>External: follow vulnerability disclosure policy and legal guidance</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Confidentiality: avoid sharing exploit details publicly before a fix is available</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">Remediation and validation</span></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Drive issues to closure with a documented <span class="highlight">remediation</span> process and post-fix validation.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Fix: apply code changes, patches, configuration updates, or compensating controls</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Review: peer review and security sign-off; ensure tests cover the regression</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Validate: rerun scanners and manual tests; confirm logs and metrics are clean</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Monitor: add alerts to detect recurrences or exploit attempts</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Document: root cause, lessons learned, and any policy/process updates</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">Automation in CI/CD</span></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Integrate checks into the <span class="highlight">CI/CD</span> pipeline to prevent regressions.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Pre-commit: secrets and linters</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Pull request: SAST and unit tests with security assertions</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Build: SCA and container image scanning</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Deploy: IaC and configuration checks, admission controls in Kubernetes</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Gates: fail builds on critical findings; create tickets automatically</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">Compliance alignment</span></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Map activities to your <span class="highlight">compliance</span> frameworks.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>ISO 27001: A.12 (Operations security), A.14 (System acquisition, development, and maintenance)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>SOC 2: CC7 (Change management), CC6 (Access controls)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>PCI DSS: Requirement 6 (Develop and maintain secure systems), 11 (Regular testing)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>HIPAA: Technical safeguards for ePHI; audit controls and integrity</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">Metrics and continuous improvement</span></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Track <span class="highlight">metrics</span> to measure progress and guide investments.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Mean time to remediate (MTTR) by severity</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Open vs closed vulnerabilities trend</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Coverage: percentage of assets scanned and frequency</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Reopen rate and false-positive rate</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Compliance pass rate against baselines</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">Safety and legal considerations</span></h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Obtain written authorization for testing and respect scope boundaries</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Avoid tests that can cause outages (e.g., aggressive fuzzing on production)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Protect sensitive data; use redaction and secure storage for evidence</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Coordinate with legal, privacy, and vendor management for third-party targets</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">References</span></h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li><a href="https://owasp.org/www-project-top-ten/">OWASP Top 10</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.first.org/cvss/">FIRST CVSS v3.1</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.cisecurity.org/cis-benchmarks">CIS Benchmarks</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.cisa.gov/known-exploited-vulnerabilities-catalog">CISA Known Exploited Vulnerabilities Catalog</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=oslc">OSLC for vulnerability management integrations</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">Appendix: Quick-start workflows</span></h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Developer quick check (pre-merge)</span></h3>
<!-- /wp:heading -->

<!-- wp:list {"ordered":true} -->
<ol class="wp-block-list"><!-- wp:list-item -->
<li>Run SAST and secrets scan locally</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Fix critical/high findings before opening PR</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Ensure unit tests cover security-critical code paths</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Release readiness (pre-production)</span></h3>
<!-- /wp:heading -->

<!-- wp:list {"ordered":true} -->
<ol class="wp-block-list"><!-- wp:list-item -->
<li>Complete SCA, container, and IaC scans</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Execute targeted DAST against staging</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Review open findings; defer only with temporary compensating controls and sign-off</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Quarterly posture review</span></h3>
<!-- /wp:heading -->

<!-- wp:list {"ordered":true} -->
<ol class="wp-block-list"><!-- wp:list-item -->
<li>Reconfirm asset inventory and criticality</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Run baseline cloud and network assessments</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Update playbooks, SLAs, and training based on lessons learned</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->
