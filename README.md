[comment]: # "Auto-generated SOAR connector documentation"
# Endace

Publisher: Endace Technology Ltd  
Connector Version: 2\.0\.1  
Product Vendor: Endace  
Product Name: Endace  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 4\.9\.39220  

This app integrates with the Endace Packet Capture device to implement investigative actions

### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a Endace asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**server** |  required  | string | Server IP/Hostname
**verify\_cert** |  optional  | boolean | Verify Server Certificate
**username** |  required  | string | Username
**password** |  required  | password | Password
**max\_pcap\_size** |  required  | numeric | Maximum pcap size in bytes \(0 = no max\)

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration  
[get pcap](#action-get-pcap) - Download a PCAP into the vault  
[delete pcap](#action-delete-pcap) - Delete the specified PCAP  
[get status](#action-get-status) - Get the status of a previously executed query  
[run query](#action-run-query) - Run a query to create a PCAP  

## action: 'test connectivity'
Validate the asset configuration for connectivity using supplied configuration

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'get pcap'
Download a PCAP into the vault

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**pcap\_id** |  required  | PCAP ID | string |  `pcap id` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.pcap\_id | string |  `pcap id` 
action\_result\.data\.\*\.status\.datamine\.status\.bytesTotal | numeric | 
action\_result\.data\.\*\.status\.datamine\.status\.name | string | 
action\_result\.data\.\*\.status\.datamine\.status\.bytesRead | numeric | 
action\_result\.data\.\*\.status\.datamine\.status\.bytesWritten | numeric | 
action\_result\.data\.\*\.status\.datamine\.status\.destinationFormat | string | 
action\_result\.data\.\*\.status\.datamine\.status\.state | string | 
action\_result\.data\.\*\.status\.datamine\.status\.progressPercentage | numeric | 
action\_result\.data\.\*\.status\.datamine\.status\.type | string | 
action\_result\.data\.\*\.status\.datamine\.status\.description | string | 
action\_result\.data\.\*\.status\.datamine\.username | string | 
action\_result\.data\.\*\.status\.datamine\.timeCreated | numeric | 
action\_result\.data\.\*\.status\.datamine\.links\.\*\.href | string |  `url` 
action\_result\.data\.\*\.status\.datamine\.links\.\*\.name | string | 
action\_result\.data\.\*\.status\.datamine\.links\.\*\.method | string | 
action\_result\.data\.\*\.status\.datamine\.datamineID | string |  `pcap id` 
action\_result\.data\.\*\.status\.datamine\.timeCreated3339 | string |  `rfc3339` 
action\_result\.data\.\*\.status\.datamine\.rotationFiles | string | 
action\_result\.data\.\*\.status\.datamine\.deduplicate | boolean | 
action\_result\.data\.\*\.status\.datamine\.endTime3339 | string | 
action\_result\.data\.\*\.status\.datamine\.startTime | numeric | 
action\_result\.data\.\*\.status\.datamine\.endTime | numeric | 
action\_result\.data\.\*\.status\.datamine\.startTime3339 | string | 
action\_result\.data\.\*\.vault\.size | numeric |  `file size` 
action\_result\.data\.\*\.vault\.vault\_id | string |  `sha1`  `vault id` 
action\_result\.data\.\*\.vault\.filename | string |  `file name` 
action\_result\.data\.\*\.vault\.contains | string | 
action\_result\.data\.\*\.vault\.app\_run\_id | numeric | 
action\_result\.data\.\*\.vault\.action | string | 
action\_result\.data\.\*\.vault\.type | string | 
action\_result\.data\.\*\.status\.datamine\.status\.bytesTotalToWriteEstimate | numeric | 
action\_result\.data\.\*\.status\.datamine\.status\.timeStarted3339 | string |  `rfc3339` 
action\_result\.data\.\*\.status\.datamine\.status\.stateUpdateTime | numeric | 
action\_result\.data\.\*\.status\.datamine\.status\.stateUpdateTime3339 | string | 
action\_result\.data\.\*\.status\.datamine\.status\.timeStarted | numeric | 
action\_result\.data\.\*\.status\.datamine\.filterAppsInclude | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.state | string | 
action\_result\.summary\.vault\_id | string |  `sha1`  `vault id` 
action\_result\.summary\.file\_availability | boolean | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'delete pcap'
Delete the specified PCAP

Type: **correct**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**pcap\_id** |  required  | PCAP ID | string |  `pcap id` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.pcap\_id | string |  `pcap id` 
action\_result\.data\.\*\.messages\.\*\.type | string | 
action\_result\.data\.\*\.messages\.\*\.name | string | 
action\_result\.data\.\*\.messages\.\*\.description | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.name | string | 
action\_result\.summary\.type | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'get status'
Get the status of a previously executed query

Type: **investigate**  
Read only: **True**

Request the status of a query and when complete it will include a link for downloading the PCAP\.

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**pcap\_id** |  required  | PCAP ID | string |  `pcap id` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.pcap\_id | string |  `pcap id` 
action\_result\.data\.\*\.datamine\.status\.bytesTotal | numeric | 
action\_result\.data\.\*\.datamine\.status\.name | string | 
action\_result\.data\.\*\.datamine\.status\.bytesRead | numeric | 
action\_result\.data\.\*\.datamine\.status\.bytesWritten | numeric | 
action\_result\.data\.\*\.datamine\.status\.destinationFormat | string | 
action\_result\.data\.\*\.datamine\.status\.state | string | 
action\_result\.data\.\*\.datamine\.status\.progressPercentage | numeric | 
action\_result\.data\.\*\.datamine\.status\.type | string | 
action\_result\.data\.\*\.datamine\.status\.description | string | 
action\_result\.data\.\*\.datamine\.username | string | 
action\_result\.data\.\*\.datamine\.timeCreated | numeric | 
action\_result\.data\.\*\.datamine\.links\.\*\.href | string |  `url` 
action\_result\.data\.\*\.datamine\.links\.\*\.name | string | 
action\_result\.data\.\*\.datamine\.links\.\*\.method | string | 
action\_result\.data\.\*\.datamine\.datamineID | string |  `pcap id` 
action\_result\.data\.\*\.datamine\.timeCreated3339 | string |  `rfc3339` 
action\_result\.data\.\*\.datamine\.rotationFiles | string | 
action\_result\.data\.\*\.datamine\.deduplicate | boolean | 
action\_result\.data\.\*\.datamine\.endTime3339 | string | 
action\_result\.data\.\*\.datamine\.startTime | numeric | 
action\_result\.data\.\*\.datamine\.endTime | numeric | 
action\_result\.data\.\*\.datamine\.startTime3339 | string | 
action\_result\.data\.\*\.datamine\.status\.bytesTotalToWriteEstimate | numeric | 
action\_result\.data\.\*\.datamine\.status\.timeStarted3339 | string |  `rfc3339` 
action\_result\.data\.\*\.datamine\.status\.stateUpdateTime | numeric | 
action\_result\.data\.\*\.datamine\.status\.stateUpdateTime3339 | string | 
action\_result\.data\.\*\.datamine\.status\.timeStarted | numeric | 
action\_result\.data\.\*\.datamine\.filterAppsInclude | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.state | string | 
action\_result\.summary\.progress | numeric | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'run query'
Run a query to create a PCAP

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**time** |  optional  | The time of interest, in RFC\-3339 format | string |  `rfc3339` 
**start\_time** |  optional  | The start time of the data, in RFC\-3339 format | string |  `rfc3339` 
**end\_time** |  optional  | The end time of the data, in RFC\-3339 format | string |  `rfc3339` 
**span\_before** |  optional  | The span, in seconds, before the value specified by the 'time' parameter | numeric | 
**span\_after** |  optional  | The span, in seconds, after the value specified by the 'time' parameter | numeric | 
**host1** |  required  | The flow initiator, expressed as <IP Address>\[/<CIDR prefix>\] | string |  `ip`  `endace ip network` 
**host2** |  required  | The flow target, expressed as <IP Address>\[/<CIDR prefix>\]\. Use 0\.0\.0\.0/0 for directionless IP of host2 | string |  `ip`  `endace ip network` 
**port1** |  optional  | The flow initiator port number | numeric |  `port` 
**port2** |  optional  | The flow target port number | numeric |  `port` 
**protocol** |  required  | The name of the IP protocol; for example, 'udp', 'tcp' | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.span\_after | string | 
action\_result\.parameter\.time | string |  `rfc3339` 
action\_result\.parameter\.span\_before | string | 
action\_result\.parameter\.port2 | string |  `port` 
action\_result\.parameter\.port1 | string |  `port` 
action\_result\.parameter\.protocol | string | 
action\_result\.parameter\.host1 | string |  `ip`  `endace ip network` 
action\_result\.parameter\.start\_time | string |  `rfc3339` 
action\_result\.parameter\.host2 | string |  `ip`  `endace ip network` 
action\_result\.parameter\.end\_time | string |  `rfc3339` 
action\_result\.data\.\*\.datamine\.messages\.\*\.type | string | 
action\_result\.data\.\*\.datamine\.messages\.\*\.name | string | 
action\_result\.data\.\*\.datamine\.messages\.\*\.description | string | 
action\_result\.data\.\*\.datamine\.results\.\*\.datamineID | string |  `pcap id` 
action\_result\.data\.\*\.datamine\.links\.\*\.href | string |  `url` 
action\_result\.data\.\*\.datamine\.links\.\*\.name | string | 
action\_result\.data\.\*\.datamine\.links\.\*\.method | string | 
action\_result\.data\.\*\.flow\.meta\.protocol | string | 
action\_result\.data\.\*\.flow\.meta\.startTime | numeric | 
action\_result\.data\.\*\.flow\.meta\.port2 | boolean | 
action\_result\.data\.\*\.flow\.meta\.endTime3339 | string |  `rfc3339` 
action\_result\.data\.\*\.flow\.meta\.host2 | string |  `ip`  `endace ip network` 
action\_result\.data\.\*\.flow\.meta\.host1 | string |  `ip`  `endace ip network` 
action\_result\.data\.\*\.flow\.meta\.endTime | numeric | 
action\_result\.data\.\*\.flow\.meta\.startTime3339 | string |  `rfc3339` 
action\_result\.data\.\*\.flow\.meta\.port1 | boolean | 
action\_result\.data\.\*\.flow\.results\.total\.flowPacketCount | numeric | 
action\_result\.data\.\*\.flow\.results\.total\.totalByteCount | numeric | 
action\_result\.data\.\*\.flow\.results\.total\.links\.\*\.fields\.\*\.type | string | 
action\_result\.data\.\*\.flow\.results\.total\.links\.\*\.fields\.\*\.name | string | 
action\_result\.data\.\*\.flow\.results\.total\.links\.\*\.fields\.\*\.value | string | 
action\_result\.data\.\*\.flow\.results\.total\.links\.\*\.href | string |  `url` 
action\_result\.data\.\*\.flow\.results\.total\.links\.\*\.name | string | 
action\_result\.data\.\*\.flow\.results\.total\.links\.\*\.method | string | 
action\_result\.data\.\*\.flow\.results\.total\.flowByteCount | numeric | 
action\_result\.data\.\*\.flow\.results\.total\.totalPacketCount | numeric | 
action\_result\.data\.\*\.flow\.results\.rotationFiles\.\*\.rotationFileID | string | 
action\_result\.data\.\*\.flow\.results\.rotationFiles\.\*\.links\.\*\.fields\.\*\.type | string | 
action\_result\.data\.\*\.flow\.results\.rotationFiles\.\*\.links\.\*\.fields\.\*\.name | string | 
action\_result\.data\.\*\.flow\.results\.rotationFiles\.\*\.links\.\*\.fields\.\*\.value | string | 
action\_result\.data\.\*\.flow\.results\.rotationFiles\.\*\.links\.\*\.href | string |  `url` 
action\_result\.data\.\*\.flow\.results\.rotationFiles\.\*\.links\.\*\.name | string | 
action\_result\.data\.\*\.flow\.results\.rotationFiles\.\*\.links\.\*\.method | string | 
action\_result\.data\.\*\.flow\.results\.rotationFiles\.\*\.rotationFileName | string | 
action\_result\.data\.\*\.flow\.results\.rotationFiles\.\*\.flowPacketCount | numeric | 
action\_result\.data\.\*\.flow\.results\.rotationFiles\.\*\.probe | string | 
action\_result\.data\.\*\.flow\.results\.rotationFiles\.\*\.flowByteCount | numeric | 
action\_result\.data\.\*\.flow\.results\.rotationFiles\.\*\.totalPacketCount | numeric | 
action\_result\.data\.\*\.flow\.results\.rotationFiles\.\*\.totalByteCount | numeric | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.flow\_byte\_count | numeric | 
action\_result\.summary\.message\_type | string | 
action\_result\.summary\.pcap\_id | string |  `pcap id` 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 