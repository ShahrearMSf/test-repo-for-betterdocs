<h1>Create a pet</h1>

<!-- wp:betterdocs/api-tryit {"method":"post","path":"/pets","refId":7733} /--><!-- wp:heading -->
<h2 class="wp-block-heading">Request Body</h2>
<!-- /wp:heading --><!-- wp:paragraph -->
<p>Content type: <code>application/json</code> — <strong>required</strong></p>
<!-- /wp:paragraph --><!-- wp:table {"className":"betterdocs-api-table"} -->
<figure class="wp-block-table betterdocs-api-table"><table><thead><tr><th>Field</th><th>Type</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>name</code></td><td>string</td><td><strong>Required</strong></td><td></td></tr><tr><td><code>tag</code></td><td>string</td><td>Optional</td><td></td></tr></tbody></table></figure>
<!-- /wp:table --><!-- wp:betterdocs/code-snippet {"codeContent":"{\n    \u0022name\u0022: \u0022Mochi\u0022,\n    \u0022tag\u0022: \u0022cat\u0022\n}","language":"json","showLanguageLabel":true,"showCopyButton":true,"showLineNumbers":false,"theme":"light","fileName":"Example request"} /--><!-- wp:heading -->
<h2 class="wp-block-heading">Responses</h2>
<!-- /wp:heading --><!-- wp:heading {"level":3,"className":"betterdocs-api-response betterdocs-api-response\u002d\u002d2xx"} -->
<h3 class="wp-block-heading betterdocs-api-response betterdocs-api-response--2xx">201 — Pet created</h3>
<!-- /wp:heading --><!-- wp:table {"className":"betterdocs-api-table"} -->
<figure class="wp-block-table betterdocs-api-table"><table><thead><tr><th>Field</th><th>Type</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>name</code></td><td>string</td><td><strong>Required</strong></td><td></td></tr><tr><td><code>tag</code></td><td>string</td><td>Optional</td><td></td></tr><tr><td><code>id</code></td><td>integer (int64)</td><td><strong>Required</strong></td><td></td></tr></tbody></table></figure>
<!-- /wp:table --><!-- wp:betterdocs/code-snippet {"codeContent":"{\n    \u0022name\u0022: \u0022Mochi\u0022,\n    \u0022tag\u0022: \u0022cat\u0022,\n    \u0022id\u0022: 1\n}","language":"json","showLanguageLabel":true,"showCopyButton":true,"showLineNumbers":false,"theme":"light","fileName":"Example 201 response"} /--><!-- wp:heading {"level":3,"className":"betterdocs-api-response betterdocs-api-response\u002d\u002d4xx"} -->
<h3 class="wp-block-heading betterdocs-api-response betterdocs-api-response--4xx">422 — Validation failed</h3>
<!-- /wp:heading --><!-- wp:table {"className":"betterdocs-api-table"} -->
<figure class="wp-block-table betterdocs-api-table"><table><thead><tr><th>Field</th><th>Type</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>code</code></td><td>integer</td><td><strong>Required</strong></td><td></td></tr><tr><td><code>message</code></td><td>string</td><td><strong>Required</strong></td><td></td></tr><tr><td><code>fields</code></td><td>array of string</td><td>Optional</td><td></td></tr></tbody></table></figure>
<!-- /wp:table --><!-- wp:betterdocs/code-snippet {"codeContent":"{\n    \u0022code\u0022: 1,\n    \u0022message\u0022: \u0022string\u0022,\n    \u0022fields\u0022: [\n        \u0022string\u0022\n    ]\n}","language":"json","showLanguageLabel":true,"showCopyButton":true,"showLineNumbers":false,"theme":"light","fileName":"Example 422 response"} /--><!-- wp:heading -->
<h2 class="wp-block-heading">Code Samples</h2>
<!-- /wp:heading --><!-- wp:betterdocs/code-snippet {"codeContent":"curl \u002d\u002drequest POST \u005c\n  \u002d\u002durl 'https://petstore.example.com/v1/pets' \u005c\n  \u002d\u002dheader 'Content-Type: application/json' \u005c\n  \u002d\u002ddata '{\n    \u0022name\u0022: \u0022Mochi\u0022,\n    \u0022tag\u0022: \u0022cat\u0022\n}'","language":"curl","showLanguageLabel":true,"showCopyButton":true,"showLineNumbers":false,"theme":"light","fileName":"cURL","codeVariants":[{"language":"javascript","codeContent":"const response = await fetch('https://petstore.example.com/v1/pets', {\n  method: 'POST',\n  headers: {\n    'Content-Type': 'application/json'\n  },\n  body: JSON.stringify({\n    \u0022name\u0022: \u0022Mochi\u0022,\n    \u0022tag\u0022: \u0022cat\u0022\n})\n});\n\nconst data = await response.json();\nconsole.log(data);"},{"language":"python","codeContent":"import requests\n\nheaders = {\n    \u0022Content-Type\u0022: \u0022application/json\u0022\n}\n\npayload = {\n    \u0022name\u0022: \u0022Mochi\u0022,\n    \u0022tag\u0022: \u0022cat\u0022\n}\n\nresponse = requests.post(\u0022https://petstore.example.com/v1/pets\u0022, headers=headers, json=payload)\n\nprint(response.json())"},{"language":"php","codeContent":"\u003c?php\n$curl = curl_init();\n\ncurl_setopt_array($curl, [\n  CURLOPT_URL =\u003e 'https://petstore.example.com/v1/pets',\n  CURLOPT_RETURNTRANSFER =\u003e true,\n  CURLOPT_CUSTOMREQUEST =\u003e 'POST',\n  CURLOPT_HTTPHEADER =\u003e [\n  'Content-Type: application/json'\n  ],\n  CURLOPT_POSTFIELDS =\u003e '{\n    \u0022name\u0022: \u0022Mochi\u0022,\n    \u0022tag\u0022: \u0022cat\u0022\n}',\n]);\n\n$response = curl_exec($curl);\ncurl_close($curl);\n\necho $response;"},{"language":"csharp","codeContent":"using System.Net.Http;\nusing System.Text;\n\nvar client = new HttpClient();\nvar request = new HttpRequestMessage(new HttpMethod(\u0022POST\u0022), \u0022https://petstore.example.com/v1/pets\u0022);\nrequest.Content = new StringContent(@\u0022{\n    \u0022\u0022name\u0022\u0022: \u0022\u0022Mochi\u0022\u0022,\n    \u0022\u0022tag\u0022\u0022: \u0022\u0022cat\u0022\u0022\n}\u0022, Encoding.UTF8, \u0022application/json\u0022);\nvar response = await client.SendAsync(request);\nvar body = await response.Content.ReadAsStringAsync();\nConsole.WriteLine(body);"},{"language":"java","codeContent":"import java.net.URI;\nimport java.net.http.*;\n\nHttpClient client = HttpClient.newHttpClient();\nHttpRequest request = HttpRequest.newBuilder()\n    .uri(URI.create(\u0022https://petstore.example.com/v1/pets\u0022))\n    .header(\u0022Content-Type\u0022, \u0022application/json\u0022)\n    .method(\u0022POST\u0022, HttpRequest.BodyPublishers.ofString(\u0022\u0022\u0022\n{\n    \u0022name\u0022: \u0022Mochi\u0022,\n    \u0022tag\u0022: \u0022cat\u0022\n}\n\u0022\u0022\u0022))\n    .build();\n\nHttpResponse\u003cString\u003e response = client.send(request, HttpResponse.BodyHandlers.ofString());\nSystem.out.println(response.body());"}]} /--><!-- wp:heading -->
<h2 class="wp-block-heading">Response</h2>
<!-- /wp:heading --><!-- wp:code -->
<pre class="wp-block-code"><code>201
{
    &quot;name&quot;: &quot;Mochi&quot;,
    &quot;tag&quot;: &quot;cat&quot;,
    &quot;id&quot;: 1
}</code></pre>

<pre class="wp-block-code"><code>422
{
    &quot;code&quot;: 1,
    &quot;message&quot;: &quot;string&quot;,
    &quot;fields&quot;: [
        &quot;string&quot;
    ]
}</code></pre>
<!-- /wp:code -->
