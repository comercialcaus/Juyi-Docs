# JuyiSDKCsharp.Api.OrdersApi

All URIs are relative to *http://185.208.220.95:8088/WSJuyi2.0/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**FindOrder**](OrdersApi.md#findorder) | **POST** /orders/find | Find an Order.
[**GetAllOrders**](OrdersApi.md#getallorders) | **GET** /orders/getAll | List all orders.
[**SynchronizeOrders**](OrdersApi.md#synchronizeorders) | **POST** /orders/synchronize | Synchronize Orders.
[**SynchronizeShipOrders**](OrdersApi.md#synchronizeshiporders) | **POST** /orders/synchronizeShip | Synchronize the shipment of the prepared orders.



## FindOrder

> Order FindOrder (FindOrderRequest findOrderRequest)

Find an Order.

Gets a single order that's inserted in our system by passing an order_id.

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using JuyiSDKCsharp.Api;
using JuyiSDKCsharp.Client;
using JuyiSDKCsharp.Model;

namespace Example
{
    public class FindOrderExample
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "http://185.208.220.95:8088/WSJuyi2.0/api";
            // Configure API key authorization: api_key
            Configuration.Default.AddApiKey("api_key", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // Configuration.Default.AddApiKeyPrefix("api_key", "Bearer");

            var apiInstance = new OrdersApi(Configuration.Default);
            var findOrderRequest = new FindOrderRequest(); // FindOrderRequest | Order id to search

            try
            {
                // Find an Order.
                Order result = apiInstance.FindOrder(findOrderRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling OrdersApi.FindOrder: " + e.Message );
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
 **findOrderRequest** | [**FindOrderRequest**](FindOrderRequest.md)| Order id to search | 

### Return type

[**Order**](Order.md)

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
| **404** | Order not found |  -  |

[[Back to top]](#)
[[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetAllOrders

> GetAllOrdersResponse GetAllOrders (int? offset = null, int? limit = null)

List all orders.

Gets all orders that are inserted in our system.

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using JuyiSDKCsharp.Api;
using JuyiSDKCsharp.Client;
using JuyiSDKCsharp.Model;

namespace Example
{
    public class GetAllOrdersExample
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "http://185.208.220.95:8088/WSJuyi2.0/api";
            // Configure API key authorization: api_key
            Configuration.Default.AddApiKey("api_key", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // Configuration.Default.AddApiKeyPrefix("api_key", "Bearer");

            var apiInstance = new OrdersApi(Configuration.Default);
            var offset = 0;  // int? | Number of items to skip (optional)  (default to 0)
            var limit = 100;  // int? | Number of items that will return (optional)  (default to 100)

            try
            {
                // List all orders.
                GetAllOrdersResponse result = apiInstance.GetAllOrders(offset, limit);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling OrdersApi.GetAllOrders: " + e.Message );
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

[**GetAllOrdersResponse**](GetAllOrdersResponse.md)

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


## SynchronizeOrders

> SynchronizeOrdersResponse SynchronizeOrders (SynchronizeOrdersRequest synchronizeOrdersRequest)

Synchronize Orders.

You need to send us the new orders, so it will notify our system that you have new orders and will insert them, so we can start preparing the shipment, if one order is already in the system it will be ignored.

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using JuyiSDKCsharp.Api;
using JuyiSDKCsharp.Client;
using JuyiSDKCsharp.Model;

namespace Example
{
    public class SynchronizeOrdersExample
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "http://185.208.220.95:8088/WSJuyi2.0/api";
            // Configure API key authorization: api_key
            Configuration.Default.AddApiKey("api_key", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // Configuration.Default.AddApiKeyPrefix("api_key", "Bearer");

            var apiInstance = new OrdersApi(Configuration.Default);
            var synchronizeOrdersRequest = new SynchronizeOrdersRequest(); // SynchronizeOrdersRequest | List of orders to insert

            try
            {
                // Synchronize Orders.
                SynchronizeOrdersResponse result = apiInstance.SynchronizeOrders(synchronizeOrdersRequest);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling OrdersApi.SynchronizeOrders: " + e.Message );
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
 **synchronizeOrdersRequest** | [**SynchronizeOrdersRequest**](SynchronizeOrdersRequest.md)| List of orders to insert | 

### Return type

[**SynchronizeOrdersResponse**](SynchronizeOrdersResponse.md)

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


## SynchronizeShipOrders

> SynchronizeShipResponse SynchronizeShipOrders ()

Synchronize the shipment of the prepared orders.

This api returns the orders that we have prepared and are ready to ship, if they don't have an error it means that they will be 'Shipped' and won't appear again, so make sure you notify your system which ones are shipped correctly because they will onyl appear once.

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using JuyiSDKCsharp.Api;
using JuyiSDKCsharp.Client;
using JuyiSDKCsharp.Model;

namespace Example
{
    public class SynchronizeShipOrdersExample
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "http://185.208.220.95:8088/WSJuyi2.0/api";
            // Configure API key authorization: api_key
            Configuration.Default.AddApiKey("api_key", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // Configuration.Default.AddApiKeyPrefix("api_key", "Bearer");

            var apiInstance = new OrdersApi(Configuration.Default);

            try
            {
                // Synchronize the shipment of the prepared orders.
                SynchronizeShipResponse result = apiInstance.SynchronizeShipOrders();
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling OrdersApi.SynchronizeShipOrders: " + e.Message );
                Debug.Print("Status Code: "+ e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**SynchronizeShipResponse**](SynchronizeShipResponse.md)

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

