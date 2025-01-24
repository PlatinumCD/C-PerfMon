Rewritten PerfMon Library
=========================

Overview
--------
This document outlines the restructured approach for the CPU Performance Monitor, drawing inspiration from principles of large-scale software design. The library now employs a configuration-based methodology, replacing preprocessor directives to facilitate extended field parsing, data publishing to Waggle, and custom data harvesting intervals.

Build and Execution
-------------------
To build and run the application, execute the following commands:

```
make
./perfmon
```

Configuration via Environment Variables
---------------------------------------
The behavior of the PerfMon library can be customized using the following optional environment variables:

- `PERFMON_ENABLE_ALL_FIELDS=1`: Enables all available fields for monitoring.
- `PERFMON_PUBLISH_DATA=1`: Activates data publishing to Waggle.
- `PERFMON_NUMBER_SAMPLES=200`: Sets the number of samples to collect.
- `PERFMON_SAMPLE_INTERVAL=0.1`: Specifies the interval between samples in seconds.
- `PERFMON_SIN_DATA_COLLECT=1`: Enables sine wave data collection.

Important Note
--------------
The environment variables `PERFMON_SIN_DATA_COLLECT` and `PERFMON_SAMPLE_INTERVAL` are mutually exclusive. `PERFMON_SIN_DATA_COLLECT` is designed for sine wave data collection, which operates on a fixed interval. In contrast, `PERFMON_SAMPLE_INTERVAL` allows for a custom sampling interval. Using both simultaneously may result in conflicts in data collection timing and behavior, as they cater to different operational modes.

These environment variables provide control over extended fields, plugin publishing, and advanced data-harvesting logic.
