# # SpecialHours

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**date** | **string** | A date value is required for each specific date that the store location has special operating hours. The timestamp is formatted as an ISO 8601 string, which is based on the 24-hour Coordinated Universal Time (UTC) clock. Format: [YYYY]-[MM]-[DD]T[hh]:[mm]:[ss].[sss]Z Example: 2018-08-04T07:09:00.000Z This field is returned if set for the store location. | [optional]
**intervals** | [**\Ebay\Sell\Inventory\Model\Interval[]**](Interval.md) | This container is used to define the opening and closing times of a store on a specific date (defined in the date field). An intervals container is needed for each specific date that the store has special operating hours. These special operating hours on the specific date override the normal operating hours for the specific day of the week. If a store location closes for lunch (or any other period during the day) and then reopens, multiple open and close pairs are needed. This container is returned if set for the store location. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
