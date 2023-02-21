# Explore Decision Support

[Learning Path](https://learn.microsoft.com/training/paths/explore-fundamentals-of-decision-support/?WT.mc_id=academic-0000-alfredodeza)

## Introduction to Anomaly Detector

[Learning Module](https://learn.microsoft.com/training/modules/intro-to-anomaly-detector/?WT.mc_id=academic-0000-alfredodeza)

Definition: An AI technique to detect if values in a series are within expectations.

Example scenarios:

* Monitoring machine systems like HVAC
* Cloud services usage over time

### Anomaly Detector service

Definition: Part of the Decision Services category in Azure Cognitive Services. Exposes a REST API. The service can detect real-time data or historical data.

Requires a *boundary* set with a sensitivity value. By default, _upper_ and _lower_ boundaries are calculated by including the expected value.

### Data Format

The REST API uses JSON that uses _granularity_ (in time, e.g. "hourly"), the timestamp and the value for each timestamp. There is a max of values that can be sent to the API of 8640.

Streaming is possible sending a single value at a time.

Use interpolation to fill in gaps of measurements if there is more than 10% missing.o

### Use cases

**Batch detection**
Best when the data is almost flat, with some spikes or dips, or a sesonal time series data with some anomalies.
Example: Compliance on temperature control for medicine

**Real-time detection**
Best when requiring the latest measurement to be detected as normal or an anomaly. Every new data point is compared to past (seen) data points.
Example: Current temperature while bottling carbonated drinks.
