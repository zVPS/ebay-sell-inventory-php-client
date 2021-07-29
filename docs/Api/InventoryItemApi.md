# Ebay\Sell\InventoryItemApi

All URIs are relative to https://api.ebay.com/sell/inventory/v1.

Method | HTTP request | Description
------------- | ------------- | -------------
[**bulkCreateOrReplaceInventoryItem()**](InventoryItemApi.md#bulkCreateOrReplaceInventoryItem) | **POST** /bulk_create_or_replace_inventory_item | 
[**bulkGetInventoryItem()**](InventoryItemApi.md#bulkGetInventoryItem) | **POST** /bulk_get_inventory_item | 
[**bulkUpdatePriceQuantity()**](InventoryItemApi.md#bulkUpdatePriceQuantity) | **POST** /bulk_update_price_quantity | 
[**createOrReplaceInventoryItem()**](InventoryItemApi.md#createOrReplaceInventoryItem) | **PUT** /inventory_item/{sku} | 
[**deleteInventoryItem()**](InventoryItemApi.md#deleteInventoryItem) | **DELETE** /inventory_item/{sku} | 
[**getInventoryItem()**](InventoryItemApi.md#getInventoryItem) | **GET** /inventory_item/{sku} | 
[**getInventoryItems()**](InventoryItemApi.md#getInventoryItems) | **GET** /inventory_item | 


## `bulkCreateOrReplaceInventoryItem()`

```php
bulkCreateOrReplaceInventoryItem($body): \Ebay\Sell\Inventory\Model\BulkInventoryItemResponse
```



Note: Please note that any eBay listing created using the Inventory API cannot be revised or relisted using the Trading API calls. This call can be used to create and/or update up to 25 new inventory item records. It is up to sellers whether they want to create a complete inventory item records right from the start, or sellers can provide only some information with the initial bulkCreateOrReplaceInventoryItem call, and then make one or more additional bulkCreateOrReplaceInventoryItem calls to complete all required fields for the inventory item records and prepare for publishing. Upon first creating inventory item records, only the SKU values are required. In the case of updating existing inventory item records, the bulkCreateOrReplaceInventoryItem call will do a complete replacement of the existing inventory item records, so all fields that are currently defined for the inventory item record are required in that update action, regardless of whether their values changed. So, when replacing/updating an inventory item record, it is advised that the seller run a 'Get' call to retrieve the full details of the inventory item records and see all of its current values/settings before attempting to update the records. Any changes that are made to inventory item records that are part of one or more active eBay listings, a successful call will automatically update these active listings. The key information that is set with the bulkCreateOrReplaceInventoryItem call include: Seller-defined SKU value for the product. Each seller product, including products within an item inventory group, must have their own SKU value. Condition of the item Product details, including any product identifier(s), such as a UPC, ISBN, EAN, or Brand/Manufacturer Part Number pair, a product description, a product title, product/item aspects, and links to images. eBay will use any supplied eBay Product ID (ePID) or a GTIN (UPC, ISBN, or EAN) and attempt to match those identifiers to a product in the eBay Catalog, and if a product match is found, the product details for the inventory item will automatically be populated. Quantity of the inventory item that is available for purchase Package weight and dimensions, which is required if the seller will be offering calculated shipping options. The package weight will also be required if the seller will be providing flat-rate shipping services, but charging a weight surcharge. In addition to the authorization header, which is required for all eBay REST API calls, the bulkCreateOrReplaceInventoryItem call also requires the Content-Language header, that sets the natural language that will be used in the field values of the request payload. For US English, the code value passed in this header should be en-US. To view other supported Content-Language values, and to read more about all supported HTTP headers for eBay REST API calls, see the HTTP request headers topic in the Using eBay RESTful APIs document. For those who prefer to create or update a single inventory item record, the createOrReplaceInventoryItem method can be used.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: Authorization Code
$config = Ebay\Sell\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Ebay\Sell\Api\InventoryItemApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = new \Ebay\Sell\Inventory\Model\BulkInventoryItem(); // \Ebay\Sell\Inventory\Model\BulkInventoryItem | Details of the inventories with sku and locale

try {
    $result = $apiInstance->bulkCreateOrReplaceInventoryItem($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InventoryItemApi->bulkCreateOrReplaceInventoryItem: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**\Ebay\Sell\Inventory\Model\BulkInventoryItem**](../Model/BulkInventoryItem.md)| Details of the inventories with sku and locale |

### Return type

[**\Ebay\Sell\Inventory\Model\BulkInventoryItemResponse**](../Model/BulkInventoryItemResponse.md)

### Authorization

[Authorization Code](../../README.md#Authorization Code)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `bulkGetInventoryItem()`

```php
bulkGetInventoryItem($body): \Ebay\Sell\Inventory\Model\BulkGetInventoryItemResponse
```



This call retrieves up to 25 inventory item records. The SKU value of each inventory item record to retrieve is specified in the request payload. The authorization header is the only required HTTP header for this call, and it is required for all Inventory API calls. See the HTTP request headers section for more information. For those who prefer to retrieve only one inventory item record by SKU value, , the getInventoryItem method can be used. To retrieve all inventory item records defined on the seller's account, the getInventoryItems method can be used (with pagination control if desired).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: Authorization Code
$config = Ebay\Sell\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Ebay\Sell\Api\InventoryItemApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = new \Ebay\Sell\Inventory\Model\BulkGetInventoryItem(); // \Ebay\Sell\Inventory\Model\BulkGetInventoryItem | Details of the inventories with sku and locale

try {
    $result = $apiInstance->bulkGetInventoryItem($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InventoryItemApi->bulkGetInventoryItem: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**\Ebay\Sell\Inventory\Model\BulkGetInventoryItem**](../Model/BulkGetInventoryItem.md)| Details of the inventories with sku and locale |

### Return type

[**\Ebay\Sell\Inventory\Model\BulkGetInventoryItemResponse**](../Model/BulkGetInventoryItemResponse.md)

### Authorization

[Authorization Code](../../README.md#Authorization Code)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `bulkUpdatePriceQuantity()`

```php
bulkUpdatePriceQuantity($body): \Ebay\Sell\Inventory\Model\BulkPriceQuantityResponse
```



This call is used by the seller to update the total ship-to-home quantity of one inventory item, and/or to update the price and/or quantity of one or more offers associated with one inventory item. Up to 25 offers associated with an inventory item may be updated with one bulkUpdatePriceQuantity call. Only one SKU (one product) can be updated per call. The getOffers call can be used to retrieve all offers associated with a SKU. The seller will just pass in the correct SKU value through the sku query parameter. To update an offer, the offerId value is required, and this value is returned in the getOffers call response. It is also useful to know which offers are unpublished and which ones are published. To get this status, look for the status value in the getOffers call response. Offers in the published state are live eBay listings, and these listings will be revised with a successful bulkUpdatePriceQuantity call. An issue will occur if duplicate offerId values are passed through the same offers container, or if one or more of the specified offers are associated with different products/SKUs. Note: For multiple-variation listings, it is recommended that the bulkUpdatePriceQuantity call be used to update price and quantity information for each SKU within that multiple-variation listing instead of using createOrReplaceInventoryItem calls to update the price and quantity for each SKU. Just remember that only one SKU (one product variation) can be updated per call. The authorization header is the only required HTTP header for this call. See the HTTP request headers section for more information.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: Authorization Code
$config = Ebay\Sell\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Ebay\Sell\Api\InventoryItemApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = new \Ebay\Sell\Inventory\Model\BulkPriceQuantity(); // \Ebay\Sell\Inventory\Model\BulkPriceQuantity | Price and allocation details for the given SKU and Marketplace

try {
    $result = $apiInstance->bulkUpdatePriceQuantity($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InventoryItemApi->bulkUpdatePriceQuantity: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**\Ebay\Sell\Inventory\Model\BulkPriceQuantity**](../Model/BulkPriceQuantity.md)| Price and allocation details for the given SKU and Marketplace |

### Return type

[**\Ebay\Sell\Inventory\Model\BulkPriceQuantityResponse**](../Model/BulkPriceQuantityResponse.md)

### Authorization

[Authorization Code](../../README.md#Authorization Code)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createOrReplaceInventoryItem()`

```php
createOrReplaceInventoryItem($content_language, $sku, $body): \Ebay\Sell\Inventory\Model\BaseResponse
```



Note: Please note that any eBay listing created using the Inventory API cannot be revised or relisted using the Trading API calls. This call creates a new inventory item record or replaces an existing inventory item record. It is up to sellers whether they want to create a complete inventory item record right from the start, or sellers can provide only some information with the initial createOrReplaceInventoryItem call, and then make one or more additional createOrReplaceInventoryItem calls to complete all required fields for the inventory item record and prepare it for publishing. Upon first creating an inventory item record, only the SKU value in the call path is required. In the case of replacing an existing inventory item record, the createOrReplaceInventoryItem call will do a complete replacement of the existing inventory item record, so all fields that are currently defined for the inventory item record are required in that update action, regardless of whether their values changed. So, when replacing/updating an inventory item record, it is advised that the seller run a getInventoryItem call to retrieve the full inventory item record and see all of its current values/settings before attempting to update the record. And if changes are made to an inventory item that is part of one or more active eBay listings, a successful call will automatically update these eBay listings. The key information that is set with the createOrReplaceInventoryItem call include: Seller-defined SKU value for the product. Each seller product, including products within an item inventory group, must have their own SKU value. This SKU value is passed in at the end of the call URI Condition of the item Product details, including any product identifier(s), such as a UPC, ISBN, EAN, or Brand/Manufacturer Part Number pair, a product description, a product title, product/item aspects, and links to images. eBay will use any supplied eBay Product ID (ePID) or a GTIN (UPC, ISBN, or EAN) and attempt to match those identifiers to a product in the eBay Catalog, and if a product match is found, the product details for the inventory item will automatically be populated. Quantity of the inventory item that is available for purchase Package weight and dimensions, which is required if the seller will be offering calculated shipping options. The package weight will also be required if the seller will be providing flat-rate shipping services, but charging a weight surcharge. In addition to the authorization header, which is required for all eBay REST API calls, the createOrReplaceInventoryItem call also requires the Content-Language header, that sets the natural language that will be used in the field values of the request payload. For US English, the code value passed in this header should be en-US. To view other supported Content-Language values, and to read more about all supported HTTP headers for eBay REST API calls, see the HTTP request headers topic in the Using eBay RESTful APIs document. For those who prefer to create or update numerous inventory item records with one call (up to 25 at a time), the bulkCreateOrReplaceInventoryItem method can be used.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: Authorization Code
$config = Ebay\Sell\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Ebay\Sell\Api\InventoryItemApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$content_language = 'content_language_example'; // string | This request header sets the natural language that will be provided in the field values of the request payload.
$sku = 'sku_example'; // string | The seller-defined SKU value for the inventory item is required whether the seller is creating a new inventory item, or updating an existing inventory item. This SKU value is passed in at the end of the call URI. SKU values must be unique across the seller's inventory. Max length: 50.
$body = new \Ebay\Sell\Inventory\Model\InventoryItem(); // \Ebay\Sell\Inventory\Model\InventoryItem | Details of the inventory item record.

try {
    $result = $apiInstance->createOrReplaceInventoryItem($content_language, $sku, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InventoryItemApi->createOrReplaceInventoryItem: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **content_language** | **string**| This request header sets the natural language that will be provided in the field values of the request payload. |
 **sku** | **string**| The seller-defined SKU value for the inventory item is required whether the seller is creating a new inventory item, or updating an existing inventory item. This SKU value is passed in at the end of the call URI. SKU values must be unique across the seller&#39;s inventory. Max length: 50. |
 **body** | [**\Ebay\Sell\Inventory\Model\InventoryItem**](../Model/InventoryItem.md)| Details of the inventory item record. |

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

## `deleteInventoryItem()`

```php
deleteInventoryItem($sku)
```



This call is used to delete an inventory item record associated with a specified SKU. A successful call will not only delete that inventory item record, but will also have the following effects: Delete any and all unpublished offers associated with that SKU; Delete any and all single-variation eBay listings associated with that SKU; Automatically remove that SKU from a multiple-variation listing and remove that SKU from any and all inventory item groups in which that SKU was a member. The authorization header is the only required HTTP header for this call. See the HTTP request headers section for more information.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: Authorization Code
$config = Ebay\Sell\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Ebay\Sell\Api\InventoryItemApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$sku = 'sku_example'; // string | This is the seller-defined SKU value of the product whose inventory item record you wish to delete. Max length: 50.

try {
    $apiInstance->deleteInventoryItem($sku);
} catch (Exception $e) {
    echo 'Exception when calling InventoryItemApi->deleteInventoryItem: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **sku** | **string**| This is the seller-defined SKU value of the product whose inventory item record you wish to delete. Max length: 50. |

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

## `getInventoryItem()`

```php
getInventoryItem($sku): \Ebay\Sell\Inventory\Model\InventoryItemWithSkuLocaleGroupid
```



This call retrieves the inventory item record for a given SKU. The SKU value is passed in at the end of the call URI. There is no request payload for this call. The authorization header is the only required HTTP header for this call, and it is required for all Inventory API calls. See the HTTP request headers section for more information. For those who prefer to retrieve numerous inventory item records by SKU value with one call (up to 25 at a time), the bulkGetInventoryItem method can be used. To retrieve all inventory item records defined on the seller's account, the getInventoryItems method can be used (with pagination control if desired).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: Authorization Code
$config = Ebay\Sell\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Ebay\Sell\Api\InventoryItemApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$sku = 'sku_example'; // string | This is the seller-defined SKU value of the product whose inventory item record you wish to retrieve. Max length: 50.

try {
    $result = $apiInstance->getInventoryItem($sku);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InventoryItemApi->getInventoryItem: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **sku** | **string**| This is the seller-defined SKU value of the product whose inventory item record you wish to retrieve. Max length: 50. |

### Return type

[**\Ebay\Sell\Inventory\Model\InventoryItemWithSkuLocaleGroupid**](../Model/InventoryItemWithSkuLocaleGroupid.md)

### Authorization

[Authorization Code](../../README.md#Authorization Code)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getInventoryItems()`

```php
getInventoryItems($limit, $offset): \Ebay\Sell\Inventory\Model\InventoryItems
```



This call retrieves all inventory item records defined for the seller's account. The limit query parameter allows the seller to control how many records are returned per page, and the offset query parameter is used to retrieve a specific page of records. The seller can make multiple calls to scan through multiple pages of records. There is no request payload for this call. The authorization header is the only required HTTP header for this call, and it is required for all Inventory API calls. See the HTTP request headers section for more information. For those who prefer to retrieve numerous inventory item records by SKU value with one call (up to 25 at a time), the bulkGetInventoryItem method can be used.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: Authorization Code
$config = Ebay\Sell\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Ebay\Sell\Api\InventoryItemApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$limit = 'limit_example'; // string | The value passed in this query parameter sets the maximum number of records to return per page of data. Although this field is a string, the value passed in this field should be an integer from 1 to 100. If this query parameter is not set, up to 100 records will be returned on each page of results. Min: 1, Max: 100
$offset = 'offset_example'; // string | The value passed in this query parameter sets the page number to retrieve. The first page of records has a value of 0, the second page of records has a value of 1, and so on. If this query parameter is not set, its value defaults to 0, and the first page of records is returned.

try {
    $result = $apiInstance->getInventoryItems($limit, $offset);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InventoryItemApi->getInventoryItems: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **limit** | **string**| The value passed in this query parameter sets the maximum number of records to return per page of data. Although this field is a string, the value passed in this field should be an integer from 1 to 100. If this query parameter is not set, up to 100 records will be returned on each page of results. Min: 1, Max: 100 | [optional]
 **offset** | **string**| The value passed in this query parameter sets the page number to retrieve. The first page of records has a value of 0, the second page of records has a value of 1, and so on. If this query parameter is not set, its value defaults to 0, and the first page of records is returned. | [optional]

### Return type

[**\Ebay\Sell\Inventory\Model\InventoryItems**](../Model/InventoryItems.md)

### Authorization

[Authorization Code](../../README.md#Authorization Code)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
