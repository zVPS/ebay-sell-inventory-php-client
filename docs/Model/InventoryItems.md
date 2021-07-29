# # InventoryItems

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**href** | **string** | This is the URL to the current page of inventory items. | [optional]
**inventory_items** | [**\Ebay\Sell\Inventory\Model\InventoryItemWithSkuLocaleGroupid[]**](InventoryItemWithSkuLocaleGroupid.md) | This container is an array of one or more inventory items, with detailed information on each inventory item. | [optional]
**limit** | **int** | This integer value is the number of inventory items that will be displayed on each results page. | [optional]
**next** | **string** | This is the URL to the next page of inventory items. This field will only be returned if there are additional inventory items to view. | [optional]
**prev** | **string** | This is the URL to the previous page of inventory items. This field will only be returned if there are previous inventory items to view. | [optional]
**size** | **int** | This integer value indicates the total number of pages of results that are available. This number will depend on the total number of inventory items available for viewing, and on the limit value. | [optional]
**total** | **int** | This integer value is the total number of inventory items that exist for the seller&#39;s account. Based on this number and on the limit value, the seller may have to toggle through multiple pages to view all inventory items. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
