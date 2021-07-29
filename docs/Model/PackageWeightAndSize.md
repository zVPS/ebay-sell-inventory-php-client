# # PackageWeightAndSize

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**dimensions** | [**\Ebay\Sell\Inventory\Model\Dimension**](Dimension.md) |  | [optional]
**package_type** | **string** | This enumeration value indicates the type of shipping package used to ship the inventory item. The supported values for this field can be found in the PackageTypeEnum type. This field will be returned if the package type is set for the inventory item. Note: You can use the GeteBayDetails Trading API call to retrieve a list of supported package types for a specific marketplace. For implementation help, refer to &lt;a href&#x3D;&#39;https://developer.ebay.com/api-docs/sell/inventory/types/slr:PackageTypeEnum&#39;&gt;eBay API documentation&lt;/a&gt; | [optional]
**weight** | [**\Ebay\Sell\Inventory\Model\Weight**](Weight.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
