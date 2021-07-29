# # OfferResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**offer_id** | **string** | The unique identifier of the offer that was just created with a createOffer call. It is not returned if the createOffer call fails to create an offer. This identifier will be needed for many offer-related calls. Note: The offerId value is only returned with a successful createOffer call. This field will not be returned in the updateOffer response. | [optional]
**warnings** | [**\Ebay\Sell\Inventory\Model\Error[]**](Error.md) | This container will contain an array of errors and/or warnings when a call is made, and errors and/or warnings occur. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
