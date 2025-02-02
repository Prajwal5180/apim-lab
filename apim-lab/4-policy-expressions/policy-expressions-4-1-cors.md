## Task 1: Cross-origin resource sharing (CORS) policy

The [cors policy](<https://docs.microsoft.com/en-us/azure/api-management/api-management-cross-domain-policies#CORS>) adds cross-origin resource sharing (CORS) support to an operation or an API to allow cross-domain calls from browser-based clients.

- We have already configured the **CORS** policy for our APIs in labs 2 & 3. Below is the resulting XML:

    ![APIM Policy CORS All APIs](media/08.png)  

- Click on the **Edit button** to view the XML present within the **CORS** policy.

    ![APIM Policy CORS All APIs](media/all-api1.png)  


```xml
<policies>
    <inbound>
        <cors allow-credentials="true">
            <allowed-origins>
                <origin>https://apim-sk-12212021.developer.azure-api.net</origin>
                <origin>https://colors-web.azurewebsites.net/</origin>
            </allowed-origins>
            <allowed-methods preflight-result-max-age="300">
                <method>*</method>
            </allowed-methods>
            <allowed-headers>
                <header>*</header>
            </allowed-headers>
            <expose-headers>
                <header>*</header>
            </expose-headers>
        </cors>
    </inbound>
    <backend>
        <forward-request />
    </backend>
    <outbound />
    <on-error />
</policies>
```

- Now, click on Next from the lower right corner to move on to the next page.
