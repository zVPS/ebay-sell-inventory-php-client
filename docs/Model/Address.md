# # Address

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**address_line1** | **string** | The first line of a street address. This field is required for store inventory locations that will be holding In-Store Pickup inventory. A street address is not required if the inventory location is not holding In-Store Pickup Inventory. This field will be returned if defined for an inventory location. Max length: 128 | [optional]
**address_line2** | **string** | The second line of a street address. This field can be used for additional address information, such as a suite or apartment number. A street address is not required if the inventory location is not holding In-Store Pickup Inventory. This field will be returned if defined for an inventory location. Max length: 128 | [optional]
**city** | **string** | The city in which the inventory location resides. This field is required for store inventory locations that will be holding In-Store Pickup inventory. For warehouse locations, this field is technically optional, as a postalCode can be used instead of city/stateOrProvince pair, and then the city is just derived from this postal/zip code. This field is returned if defined for an inventory location. Max length: 128 | [optional]
**country** | **string** | The country in which the address resides, represented as two-letter ISO 3166 country code. For example, US represents the United States, and DE represents Germany. Max length: 2 For implementation help, refer to &lt;a href&#x3D;&#39;https://developer.ebay.com/api-docs/sell/inventory/types/CountryCodeEnum\&quot;&#39;&gt;eBay API documentation&lt;/a&gt; | [optional]
**county** | **string** | The county in which the address resides. This field is returned if defined for an inventory location. | [optional]
**postal_code** | **string** | The postal/zip code of the address. eBay uses postal codes to surface In-Store Pickup items within the vicinity of a buyer&#39;s location, and it also user postal codes (origin and destination) to estimate shipping costs when the seller uses calculated shipping. A city/stateOrProvince pair can be used instead of a postalCode value, and then the postal code is just derived from the city and state/province. This field is returned if defined for an inventory location. Max length: 16 | [optional]
**state_or_province** | **string** | The state/province in which the inventory location resides. This field is required for store inventory locations that will be holding In-Store Pickup inventory. For warehouse locations, this field is technically optional, as a postalCode can be used instead of city/stateOrProvince pair, and then the state or province is just derived from this postal/zip code. Max length: 128 | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
