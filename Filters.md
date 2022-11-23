# Filters

Filters allow us to filter on certain asset types or assets. Depending on the type of the property you are filtering on, different filter options will be available. Opening the filter menu shows a list of all the filters in the tenant. Clicking a filter shows all the relevant data. When creating a new filter, first the asset and property filters are set using the below listed filter options. After that a name can be given to a filter, as well as a scope. The scope can be set to three different modes:

- Single use: the filter can only be used in the place it was created
- Reusable: the filter can be used multiple times
- Main menu: the filter can be used multiple times but is listed under the main menu scope when searching filters. This is useful to separate important filters from general filters

All created filters can be found on the Filter page. Selecting a filter listed shows all the filters settings, as well as a list of all the sub filters used in the filter. It also lists where and how many times the filter is referenced

| Filter options                                    | Options shown depend on the type of property                                                                            |
| ------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| ![Equals](Documentation/Filters/0.png)            | Will give all assets that are the same as the filter value.                                                             |
| ![Not Equals](Documentation/Filters/1.png)        | Will give all assets that are not the same as the filter value.                                                         |
| ![Starts with](Documentation/Filters/2.png)       | Will give all assets that start with a certain tag or text.                                                             |
| ![Not starts with](Documentation/Filters/3.png)   | Will give all assets that do not start with a certain tag or text.                                                      |
| ![Ends with](Documentation/Filters/4.png)         | Will give all assets that end with a certain tag or text.                                                               |
| ![Not Ends with](Documentation/Filters/5.png)     | Will give all assets that do not end with a certain tag or text.                                                        |
| ![Contains](Documentation/Filters/6.png)          | Will give all assets that contain a certain tag or text.                                                                |
| ![Not Contains](Documentation/Filters/7.png)      | Will give all assets that do not contain a certain tag or text.                                                         |
| ![No value](Documentation/Filters/8.png)          | Will give all assets that do not yet have a value for the selected property.                                            |
| ![Any value](Documentation/Filters/9.png)         | Will give all assets that have a value for the selected property.                                                       |
| ![Near](Documentation/Filters/10.png)             | Will give all assets that fall within a certain distance of a selected position. Not yet fully implemented.             |
| ![Less than](Documentation/Filters/11.png)        | Will give all assets that have a lower value than the filter value. (In date, this is before filter date)               |
| ![Less or equal](Documentation/Filters/12.png)    | Will give all assets that have a lower or equal value to the filter value. (In date, this is before or on filter date)  |
| ![Greather than](Documentation/Filters/13.png)    | Will give all assets that have a greater value than the filter value. (In date, this is after filter date)              |
| ![Greater or equal](Documentation/Filters/14.png) | Will give all assets that have a greater or equal value to the filter value. (In date, this is after or on filter date) |
| ![One of these](Documentation/Filters/15.png)     | Will give all assets that contain a certain asset.                                                                      |
| ![Not One of these](Documentation/Filters/16.png) | Will give all assets that do not contain a certain asset.                                                               |

Pressing the ![Expression](Documentation/Filters/18.png) symbol allows for more advanced filters to be written using java-script. Where ‘&&’ means ‘and’, || means ‘or’ and ‘!’ means ‘not’.
When creating a filter in a view:

![Save filter](Documentation/Filters/19.png) allows you to save the filter to be used later in widgets (see [widgets](Widgets.md)).

![Reset](Documentation/Filters/20.png) clears all filter settings.
