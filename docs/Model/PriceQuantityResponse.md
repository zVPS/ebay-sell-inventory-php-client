# # PriceQuantityResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**errors** | [**\Ebay\Sell\Inventory\Model\Error[]**](Error.md) | This array will be returned if there were one or more errors associated with the update to the offer or inventory item record. | [optional]
**offer_id** | **string** | The unique identifier of the offer that was updated. This field will not be returned in situations where the seller is only updating the total &#39;ship-to-home&#39; quantity of an inventory item record. | [optional]
**sku** | **string** | This is the seller-defined SKU value of the product. This field is returned whether the seller attempted to update an offer with the SKU value or just attempted to update the total &#39;ship-to-home&#39; quantity of an inventory item record. Max Length: 50 | [optional]
**status_code** | **int** | The value returned in this container will indicate the status of the attempt to update the price and/or quantity of the offer (specified in the corresponding offerId field) or the attempt to update the total &#39;ship-to-home&#39; quantity of an inventory item (specified in the corresponding sku field). For a completely successful update of an offer or inventory item record, a value of 200 will appear in this field. A user can view the HTTP status codes section for information on other status codes that may be returned with the bulkUpdatePriceQuantity method. | [optional]
**warnings** | [**\Ebay\Sell\Inventory\Model\Error[]**](Error.md) | This array will be returned if there were one or more warnings associated with the update to the offer or inventory item record. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
