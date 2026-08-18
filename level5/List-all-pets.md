<h1>List all pets</h1>

<!-- wp:betterdocs/api-tryit {"method":"get","path":"/pets","refId":7733} /--><!-- wp:heading -->
<h2 class="wp-block-heading">Query Parameters</h2>
<!-- /wp:heading --><!-- wp:table {"className":"betterdocs-api-table"} -->
<figure class="wp-block-table betterdocs-api-table"><table><thead><tr><th>Name</th><th>Type</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>limit</code></td><td>integer (int32)</td><td>Optional</td><td>Max items to return (max 100)</td></tr></tbody></table></figure>
<!-- /wp:table --><!-- wp:heading -->
<h2 class="wp-block-heading">Responses</h2>
<!-- /wp:heading --><!-- wp:heading {"level":3,"className":"betterdocs-api-response betterdocs-api-response\u002d\u002d2xx"} -->
<h3 class="wp-block-heading betterdocs-api-response betterdocs-api-response--2xx">200 — A paged array of pets</h3>
<!-- /wp:heading --><!-- wp:table {"className":"betterdocs-api-table"} -->
<figure class="wp-block-table betterdocs-api-table"><table><thead><tr><th>Field</th><th>Type</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>[].name</code></td><td>string</td><td><strong>Required</strong></td><td></td></tr><tr><td><code>[].tag</code></td><td>string</td><td>Optional</td><td></td></tr><tr><td><code>[].id</code></td><td>integer (int64)</td><td><strong>Required</strong></td><td></td></tr></tbody></table></figure>
<!-- /wp:table --><!-- wp:betterdocs/code-snippet {"codeContent":"[\n    {\n        \u0022name\u0022: \u0022Mochi\u0022,\n        \u0022tag\u0022: \u0022cat\u0022,\n        \u0022id\u0022: 1\n    }\n]","language":"json","showLanguageLabel":true,"showCopyButton":true,"showLineNumbers":false,"theme":"light","fileName":"Example 200 response"} /--><!-- wp:heading -->
<h2 class="wp-block-heading">Code Samples</h2>
<!-- /wp:heading --><!-- wp:betterdocs/code-snippet {"codeContent":"curl \u002d\u002drequest GET \u005c\n  \u002d\u002durl 'https://petstore.example.com/v1/pets'","language":"curl","showLanguageLabel":true,"showCopyButton":true,"showLineNumbers":false,"theme":"light","fileName":"cURL","codeVariants":[{"language":"javascript","codeContent":"const response = await fetch('https://petstore.example.com/v1/pets', {\n  method: 'GET'\n});\n\nconst data = await response.json();\nconsole.log(data);"},{"language":"python","codeContent":"import requests\n\nresponse = requests.get(\u0022https://petstore.example.com/v1/pets\u0022)\n\nprint(response.json())"},{"language":"php","codeContent":"\u003c?php\n$curl = curl_init();\n\ncurl_setopt_array($curl, [\n  CURLOPT_URL =\u003e 'https://petstore.example.com/v1/pets',\n  CURLOPT_RETURNTRANSFER =\u003e true,\n  CURLOPT_CUSTOMREQUEST =\u003e 'GET',\n]);\n\n$response = curl_exec($curl);\ncurl_close($curl);\n\necho $response;"},{"language":"csharp","codeContent":"using System.Net.Http;\n\nvar client = new HttpClient();\nvar request = new HttpRequestMessage(new HttpMethod(\u0022GET\u0022), \u0022https://petstore.example.com/v1/pets\u0022);\nvar response = await client.SendAsync(request);\nvar body = await response.Content.ReadAsStringAsync();\nConsole.WriteLine(body);"},{"language":"java","codeContent":"import java.net.URI;\nimport java.net.http.*;\n\nHttpClient client = HttpClient.newHttpClient();\nHttpRequest request = HttpRequest.newBuilder()\n    .uri(URI.create(\u0022https://petstore.example.com/v1/pets\u0022))\n    .method(\u0022GET\u0022, HttpRequest.BodyPublishers.noBody())\n    .build();\n\nHttpResponse\u003cString\u003e response = client.send(request, HttpResponse.BodyHandlers.ofString());\nSystem.out.println(response.body());"}]} /--><!-- wp:heading -->
<h2 class="wp-block-heading">Response</h2>
<!-- /wp:heading --><!-- wp:code -->
<pre class="wp-block-code"><code>200
[
    {
        &quot;name&quot;: &quot;Mochi&quot;,
        &quot;tag&quot;: &quot;cat&quot;,
        &quot;id&quot;: 1
    }
]</code></pre>
<!-- /wp:code -->
