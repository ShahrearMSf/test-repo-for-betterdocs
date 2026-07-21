<h1>Glossary Removal from Settings: Impact, Migration, and Best Practices</h1>

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">Overview</span></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>This document explains the removal of the <span class="highlight">glossary</span> from the application’s settings, its impact on users and integrations, how existing data is handled, and the recommended steps to adapt. It is intended for administrators, developers, content managers, and support teams.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">What Changed</span></h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>The <span class="highlight">glossary setting</span>—previously used to manage centralized term definitions and inline tooltips—has been removed from the Settings area. Glossary-related configurations, UI entry points, and APIs tied to this setting are deprecated or rerouted as described below.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Why It Changed</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Reduce redundancy by consolidating definitions with content models and documentation sources</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Improve performance by removing runtime lookups tied to global settings</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Enable domain-specific glossaries at the project or space level rather than forcing a global scope</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Simplify permissions and auditing</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">Scope and Impact</span></h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Who Is Affected</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Administrators who previously managed terms in Settings</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Editors relying on auto-tooltips for defined terms</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Developers using glossary-related APIs or webhooks</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Analytics and localization teams referencing term metadata</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">User Experience Changes</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>The Settings menu no longer shows a Glossary section</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Inline tooltips previously powered by the global glossary may no longer appear unless migrated</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Term definition sidebars and quick-insert pickers that sourced global entries now reference project-level sources (if configured) or remain disabled</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">Data Handling and Backward Compatibility</span></h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Existing Data</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>All existing <span class="highlight">glossary terms</span> have been exported to a read-only archive</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Archived data includes: term, definition, canonical URL, tags, last-modified, and owner</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>No data is deleted automatically; exports are retained according to your organization’s data retention policy</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">API and Webhooks</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Deprecated endpoints return HTTP 410 Gone</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Transitional endpoints return HTTP 301 Moved Permanently to project-level glossary resources (when available)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Webhooks referencing the removed setting will not fire; subscribe to project glossary events instead</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Permissions</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Global glossary roles are removed</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Project-level roles govern creation, editing, and publishing of definitions</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Audit logs continue to record changes via project scopes</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">Migration Paths</span></h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Recommended Approaches</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li><strong>Project-level Glossaries:</strong> Create or enable a <span class="highlight">project glossary</span> in each workspace where terms are actively used</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>Content Model Fields:</strong> Store definitions as part of content types (e.g., Definition content type with references), enabling editorial control and versioning</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>External Source of Truth:</strong> Synchronize with a docs platform or terminology management system, then expose via API at render time</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Step-by-Step Migration</span></h3>
<!-- /wp:heading -->

<!-- wp:list {"ordered":true} -->
<ol class="wp-block-list"><!-- wp:list-item -->
<li>Download the archive of your previous glossary from the Admin console</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Choose a target model: project glossary, content model, or external source</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Import terms into the chosen target using the importer or API</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Map term identifiers (slugs) to avoid duplicates and maintain stable links</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Update rendering logic to resolve definitions from the new source</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Test in staging to validate tooltips, links, search, and permissions</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Deploy and communicate the change to editors and stakeholders</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">Developer Guide</span></h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Resolving Definitions at Runtime</span></h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>If your UI previously queried the global setting, switch to a <span class="highlight">project-level API</span> or your content model. Example pseudo-requests:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code># Get terms for a project
GET /api/projects/{projectId}/glossary?limit=100&amp;locale=en

# Resolve a single term by slug
GET /api/projects/{projectId}/glossary/{slug}
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Fallback Strategy</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Attempt project glossary lookup by slug</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Fallback to localized content-model definition</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Render without tooltip if neither source is present</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Client-Side Tooltip Rendering</span></h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>// Pseudocode
function resolveDefinition(term, locale) {
  return fetch(`/api/projects/${projectId}/glossary/${slug}?locale=${locale}`)
    .then(r =&gt; r.ok ? r.json() : null)
    .catch(() =&gt; null);
}

function enhanceTextWithTooltips(node, termsIndex) {
  // Replace matched terms with &lt;abbr title="Definition"&gt;Term&lt;/abbr&gt;
}
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Error Handling</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Handle 410 for removed global endpoints by routing to project resources</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Gracefully degrade UI when a definition is missing</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Log unresolved slugs for monitoring and editorial follow-up</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">Content and Editorial Workflows</span></h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Establish Ownership</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Assign a <span class="highlight">term owner</span> per project to oversee accuracy and currency</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Define SLAs for updating definitions triggered by product releases</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Naming and Tagging Conventions</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Use stable, lowercase slugs with hyphens (e.g., <code>single-sign-on</code>)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Tag terms by domain (security, billing, UI) and audience (end-user, admin, developer)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Avoid product names in definitions—link to canonical docs instead</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Localization</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Localize definitions as independent entries with translation memory</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Maintain a <span class="highlight">canonical definition</span> in source locale and track equivalence notes</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Include usage examples and non-translatable aliases where relevant</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">Testing and Validation</span></h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Pre-Deployment Checklist</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Archived data verified and accessible</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Migrations completed for all active projects</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Rendering updated in core surfaces (docs, app UI, help panels)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Search index re-built to include new definition sources</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Access controls validated for editors and viewers</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Post-Deployment Monitoring</span></h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Track 404/410/5xx on glossary routes</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Measure tooltip render rates and user engagement</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Survey editors for gaps and friction points</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">Security and Compliance</span></h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>PII and confidential terms should be scoped to restricted projects and redacted from public indexes</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Audit logs preserve add/edit/delete events per project</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Exports remain encrypted at rest and in transit</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">Frequently Asked Questions</span></h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Can I restore the global glossary?</span></h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>No. The <span class="highlight">global glossary</span> has been permanently removed. Use project-level glossaries or content models.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Will existing links to glossary terms break?</span></h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Incoming links to legacy glossary URLs return HTTP 301 to equivalent project routes when mappings exist; otherwise, they return 410.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">Do I need to retranslate all terms?</span></h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>No. You can import translations from the archive and map locales to your project model.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading"><span class="highlight">How do I access the archive?</span></h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Admins can download it from the Admin console under Data Archives or via the Export API.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><span class="highlight">Support and Resources</span></h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Migrating to project glossaries: <a href="https://example.com/docs/project-glossary-migration">https://example.com/docs/project-glossary-migration</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>API reference: <a href="https://example.com/docs/api">https://example.com/docs/api</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Contact support: <a href="https://example.com/support">https://example.com/support</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->
