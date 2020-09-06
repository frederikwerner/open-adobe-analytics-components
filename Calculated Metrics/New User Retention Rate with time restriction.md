# New User Retention Rate with time restriction
Metric showing the percentage of users who came to a site for the first time and came back within a certain time in the Reporting Window. Created by [frederikwerner](https://github.com/frederikwerner) for [fullstackanalyst.io](https://www.fullstackanalyst.io/?r=g)

## Usage examples
* Put in a table or graph to see the trend in New User Retention within a certain time over time
* Use with marketing campaigns to see how many of the newly acquired users came back within a certain time

## Business questions
* Are the people we acquire through campaigns coming back to our site within the time we want?
* Are the features we build beneficial or detrimental to user retention within a certain time?

## Screenshots
![New User Retention Rate with time restriction in Adobe Analytics](res/newuserretentionratewithtimerestriction3.png)  
![New User Retention Rate with time restriction in Adobe Analytics](res/newuserretentionratewithtimerestriction4.png)

## Dependencies
* [Returning First Time Visitors with time restriction](../Segments/Returning%20First%20Time%20Visitors%20with%20time%20restriction.md) Segment
* First Time Visits Segment

## Tags
Retention, Customer Journey, Acquisition

## Definitions
### Screenshot of metric overview
![Metric Summary](res/newuserretentionratewithtimerestriction1.png)
### Screenshot of metric builder
![Metric Builder](res/newuserretentionratewithtimerestriction2.png)
### API definition of metric
```yaml
{
    "definition": {
        "formula": {
            "func": "divide",
            "col1": {
                "func": "calc-metric",
                "formula": {
                    "func": "metric",
                    "name": "metrics/visitors",
                    "description": "Unique Visitors"
                },
                "version": [
                    1,
                    0,
                    0
                ],
                "filters": [
                    {
                        "func": "segment-ref",
                        "description": "First Time Visits",
                        "id": "First_Time_Visits"
                    },
                    {
                        "func": "segment-ref",
                        "description": "Returning First Time Visitors with time restriction",
                        "id": "[ID of Returning First Time Visitors with time restriction Segment]"
                    }
                ]
            },
            "col2": {
                "func": "calc-metric",
                "formula": {
                    "func": "metric",
                    "name": "metrics/visitors",
                    "description": "Unique Visitors"
                },
                "version": [
                    1,
                    0,
                    0
                ],
                "filters": [
                    {
                        "func": "segment-ref",
                        "description": "First Time Visits",
                        "id": "First_Time_Visits"
                    }
                ]
            }
        },
        "func": "calc-metric",
        "version": [
            1,
            0,
            0
        ]
    }
}
```