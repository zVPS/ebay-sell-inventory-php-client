# Ebay\Sell\Inventory\InventoryItemGroupApi

All URIs are relative to https://api.ebay.com/sell/inventory/v1.

Method | HTTP request | Description
------------- | ------------- | -------------
[**createOrReplaceInventoryItemGroup()**](InventoryItemGroupApi.md#createOrReplaceInventoryItemGroup) | **PUT** /inventory_item_group/{inventoryItemGroupKey} | 
[**deleteInventoryItemGroup()**](InventoryItemGroupApi.md#deleteInventoryItemGroup) | **DELETE** /inventory_item_group/{inventoryItemGroupKey} | 
[**getInventoryItemGroup()**](InventoryItemGroupApi.md#getInventoryItemGroup) | **GET** /inventory_item_group/{inventoryItemGroupKey} | 


## `createOrReplaceInventoryItemGroup()`

```php
createOrReplaceInventoryItemGroup($content_language, $inventory_item_group_key, $body): \Ebay\Sell\Inventory\Model\BaseResponse
```



This call creates a new inventory item group or updates an existing inventory item group. It is up to sellers whether they want to create a complete inventory item group record right from the start, or sellers can provide only some information with the initial createOrReplaceInventoryItemGroup call, and then make one or more additional createOrReplaceInventoryItemGroup calls to complete the inventory item group record. Upon first creating an inventory item group record, the only required elements are the inventoryItemGroupKey identifier in the call URI, and the members of the inventory item group specified through the variantSKUs array in the request payload. In the case of updating/replacing an existing inventory item group, this call does a complete replacement of the existing inventory item group record, so all fields (including the member SKUs) that make up the inventory item group are required, regardless of whether their values changed. So, when replacing/updating an inventory item group record, it is advised that the seller run a getInventoryItemGroup call for that inventory item group to see all of its current values/settings/members before attempting to update the record. And if changes are made to an inventory item group that is part of a live, multiple-variation eBay listing, these changes automatically update the eBay listing. For example, if a SKU value is removed from the inventory item group, the corresponding product variation will be removed from the eBay listing as well. In addition to the required inventory item group identifier and member SKUs, other key information that is set with this call include: Title and description of the inventory item group. The string values provided in these fields will actually become the listing title and listing description of the listing once the first SKU of the inventory item group is published successfully Common aspects that inventory items in the qroup share Product aspects that vary within each product variation Links to images demonstrating the variations of the product, and these images should correspond to the product aspect that is set with the variesBy.aspectsImageVariesBy field In addition to the authorization header, which is required for all eBay REST API calls, the createOrReplaceInventoryItemGroup call also requires the Content-Language header, that sets the natural language that will be used in the field values of the request payload. For US English, the code value passed in this header should be en-US. To view other supported Content-Language values, and to read more about all supported HTTP headers for eBay REST API calls, see the HTTP request headers topic in the Using eBay RESTful APIs document.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: Authorization Code
$config = Ebay\Sell\Inventory\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Ebay\Sell\Inventory\Api\InventoryItemGroupApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$content_language = 'content_language_example'; // string | This request header sets the natural language that will be provided in the field values of the request payload.
$inventory_item_group_key = 'inventory_item_group_key_example'; // string | Unique identifier of the inventory item group. This identifier is supplied by the seller. The inventoryItemGroupKey value for the inventory item group to create/update is passed in at the end of the call URI. This value cannot be changed once it is set.
$body = new \Ebay\Sell\Inventory\Model\InventoryItemGroup(); // \Ebay\Sell\Inventory\Model\InventoryItemGroup | Details of the inventory Item Group

try {
    $result = $apiInstance->createOrReplaceInventoryItemGroup($content_language, $inventory_item_group_key, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InventoryItemGroupApi->createOrReplaceInventoryItemGroup: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **content_language** | **string**| This request header sets the natural language that will be provided in the field values of the request payload. |
 **inventory_item_group_key** | **string**| Unique identifier of the inventory item group. This identifier is supplied by the seller. The inventoryItemGroupKey value for the inventory item group to create/update is passed in at the end of the call URI. This value cannot be changed once it is set. |
 **body** | [**\Ebay\Sell\Inventory\Model\InventoryItemGroup**](../Model/InventoryItemGroup.md)| Details of the inventory Item Group |

### Return type

[**\Ebay\Sell\Inventory\Model\BaseResponse**](../Model/BaseResponse.md)

### Authorization

[Authorization Code](../../README.md#Authorization Code)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteInventoryItemGroup()`

```php
deleteInventoryItemGroup($inventory_item_group_key)
```



This call deletes the inventory item group for a given inventoryItemGroupKey value.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: Authorization Code
$config = Ebay\Sell\Inventory\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Ebay\Sell\Inventory\Api\InventoryItemGroupApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$inventory_item_group_key = 'inventory_item_group_key_example'; // string | The unique identifier of an inventory item group. This value is assigned by the seller when an inventory item group is created. The inventoryItemGroupKey value for the inventory item group to delete is passed in at the end of the call URI.

try {
    $apiInstance->deleteInventoryItemGroup($inventory_item_group_key);
} catch (Exception $e) {
    echo 'Exception when calling InventoryItemGroupApi->deleteInventoryItemGroup: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **inventory_item_group_key** | **string**| The unique identifier of an inventory item group. This value is assigned by the seller when an inventory item group is created. The inventoryItemGroupKey value for the inventory item group to delete is passed in at the end of the call URI. |

### Return type

void (empty response body)

### Authorization

[Authorization Code](../../README.md#Authorization Code)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getInventoryItemGroup()`

```php
getInventoryItemGroup($inventory_item_group_key): \Ebay\Sell\Inventory\Model\InventoryItemGroup
```



This call retrieves the inventory item group for a given inventoryItemGroupKey value. The inventoryItemGroupKey value is passed in at the end of the call URI.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: Authorization Code
$config = Ebay\Sell\Inventory\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Ebay\Sell\Inventory\Api\InventoryItemGroupApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$inventory_item_group_key = 'inventory_item_group_key_example'; // string | The unique identifier of an inventory item group. This value is assigned by the seller when an inventory item group is created. The inventoryItemGroupKey value for the inventory item group to retrieve is passed in at the end of the call URI.

try {
    $result = $apiInstance->getInventoryItemGroup($inventory_item_group_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InventoryItemGroupApi->getInventoryItemGroup: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **inventory_item_group_key** | **string**| The unique identifier of an inventory item group. This value is assigned by the seller when an inventory item group is created. The inventoryItemGroupKey value for the inventory item group to retrieve is passed in at the end of the call URI. |

### Return type

[**\Ebay\Sell\Inventory\Model\InventoryItemGroup**](../Model/InventoryItemGroup.md)

### Authorization

[Authorization Code](../../README.md#Authorization Code)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
