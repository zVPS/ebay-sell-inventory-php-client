# # PriceQuantity

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**offers** | [**\Ebay\Sell\Inventory\Model\OfferPriceQuantity[]**](OfferPriceQuantity.md) | This container is needed if the seller is updating the price and/or quantity of one or more published offers, and a successful call will actually update the active eBay listing with the revised price and/or available quantity. This call is not designed to work with unpublished offers. For unpublished offers, the seller should use the updateOffer call to update the available quantity and/or price. If the seller is also using the shipToLocationAvailability container and sku field to update the total &#39;ship-to-home&#39; quantity of the inventory item, the SKU value associated with the corresponding offerId value(s) must be the same as the corresponding sku value that is passed in, or an error will occur. A separate (OfferPriceQuantity) node is required for each offer being updated. | [optional]
**ship_to_location_availability** | [**\Ebay\Sell\Inventory\Model\ShipToLocationAvailability**](ShipToLocationAvailability.md) |  | [optional]
**sku** | **string** | This is the seller-defined SKU value of the inventory item whose total &#39;ship-to-home&#39; quantity will be updated. This field is only required when the seller is updating the total quantity of an inventory item using the shipToLocationAvailability container. If the seller is updating the price and/or quantity of one or more specific offers, one or more offerId values are used instead, and the sku value is not needed. If the seller wants to update the price and/or quantity of one or more offers, and also wants to update the total &#39;ship-to-home&#39; quantity of the corresponding inventory item, the SKU value associated with the offerId value(s) must be the same as the corresponding sku value that is passed in, or an error will occur. Max Length: 50 | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
