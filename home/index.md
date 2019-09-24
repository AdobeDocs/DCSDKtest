# Heading 1

## Heading 2

.. note:: The `DC Services SDK <./servicessdk/index.html>`__ and `DC View SDK <./viewsdk/index.html>`__ are now available for early access. This version of the SDK provides JAVA APIs, documentation, and sample code.  

## Heading 2

Despite its near ubiquity, supporting PDF viewing on the web or in applications often remains a multi-step process where the developer relies on disparate browser implementations and simply doesn't own the end-to-end customer experience. This means that organizations have little control over their PDF workflows and PDF integration often requires additional downloads or sending users to 3rd party applications. 

### Heading 3

What? 


### Heading 3

What? 


### Heading 4

In line code: After installing the Nuget package, navigate to the `.nuget` directory, find and open `adobe.documentcloud.services.0.5.0.nupkg.sha512`.


### Heading 4

blockquote 

> Timeout properties are inferred and provide defaults. Manually add the properties to your configuration file if you prefer to use custom values. Communication times with Adobe servers are configurable as follows: 

### Heading 3

JSON snippet

```
  {
    "identity": {
      "type": "techacct",
      "client_id": "<YOUR_CLIENT_ID>",
      "client_secret": "<YOUR_CLIENT_SECRET>",
      "private_key": "---BEGIN RSA PRIVATE KEY---\nXXXXX..XXXX\n---END RSA PRIVATE KEY-----\n",
      "claim": "https://ims-na1.adobelogin.com/s/ent_documentcloud_sdk",
      "issuer": "<YOUR_ORGANIZATION_ID>",
      "subject": "<YOUR_TECHINCAL_ACCOUNT_ID>"
    },
      "timeout": "2000",
      "uploadTimeout": "400000",
      "readWriteTimeout": "10000"
  }
```

### Heading 3

HTML snippet

```
<html>
<head>
  <title>Your title</title>
  <meta charset="utf-8"/>
  <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1"/>
  <script src="https://documentcloud.adobe.com/view-sdk/main.js"></script>
</head>
<body>
  <div id="adobe-dc-view"></div>
  <script type="text/javascript">
   document.addEventListener("adobe_dc_view_sdk.ready", function()
   {
      var adobeDCView = new AdobeDC.View({clientId: "<YOUR_CLIENT_ID>", divId: "adobe-dc-view"});
      adobeDCView.previewFile(
     {
         content:  {location: {url: "(path to your PDF)/yourfilename.pdf"}},
         metaData: {fileName: "yourfilename.pdf"}
     });
   });
  </script>
</body>
</html>
<!--Get the samples from https://www.adobe.com/go/dcviewsdk_samples-->
```

Bullets

* [Relative link](./servicessdk/index.html)
* [Relative link](./viewsdk/index.html)
* HTTPS link: [Dev Key](https://www.adobe.com/go/dcsdk_requestform)
    -nested bullet
    -nested bullet
    -nested bullet

Numbering

1. It's a bit stupid
2. to actually have to
3. type the number to get numbering!
4. Oh well. 