# SF-Crimes-Analytics-Kafka-Spark-Integration

# Answers to questions

1. How did changing values on the SparkSession property parameters affect the throughput and latency of the data?

	I analysed the inputRowsPerSecond SparkSession parameter to increase the throughput of the Spark trigger to process large number of input rows.

2. What were the 2-3 most efficient SparkSession property key/value pairs? Through testing multiple variations on values, how can you tell these were the most optimal?

	I tested followin properties to see the most optimal configuration of Spark streaming for this analysis:
		1. Name: maxOffsetsPerTrigger, Purpose:  limit the rate when fetching data, Tested values: 10 20 50 60 85 and 100. Optimal value: 100.
		2. Name: maxRatePerPartition, Purpose: to increase the input rate per partition, Tested values: 10 20 30 40 50 60 70 80 90 100, Optimal value: 100
