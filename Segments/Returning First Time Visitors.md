# Returning First Time Visitors
Segment to return all Hits from Visitors who had both their first and second Visit in a given Date Range. Created by [frederikwerner](https://github.com/frederikwerner) for [fullstackanalyst.io](https://www.fullstackanalyst.io/?r=g)

## Usage examples
* Can be used in a table or graph together with the Unique Visitors metric to show the number of Visitors who had both their first and their second Visit in the selected Date Range.
* Can be used in Retention Metrics
* Can be used to show the percentage of Visitors who were acquired and retained in a given Date Range
* Can be used with the First Time Visits Segment to show the day a User came for the first time and returned later on

## Business questions
* How many Users visited my site for the first time and came back?
* How many of the new Users acquired by a campaign came back?

## Screenshots
![Returning First Time Visitors Segment in Adobe Analytics](res/returningfirsttimevisitors2.png)
![Returning First Time Visitors Segment with First Time Visits Segment in Adobe Analytics](res/returningfirsttimevisitors3.png)
## Tags
Retention, Customer Journey, Acquisition

## Definitions
### Screenshot of segment builder
![Segment Builder](res/returningfirsttimevisitors1.png)
### API definition of segment
```yaml
{
    "definition": {
        "container": {
            "func": "container",
            "pred": {
                "func": "and",
                "preds": [
                    {
                        "val": {
                            "func": "attr",
                            "name": "variables/visitnumber"
                        },
                        "func": "eq",
                        "num": 1,
                        "description": "Visit Number"
                    },
                    {
                        "val": {
                            "func": "attr",
                            "name": "variables/visitnumber"
                        },
                        "func": "eq",
                        "num": 2,
                        "description": "Visit Number"
                    }
                ]
            },
            "context": "visitors"
        },
        "func": "segment",
        "version": [
            1,
            0,
            0
        ]
    }
}
```