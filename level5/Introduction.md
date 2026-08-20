<h1>Introduction</h1>

<!-- wp:heading -->
<h2 class="wp-block-heading">xCloud Public API</h2>
<!-- /wp:heading --><!-- wp:paragraph -->
<p>A self-service REST API for all xCloud customers. Use this API to programmatically
manage your servers, sites, databases, backups, cron jobs, and more — directly from
your own scripts, CI/CD pipelines, or integrations.</p>
<!-- /wp:paragraph --><!-- wp:heading -->
<h2 class="wp-block-heading">Authentication</h2>
<!-- /wp:heading --><!-- wp:paragraph -->
<p>All API requests (except <code>GET /health</code>) require a <strong>Sanctum Personal Access Token</strong>
passed as a Bearer token in the <code>Authorization</code> header.</p>
<!-- /wp:paragraph --><!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">Creating a Token</h3>
<!-- /wp:heading --><!-- wp:list {"ordered":true} -->
<ol>
<li>Log in to <a href="https://app.xcloud.host">app.xcloud.host</a></li>
<li>Navigate to <strong>Account → API Tokens</strong> (<code>/user/api-tokens</code>)</li>
<li>Click <strong>Create New Token</strong></li>
<li>Select the required scopes for your use case</li>
<li>Copy the token — <strong>it is shown only once</strong></li>
</ol>
<!-- /wp:list --><!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">Available Scopes</h3>
<!-- /wp:heading --><!-- wp:html -->
<table>
<thead>
<tr>
<th>Scope</th>
<th>Access</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>read:servers</code></td>
<td>List and view servers, databases, cron jobs, PHP versions, monitoring, sudo users</td>
</tr>
<tr>
<td><code>write:servers</code></td>
<td>Reboot servers, create WordPress sites, manage sudo users</td>
</tr>
<tr>
<td><code>read:sites</code></td>
<td>List and view sites, backups, SSL, domain, git, deployment logs, SSH config</td>
</tr>
<tr>
<td><code>write:sites</code></td>
<td>Trigger backups, rescue sites, purge cache, update SSH/SFTP config</td>
</tr>
<tr>
<td><code>*</code></td>
<td>Full access to all endpoints</td>
</tr>
</tbody>
</table>
<!-- /wp:html --><!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">Required Headers</h3>
<!-- /wp:heading --><!-- wp:html -->
<pre><code class="language-http">Authorization: Bearer &lt;your-token&gt;
Accept: application/json
Content-Type: application/json</code></pre>
<!-- /wp:html --><!-- wp:heading -->
<h2 class="wp-block-heading">Response Format</h2>
<!-- /wp:heading --><!-- wp:paragraph -->
<p>All responses follow a consistent envelope:</p>
<!-- /wp:paragraph --><!-- wp:html -->
<pre><code class="language-json">{
  "success": true,
  "message": "Operation completed successfully.",
  "data": { ... }
}</code></pre>
<!-- /wp:html --><!-- wp:paragraph -->
<p>For paginated lists, <code>data</code> contains:</p>
<!-- /wp:paragraph --><!-- wp:html -->
<pre><code class="language-json">{
  "data": [ ... ],
  "meta": {
    "current_page": 1,
    "last_page": 5,
    "per_page": 15,
    "total": 72
  }
}</code></pre>
<!-- /wp:html --><!-- wp:heading -->
<h2 class="wp-block-heading">HTTP Status Codes</h2>
<!-- /wp:heading --><!-- wp:html -->
<table>
<thead>
<tr>
<th>Code</th>
<th>Meaning</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>200 OK</code></td>
<td>Request successful</td>
</tr>
<tr>
<td><code>202 Accepted</code></td>
<td>Async operation queued (e.g. reboot, backup)</td>
</tr>
<tr>
<td><code>400 Bad Request</code></td>
<td>Validation error — check <code>errors</code> in response body</td>
</tr>
<tr>
<td><code>401 Unauthorized</code></td>
<td>Missing or invalid token</td>
</tr>
<tr>
<td><code>403 Forbidden</code></td>
<td>Token lacks the required scope</td>
</tr>
<tr>
<td><code>404 Not Found</code></td>
<td>Resource not found or not accessible to your team</td>
</tr>
<tr>
<td><code>422 Unprocessable Entity</code></td>
<td>Business logic validation failure</td>
</tr>
<tr>
<td><code>429 Too Many Requests</code></td>
<td>Rate limit exceeded</td>
</tr>
<tr>
<td><code>500 Internal Server Error</code></td>
<td>Server error — contact support</td>
</tr>
</tbody>
</table>
<!-- /wp:html --><!-- wp:heading -->
<h2 class="wp-block-heading">Rate Limits</h2>
<!-- /wp:heading --><!-- wp:html -->
<table>
<thead>
<tr>
<th>Type</th>
<th>Limit</th>
</tr>
</thead>
<tbody>
<tr>
<td>Authenticated requests</td>
<td><strong>60 requests / minute</strong></td>
</tr>
<tr>
<td>Unauthenticated requests</td>
<td><strong>10 requests / minute</strong></td>
</tr>
</tbody>
</table>
<!-- /wp:html --><!-- wp:paragraph -->
<p>Rate limit headers are included in every response:</p>
<!-- /wp:paragraph --><!-- wp:html -->
<pre><code class="language-http">X-RateLimit-Limit: 60
X-RateLimit-Remaining: 58
X-RateLimit-Reset: 1710000060</code></pre>
<!-- /wp:html --><!-- wp:paragraph -->
<p>When you exceed the limit, the API returns <code>429 Too Many Requests</code> with a
<code>Retry-After</code> header indicating how many seconds to wait.</p>
<!-- /wp:paragraph --><!-- wp:heading -->
<h2 class="wp-block-heading">Base URLs</h2>
<!-- /wp:heading --><!-- wp:table {"className":"betterdocs-api-table"} -->
<figure class="wp-block-table betterdocs-api-table"><table><thead><tr><th>URL</th><th>Description</th></tr></thead><tbody><tr><td><code>https://app.xcloud.host/api/v1</code></td><td>Production</td></tr></tbody></table></figure>
<!-- /wp:table --><!-- wp:heading -->
<h2 class="wp-block-heading">Authentication</h2>
<!-- /wp:heading --><!-- wp:table {"className":"betterdocs-api-table"} -->
<figure class="wp-block-table betterdocs-api-table"><table><thead><tr><th>Scheme</th><th>Type</th><th>Details</th></tr></thead><tbody><tr><td><code>bearerAuth</code></td><td>http</td><td>HTTP bearer authentication</td></tr></tbody></table></figure>
<!-- /wp:table --><!-- wp:heading -->
<h2 class="wp-block-heading">API Details</h2>
<!-- /wp:heading --><!-- wp:table {"className":"betterdocs-api-table"} -->
<figure class="wp-block-table betterdocs-api-table"><table><tbody><tr><td>Version</td><td>1.0.0</td></tr><tr><td>Contact</td><td>xCloud Support — <a href="https://xcloud.host/support">https://xcloud.host/support</a></td></tr><tr><td>License</td><td>Proprietary</td></tr></tbody></table></figure>
<!-- /wp:table -->
