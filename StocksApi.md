# JuyiSDKCsharp.Api.StocksApi

All URIs are relative to *http://185.208.220.95:8088/WSJuyi2.0/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**FindStock**](StocksApi.md#findstock) | **POST** /stocks/find | Find a product stock.
[**GetAllStocks**](StocksApi.md#getallstocks) | **GET** /stocks/getAll | List the stock.
[**SynchronizeStocks**](StocksApi.md#synchronizestocks) | **POST** /stocks/synchronize | Synchronizes the stock of the products



## FindStock

> Stock FindStock (FindProductRequest findProductRequest)

Find a product stock.

Gets a single product by passing a sku (It's the same as the product but only returns the sku and stock fields).

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using JuyiSDKCsharp.Api;
using JuyiSDKCsharp.Client;
using JuyiSDKCsharp.Model;

namespace Example
{
    public class FindStockExample
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "http://185.208.220.95:8088/WSJuyi2.0/api";
            // Configure API key authorization: api_key
            Configuration.Default.AddApiKey("api_key", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // Configuration.Default.AddApiKeyPrefix("api_key", "Bearer");

            var apiInstance = new StocksApi(Configuration.Default);
            var findProductRequest = new FindProductRequest(); // FindProductRequest | Sku code to search

            try
            {
                // Find a product stock.
                Stock result = apiInstance.FindStock(findProductRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling StocksApi.FindStock: " + e.Message );
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

[**Stock**](Stock.md)

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
| **404** | Product Stock Sku not found |  -  |

[[Back to top]](#)
[[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetAllStocks

> GetAllStocksResponse GetAllStocks (int? offset = null, int? limit = null)

List the stock.

Returns a list with the products stock (It's the same as the product but only returns the sku and stock fields).

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using JuyiSDKCsharp.Api;
using JuyiSDKCsharp.Client;
using JuyiSDKCsharp.Model;

namespace Example
{
    public class GetAllStocksExample
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "http://185.208.220.95:8088/WSJuyi2.0/api";
            // Configure API key authorization: api_key
            Configuration.Default.AddApiKey("api_key", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // Configuration.Default.AddApiKeyPrefix("api_key", "Bearer");

            var apiInstance = new StocksApi(Configuration.Default);
            var offset = 0;  // int? | Number of items to skip (optional)  (default to 0)
            var limit = 100;  // int? | Number of items that will return (optional)  (default to 100)

            try
            {
                // List the stock.
                GetAllStocksResponse result = apiInstance.GetAllStocks(offset, limit);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling StocksApi.GetAllStocks: " + e.Message );
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

[**GetAllStocksResponse**](GetAllStocksResponse.md)

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


## SynchronizeStocks

> SynchronizeStocksResponse SynchronizeStocks (SynchronizeStocksRequest synchronizeStocksRequest)

Synchronizes the stock of the products

Notifies and inserts the stocks that you have on your warehouse in China in our system

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using JuyiSDKCsharp.Api;
using JuyiSDKCsharp.Client;
using JuyiSDKCsharp.Model;

namespace Example
{
    public class SynchronizeStocksExample
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "http://185.208.220.95:8088/WSJuyi2.0/api";
            // Configure API key authorization: api_key
            Configuration.Default.AddApiKey("api_key", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // Configuration.Default.AddApiKeyPrefix("api_key", "Bearer");

            var apiInstance = new StocksApi(Configuration.Default);
            var synchronizeStocksRequest = new SynchronizeStocksRequest(); // SynchronizeStocksRequest | List of stocks to insert

            try
            {
                // Synchronizes the stock of the products
                SynchronizeStocksResponse result = apiInstance.SynchronizeStocks(synchronizeStocksRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling StocksApi.SynchronizeStocks: " + e.Message );
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
 **synchronizeStocksRequest** | [**SynchronizeStocksRequest**](SynchronizeStocksRequest.md)| List of stocks to insert | 

### Return type

[**SynchronizeStocksResponse**](SynchronizeStocksResponse.md)

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

[[Back to top]](#)
[[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)

