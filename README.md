# Assignment-12.1

1.Explain the need of Flume.

Ans.Apache Flume is a tool used to collect, aggregate and transport large amounts of streaming data like log files, events, etc., from a number of different sources to a centralized data store like HDFS,HBase.It is a highly distributed, reliable, and configurable tool.
The need of flume can be understood by the following example-A company has tons of services running on multiple servers. And lots of data (logs) are produced by them, now we need to analyze them altogether. In order to process that logs, we need a reliable, scalable, extensible and manageable distributed data collection service which can perform flow of unstructured data (logs) from one location to another where they will be processed (say in HDFS). Apache flume is an open source data collection service for moving the data from source to destination.Based on streaming data flows, it has a simple and flexible architecture. It is highly fault tolerant and robust and with tunable reliability mechanisms for fail-over and recovery. Flume allows data collection in batch as well as streaming mode.


2.Explain the working of Flume and its components in brief.

Ans.Apache Flume consists of the following components:

•	Event – a singular unit of data that is transported by Flume (typically a single log entry)
•	Source – the entity through which data enters into Flume. Sources either actively poll for data or passively wait for data to be     delivered to them. A variety of sources allow data to be collected, such as log4j logs and syslogs.
•	Sink – the entity that delivers the data to the destination. A variety of sinks allow data to be streamed to a range of destinations. One example is the HDFS sink that writes events to HDFS.
•	Channel – the conduit between the Source and the Sink. Sources ingest events into the channel and the sinks drain the channel.
•	Agent – any physical Java virtual machine running Flume. It is a collection of sources, sinks and channels.
•	Client – produces and transmits the Event to the Source operating within the Agent

Working of Flume:
A flow in Flume starts from the Client (Web Server). The Client transmits the event to a Source operating within the Agent. The Source receiving this event then delivers it to one or more Channels. These Channels are drained by one or more Sinks operating within the same Agent. Channels allow decoupling of ingestion rate from drain rate using the familiar producer-consumer mode of data exchange. When spikes in client side activity cause data to be generated faster than what the provisioned capacity on the destination can handle, the channel size increases. This allows sources to continue normal operation for the duration of the spike. Flume agents can be chained together by connecting the sink of one agent to the source of another agent. This enables the creation of complex dataflow topologies.
