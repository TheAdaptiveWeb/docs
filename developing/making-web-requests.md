---
description: Making web requests using the XHRService.
---

# Web Requests

## Basic requests

A `GET` request can be made by calling the `request` method with a URL as the first parameter.

```typescript
aw.request('https://example.adaptiveweb.io/')
    .then(response => {
        console.log(response);
    });
```

## Specifying request options

Options can be specified as the second parameter. Options can be passed as an Object, or \(if using TypeScript\) as an instance of `XHROptions`. Below is the full list of options allowed.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Option name</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Default</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">method</td>
      <td style="text-align:left"><code>string</code>
      </td>
      <td style="text-align:left"><code>GET</code>
      </td>
      <td style="text-align:left">
        <p>The HTTP method to use when sending the request</p>
        <p></p>
        <p>Allowed values are <code>GET</code>, <code>POST</code>, <code>DELETE</code>, <code>UPDATE</code>, <code>PATCH</code> or <code>PUT</code>, <code>HEAD</code>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">data</td>
      <td style="text-align:left"><code>Blob</code> , <code>string</code> or <code>{ [key: string]: any }</code>
      </td>
      <td style="text-align:left"><code>{}</code>
      </td>
      <td style="text-align:left">Data to be serialized into the querystring (for GET requests) or body
        for other methods</td>
    </tr>
    <tr>
      <td style="text-align:left">async</td>
      <td style="text-align:left"><code>boolean</code>
      </td>
      <td style="text-align:left"><code>true</code>
      </td>
      <td style="text-align:left">Whether the request should be sent asynchronously</td>
    </tr>
    <tr>
      <td style="text-align:left">user</td>
      <td style="text-align:left"><code>string</code>
      </td>
      <td style="text-align:left"><code>undefined</code>
      </td>
      <td style="text-align:left">The username for HTTP authorization</td>
    </tr>
    <tr>
      <td style="text-align:left">password</td>
      <td style="text-align:left"><code>string</code>
      </td>
      <td style="text-align:left"><code>undefined</code>
      </td>
      <td style="text-align:left">The password for HTTP authorization</td>
    </tr>
    <tr>
      <td style="text-align:left">withCredentials</td>
      <td style="text-align:left"><code>boolean</code>
      </td>
      <td style="text-align:left"><code>false</code>
      </td>
      <td style="text-align:left">Whether to send cookies to 3rd party domains</td>
    </tr>
    <tr>
      <td style="text-align:left">timeout</td>
      <td style="text-align:left"><code>number</code>
      </td>
      <td style="text-align:left"><code>0</code> (no timeout)</td>
      <td style="text-align:left">The amount of milliseconds a request can take before automatically being
        terminated</td>
    </tr>
    <tr>
      <td style="text-align:left">serialize</td>
      <td style="text-align:left"><code>Function</code>
      </td>
      <td style="text-align:left"><code>JSON.stringify</code>
      </td>
      <td style="text-align:left">The method used to serialize data</td>
    </tr>
    <tr>
      <td style="text-align:left">deserialize</td>
      <td style="text-align:left"><code>Function</code>
      </td>
      <td style="text-align:left"><code>JSON.parse</code>
      </td>
      <td style="text-align:left">The method used to deserialize data</td>
    </tr>
    <tr>
      <td style="text-align:left">headers</td>
      <td style="text-align:left"><code>{ [key: string] : string }</code>
      </td>
      <td style="text-align:left">See notes below</td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>The default headers are:

```javascript
{
    'Content-Type': 'application/json; charset=utf-8',
    'Accept': 'application/json, text/*'
}
```

For example, a post request can be made with the following method call:

```typescript
aw.request('https://example.adaptiveweb.io/', {
    method: 'POST',
    data: {
        myVar: 'value',
        myVar2: 123
    }
}).then(...);
```

