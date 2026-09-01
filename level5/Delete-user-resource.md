<h1>Delete user resource.</h1>

<!-- wp:betterdocs/api-tryit {"method":"delete","path":"/user/{username}","refId":7886} /--><!-- wp:paragraph -->
<p>This can only be done by the logged in user.</p>
<!-- /wp:paragraph --><!-- wp:heading -->
<h2 class="wp-block-heading">Path Parameters</h2>
<!-- /wp:heading --><!-- wp:table {"className":"betterdocs-api-table"} -->
<figure class="wp-block-table betterdocs-api-table"><table><thead><tr><th>Name</th><th>Type</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>username</code></td><td>string</td><td><strong>Required</strong></td><td>The name that needs to be deleted</td></tr></tbody></table></figure>
<!-- /wp:table --><!-- wp:heading -->
<h2 class="wp-block-heading">Responses</h2>
<!-- /wp:heading --><!-- wp:heading {"level":3,"className":"betterdocs-api-response betterdocs-api-response\u002d\u002d2xx"} -->
<h3 class="wp-block-heading betterdocs-api-response betterdocs-api-response--2xx">200 — User deleted</h3>
<!-- /wp:heading --><!-- wp:heading {"level":3,"className":"betterdocs-api-response betterdocs-api-response\u002d\u002d4xx"} -->
<h3 class="wp-block-heading betterdocs-api-response betterdocs-api-response--4xx">400 — Invalid username supplied</h3>
<!-- /wp:heading --><!-- wp:heading {"level":3,"className":"betterdocs-api-response betterdocs-api-response\u002d\u002d4xx"} -->
<h3 class="wp-block-heading betterdocs-api-response betterdocs-api-response--4xx">404 — User not found</h3>
<!-- /wp:heading --><!-- wp:heading {"level":3,"className":"betterdocs-api-response betterdocs-api-response\u002d\u002ddxx"} -->
<h3 class="wp-block-heading betterdocs-api-response betterdocs-api-response--dxx">default — Unexpected error</h3>
<!-- /wp:heading --><!-- wp:heading -->
<h2 class="wp-block-heading">Code Samples</h2>
<!-- /wp:heading --><!-- wp:betterdocs/code-snippet {"codeContent":"curl \u002d\u002drequest DELETE \u005c\n  \u002d\u002durl '/api/v3/user/{username}'","language":"curl","showLanguageLabel":true,"showCopyButton":true,"showLineNumbers":false,"theme":"light","fileName":"cURL","codeVariants":[{"language":"javascript","codeContent":"const response = await fetch('/api/v3/user/{username}', {\n  method: 'DELETE'\n});\n\nconst data = await response.json();\nconsole.log(data);"},{"language":"python","codeContent":"import requests\n\nresponse = requests.delete(\u0022/api/v3/user/{username}\u0022)\n\nprint(response.json())"},{"language":"php","codeContent":"\u003c?php\n$curl = curl_init();\n\ncurl_setopt_array($curl, [\n  CURLOPT_URL =\u003e '/api/v3/user/{username}',\n  CURLOPT_RETURNTRANSFER =\u003e true,\n  CURLOPT_CUSTOMREQUEST =\u003e 'DELETE',\n]);\n\n$response = curl_exec($curl);\ncurl_close($curl);\n\necho $response;"},{"language":"csharp","codeContent":"using System.Net.Http;\n\nvar client = new HttpClient();\nvar request = new HttpRequestMessage(new HttpMethod(\u0022DELETE\u0022), \u0022/api/v3/user/{username}\u0022);\nvar response = await client.SendAsync(request);\nvar body = await response.Content.ReadAsStringAsync();\nConsole.WriteLine(body);"},{"language":"java","codeContent":"import java.net.URI;\nimport java.net.http.*;\n\nHttpClient client = HttpClient.newHttpClient();\nHttpRequest request = HttpRequest.newBuilder()\n    .uri(URI.create(\u0022/api/v3/user/{username}\u0022))\n    .method(\u0022DELETE\u0022, HttpRequest.BodyPublishers.noBody())\n    .build();\n\nHttpResponse\u003cString\u003e response = client.send(request, HttpResponse.BodyHandlers.ofString());\nSystem.out.println(response.body());"}]} /-->
