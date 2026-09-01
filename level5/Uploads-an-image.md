<h1>Uploads an image.</h1>

<!-- wp:betterdocs/api-tryit {"method":"post","path":"/pet/{petId}/uploadImage","refId":7886} /--><!-- wp:paragraph -->
<p>Upload image of the pet.</p>
<!-- /wp:paragraph --><!-- wp:heading -->
<h2 class="wp-block-heading">Path Parameters</h2>
<!-- /wp:heading --><!-- wp:table {"className":"betterdocs-api-table"} -->
<figure class="wp-block-table betterdocs-api-table"><table><thead><tr><th>Name</th><th>Type</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>petId</code></td><td>integer (int64)</td><td><strong>Required</strong></td><td>ID of pet to update</td></tr></tbody></table></figure>
<!-- /wp:table --><!-- wp:heading -->
<h2 class="wp-block-heading">Query Parameters</h2>
<!-- /wp:heading --><!-- wp:table {"className":"betterdocs-api-table"} -->
<figure class="wp-block-table betterdocs-api-table"><table><thead><tr><th>Name</th><th>Type</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>additionalMetadata</code></td><td>string</td><td>Optional</td><td>Additional Metadata</td></tr></tbody></table></figure>
<!-- /wp:table --><!-- wp:heading -->
<h2 class="wp-block-heading">Request Body</h2>
<!-- /wp:heading --><!-- wp:paragraph -->
<p>Content type: <code>application/octet-stream</code></p>
<!-- /wp:paragraph --><!-- wp:heading -->
<h2 class="wp-block-heading">Responses</h2>
<!-- /wp:heading --><!-- wp:heading {"level":3,"className":"betterdocs-api-response betterdocs-api-response\u002d\u002d2xx"} -->
<h3 class="wp-block-heading betterdocs-api-response betterdocs-api-response--2xx">200 — successful operation</h3>
<!-- /wp:heading --><!-- wp:table {"className":"betterdocs-api-table"} -->
<figure class="wp-block-table betterdocs-api-table"><table><thead><tr><th>Field</th><th>Type</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>code</code></td><td>integer (int32)</td><td>Optional</td><td></td></tr><tr><td><code>type</code></td><td>string</td><td>Optional</td><td></td></tr><tr><td><code>message</code></td><td>string</td><td>Optional</td><td></td></tr></tbody></table></figure>
<!-- /wp:table --><!-- wp:betterdocs/code-snippet {"codeContent":"{\n    \u0022code\u0022: 1,\n    \u0022type\u0022: \u0022string\u0022,\n    \u0022message\u0022: \u0022string\u0022\n}","language":"json","showLanguageLabel":true,"showCopyButton":true,"showLineNumbers":false,"theme":"light","fileName":"Example 200 response"} /--><!-- wp:heading {"level":3,"className":"betterdocs-api-response betterdocs-api-response\u002d\u002d4xx"} -->
<h3 class="wp-block-heading betterdocs-api-response betterdocs-api-response--4xx">400 — No file uploaded</h3>
<!-- /wp:heading --><!-- wp:heading {"level":3,"className":"betterdocs-api-response betterdocs-api-response\u002d\u002d4xx"} -->
<h3 class="wp-block-heading betterdocs-api-response betterdocs-api-response--4xx">404 — Pet not found</h3>
<!-- /wp:heading --><!-- wp:heading {"level":3,"className":"betterdocs-api-response betterdocs-api-response\u002d\u002ddxx"} -->
<h3 class="wp-block-heading betterdocs-api-response betterdocs-api-response--dxx">default — Unexpected error</h3>
<!-- /wp:heading --><!-- wp:heading -->
<h2 class="wp-block-heading">Code Samples</h2>
<!-- /wp:heading --><!-- wp:betterdocs/code-snippet {"codeContent":"curl \u002d\u002drequest POST \u005c\n  \u002d\u002durl '/api/v3/pet/{petId}/uploadImage' \u005c\n  \u002d\u002dheader 'Authorization: Bearer YOUR_TOKEN'","language":"curl","showLanguageLabel":true,"showCopyButton":true,"showLineNumbers":false,"theme":"light","fileName":"cURL","codeVariants":[{"language":"javascript","codeContent":"const response = await fetch('/api/v3/pet/{petId}/uploadImage', {\n  method: 'POST',\n  headers: {\n    'Authorization': 'Bearer YOUR_TOKEN'\n  }\n});\n\nconst data = await response.json();\nconsole.log(data);"},{"language":"python","codeContent":"import requests\n\nheaders = {\n    \u0022Authorization\u0022: \u0022Bearer YOUR_TOKEN\u0022\n}\n\nresponse = requests.post(\u0022/api/v3/pet/{petId}/uploadImage\u0022, headers=headers)\n\nprint(response.json())"},{"language":"php","codeContent":"\u003c?php\n$curl = curl_init();\n\ncurl_setopt_array($curl, [\n  CURLOPT_URL =\u003e '/api/v3/pet/{petId}/uploadImage',\n  CURLOPT_RETURNTRANSFER =\u003e true,\n  CURLOPT_CUSTOMREQUEST =\u003e 'POST',\n  CURLOPT_HTTPHEADER =\u003e [\n  'Authorization: Bearer YOUR_TOKEN'\n  ],\n]);\n\n$response = curl_exec($curl);\ncurl_close($curl);\n\necho $response;"},{"language":"csharp","codeContent":"using System.Net.Http;\n\nvar client = new HttpClient();\nvar request = new HttpRequestMessage(new HttpMethod(\u0022POST\u0022), \u0022/api/v3/pet/{petId}/uploadImage\u0022);\nrequest.Headers.Add(\u0022Authorization\u0022, \u0022Bearer YOUR_TOKEN\u0022);\nvar response = await client.SendAsync(request);\nvar body = await response.Content.ReadAsStringAsync();\nConsole.WriteLine(body);"},{"language":"java","codeContent":"import java.net.URI;\nimport java.net.http.*;\n\nHttpClient client = HttpClient.newHttpClient();\nHttpRequest request = HttpRequest.newBuilder()\n    .uri(URI.create(\u0022/api/v3/pet/{petId}/uploadImage\u0022))\n    .header(\u0022Authorization\u0022, \u0022Bearer YOUR_TOKEN\u0022)\n    .method(\u0022POST\u0022, HttpRequest.BodyPublishers.noBody())\n    .build();\n\nHttpResponse\u003cString\u003e response = client.send(request, HttpResponse.BodyHandlers.ofString());\nSystem.out.println(response.body());"}]} /--><!-- wp:heading -->
<h2 class="wp-block-heading">Response</h2>
<!-- /wp:heading --><!-- wp:betterdocs/code-snippet-tab {"responses":[{"status":"200","language":"json","codeContent":"{\n    \u0022code\u0022: 1,\n    \u0022type\u0022: \u0022string\u0022,\n    \u0022message\u0022: \u0022string\u0022\n}"}],"showCopyButton":true,"showLineNumbers":false,"theme":"light"} /-->
