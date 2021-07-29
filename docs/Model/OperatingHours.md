# # OperatingHours

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**day_of_week_enum** | **string** | A dayOfWeekEnum value is required for each day of the week that the store location has regular operating hours. This field is returned if operating hours are defined for the store location. For implementation help, refer to &lt;a href&#x3D;&#39;https://developer.ebay.com/api-docs/sell/inventory/types/api:DayOfWeekEnum&#39;&gt;eBay API documentation&lt;/a&gt; | [optional]
**intervals** | [**\Ebay\Sell\Inventory\Model\Interval[]**](Interval.md) | This container is used to define the opening and closing times of a store&#39;s working day (defined in the dayOfWeekEnum field). An intervals container is needed for each day of the week that the store location is open. If a store location closes for lunch (or any other period during the day) and then reopens, multiple open and close pairs are needed This container is returned if operating hours are defined for the store location. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
