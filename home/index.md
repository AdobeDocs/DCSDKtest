# Heading 1

## Heading 2

The [DC Services SDK](./servicessdk/index.html) and [DC View SDK](./viewsdk/index.html) are now available for early access. This version of the SDK provides JAVA APIs, documentation, and sample code.  

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

Javascript snippet

```javascript
Get the samples from https://www.adobe.com/go/dcservicessdk_java_samples
import java.io.IOException;
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import com.adobe.platform.operation.ClientContext;
import com.adobe.platform.operation.exception.SdkException;
import com.adobe.platform.operation.exception.ServiceApiException;
import com.adobe.platform.operation.io.FileRef;
import com.adobe.platform.operation.pdfops.CreatePDFOperation;

public class CreatePDFFromDOCX {

   // Initialize the logger.
   private static final Logger LOGGER = LoggerFactory.getLogger(CreatePDFFromDOCX.class);

   public static void main(String[] args) {

       try {

           // Initial setup, create a ClientContext using a config file and a new operation instance.
           ClientContext clientContext = ClientContext.createFromFile("dc-services-sdk-config.json");
           CreatePDFOperation createPdfOperation = CreatePDFOperation.createNew();

           // Set operation input from a source file.
           FileRef source = FileRef.createFromLocalFile("src/main/resources/createPDFInput.docx");
           createPdfOperation.setInput(source);

           // Execute the operation.
           FileRef result = createPdfOperation.execute(clientContext);

           // Save the result to the specified location.
           result.saveAs("output/createPDFFromDOCX.pdf");

       } catch (ServiceApiException | IOException | SdkException ex) {
           LOGGER.error("Exception encountered while executing operation", ex);
       }
   }
}
```

JSON snippet

```json
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

HTML code sample snippet

```html
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

**Raw HTML that should render as HTML**

> Not sure how useful this is without having custom JS as well. . .  

<br/><br/><br/>
  <div style="color:red;" class="penguin">Penguin</div>
  <div class="duck">duck</div>
  <div class="goose">goose</div>
  <div class="section" id="first-section">
     <h2>first section</h2>
     <p>Blah blah</p>
     <div class="tabs">
    <ul>
       <li><a href="#tabsaaa1">Penguin</a></li>
       <li><a href="#tabsbbb1">duck</a></li>
       <li><a href="#tabsccc1">Goose</a>
    </ul>
    <div id="tabsaaa1" class="penguin"> one </div>
    <div id="tabsbbb1" class="duck"> two </div>
    <div id="tabsccc1" class="goose"> three</div>
   </div>
     <div class="section" id="section-2">
    <h2>Section 2</h2>
    <p>Blah blah</p>
    <div class="tabs">
       <ul>
      <li><a href="#tabsaaa1">Penguin</a></li>
      <li><a href="#tabsbbb1">duck</a></li>
      <li><a href="#tabsccc1">Goose</a>
       </ul>
       <div id="tabsaaa1" class="penguin"> one </div>
       <div id="tabsbbb1" class="duck"> two </div>
       <div id="tabsccc1" class="goose"> three</div>
      </div>
   </div>
    </div>
 </div>
  </div>
		
		

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