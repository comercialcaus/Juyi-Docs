# JuyiSDKCsharp.Api.ProductsApi

All URIs are relative to *http://185.208.220.95:8088/WSJuyi2.0/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**FindProduct**](ProductsApi.md#findproduct) | **POST** /products/find | Find a product.
[**GetAllProducts**](ProductsApi.md#getallproducts) | **GET** /products/getAll | List all products.



## FindProduct

> Product FindProduct (FindProductRequest findProductRequest)

Find a product.

Gets a single product by passing a sku.

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using JuyiSDKCsharp.Api;
using JuyiSDKCsharp.Client;
using JuyiSDKCsharp.Model;

namespace Example
{
    public class FindProductExample
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "http://185.208.220.95:8088/WSJuyi2.0/api";
            // Configure API key authorization: api_key
            Configuration.Default.AddApiKey("api_key", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // Configuration.Default.AddApiKeyPrefix("api_key", "Bearer");

            var apiInstance = new ProductsApi(Configuration.Default);
            var findProductRequest = new FindProductRequest(); // FindProductRequest | Sku code to search

            try
            {
                // Find a product.
                Product result = apiInstance.FindProduct(findProductRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling ProductsApi.FindProduct: " + e.Message );
                Debug.Print("Status Code: "+ e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **findProductRequest** | [**FindProductRequest**](FindProductRequest.md)| Sku code to search | 

### Return type

[**Product**](Product.md)

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | successful operation |  -  |
| **400** | The Request is Malformed, check if you are calling the correct endpoint and the parameters are correct |  -  |
| **401** | Unauthorized, the api key is missing or wrong |  -  |
| **405** | The HTTP Method in which you send the Request is not valid |  -  |
| **404** | Product Sku not found |  -  |

[[Back to top]](#)
[[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetAllProducts

> GetAllProductsResponse GetAllProducts (int? offset = null, int? limit = null)

List all products.

Gets all the product list we have available to sell with the all the product information we have.

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using JuyiSDKCsharp.Api;
using JuyiSDKCsharp.Client;
using JuyiSDKCsharp.Model;

namespace Example
{
    public class GetAllProductsExample
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "http://185.208.220.95:8088/WSJuyi2.0/api";
            // Configure API key authorization: api_key
            Configuration.Default.AddApiKey("api_key", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // Configuration.Default.AddApiKeyPrefix("api_key", "Bearer");

            var apiInstance = new ProductsApi(Configuration.Default);
            var offset = 0;  // int? | Number of items to skip (optional)  (default to 0)
            var limit = 100;  // int? | Number of items that will return (optional)  (default to 100)

            try
            {
                // List all products.
                GetAllProductsResponse result = apiInstance.GetAllProducts(offset, limit);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling ProductsApi.GetAllProducts: " + e.Message );
                Debug.Print("Status Code: "+ e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **offset** | **int?**| Number of items to skip | [optional] [default to 0]
 **limit** | **int?**| Number of items that will return | [optional] [default to 100]

### Return type

[**GetAllProductsResponse**](GetAllProductsResponse.md)

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | successful operation |  -  |
| **400** | The Request is Malformed, check if you are calling the correct endpoint and the parameters are correct |  -  |
| **401** | Unauthorized, the api key is missing or wrong |  -  |
| **405** | The HTTP Method in which you send the Request is not valid |  -  |

[[Back to top]](#)
[[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)

