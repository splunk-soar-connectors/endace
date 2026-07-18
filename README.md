# Endace

Publisher: Endace Technology Ltd <br>
Connector Version: 2.0.0 <br>
Product Vendor: Endace <br>
Product Name: Endace <br>
Minimum Product Version: 4.9.39220

This app integrates with the Endace Packet Capture device to implement investigative actions

### Configuration variables

This table lists the configuration variables required to operate Endace. These variables are specified when configuring a Endace asset in Splunk SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**server** | required | string | Server IP/Hostname |
**verify_cert** | optional | boolean | Verify Server Certificate |
**username** | required | string | Username |
**password** | required | password | Password |
**max_pcap_size** | required | numeric | Maximum pcap size in bytes (0 = no max) |

### Supported Actions

[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration <br>
[get pcap](#action-get-pcap) - Download a PCAP into the vault <br>
[delete pcap](#action-delete-pcap) - Delete the specified PCAP <br>
[get status](#action-get-status) - Get the status of a previously executed query <br>
[run query](#action-run-query) - Run a query to create a PCAP

## action: 'test connectivity'

Validate the asset configuration for connectivity using supplied configuration

Type: **test** <br>
Read only: **True**

#### Action Parameters

No parameters are required for this action

#### Action Output

No Output

## action: 'get pcap'

Download a PCAP into the vault

Type: **investigate** <br>
Read only: **True**

#### Action Parameters

PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**pcap_id** | required | PCAP ID | string | `pcap id` |

#### Action Output

DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.parameter.pcap_id | string | `pcap id` | f411b785-2507-4320-bbf3-83d3ecf69290 |
action_result.data.\*.status.datamine.status.bytesTotal | numeric | | 1979711440 |
action_result.data.\*.status.datamine.status.name | string | | |
action_result.data.\*.status.datamine.status.bytesRead | numeric | | 536842225 |
action_result.data.\*.status.datamine.status.bytesWritten | numeric | | 69255168 |
action_result.data.\*.status.datamine.status.destinationFormat | string | | pcap erf |
action_result.data.\*.status.datamine.status.state | string | | COMPLETED RUNNING |
action_result.data.\*.status.datamine.status.progressPercentage | numeric | | 0.079115472451523 |
action_result.data.\*.status.datamine.status.type | string | | Download |
action_result.data.\*.status.datamine.status.description | string | | Completed Running |
action_result.data.\*.status.datamine.username | string | | |
action_result.data.\*.status.datamine.timeCreated | numeric | | 1402559070 |
action_result.data.\*.status.datamine.links.\*.href | string | `url` | http://endace-probe-101/api/v5/datamines/f411b785-2507-4320-bbf3-83d3ecf69290 |
action_result.data.\*.status.datamine.links.\*.name | string | | getDatamine |
action_result.data.\*.status.datamine.links.\*.method | string | | GET |
action_result.data.\*.status.datamine.datamineID | string | `pcap id` | f411b785-2507-4320-bbf3-83d3ecf69290 |
action_result.data.\*.status.datamine.timeCreated3339 | string | `rfc3339` | 2014-06-12T07:44:30.989Z |
action_result.data.\*.status.datamine.rotationFiles | string | | beda7946-7bca-5756-9040-f37b481434a0 |
action_result.data.\*.status.datamine.deduplicate | boolean | | True False |
action_result.data.\*.status.datamine.endTime3339 | string | | 2014-06-10T03:37:09.500Z |
action_result.data.\*.status.datamine.startTime | numeric | | 1402367830 |
action_result.data.\*.status.datamine.endTime | numeric | | 1402371429 |
action_result.data.\*.status.datamine.startTime3339 | string | | 2014-06-10T02:37:09.500Z |
action_result.data.\*.vault.size | numeric | `file size` | 15799219 |
action_result.data.\*.vault.vault_id | string | `sha1` `vault id` | 2fd4e1c67a2d28fced849ee1bb76e7391b93eb12 |
action_result.data.\*.vault.filename | string | `file name` | 71a28c03-37fb-45f2-a63a-7167c4c7efa4.pcap |
action_result.data.\*.vault.contains | string | | pcap |
action_result.data.\*.vault.app_run_id | numeric | | 2340 |
action_result.data.\*.vault.action | string | | get pcap |
action_result.data.\*.vault.type | string | | pcap |
action_result.data.\*.status.datamine.status.bytesTotalToWriteEstimate | numeric | | 875368191 |
action_result.data.\*.status.datamine.status.timeStarted3339 | string | `rfc3339` | 2014-06-17T05:07:36.049Z |
action_result.data.\*.status.datamine.status.stateUpdateTime | numeric | | 1402981659 |
action_result.data.\*.status.datamine.status.stateUpdateTime3339 | string | | 2014-06-17T05:07:39.896Z |
action_result.data.\*.status.datamine.status.timeStarted | numeric | | 1402981656 |
action_result.data.\*.status.datamine.filterAppsInclude | string | | HTTP |
action_result.status | string | | success failed |
action_result.message | string | | PCAP downloaded to Vault: 2fd4e1c67a2d28fced849ee1bb76e7391b93eb12. Error downloading file. State: RUNNING |
action_result.summary.state | string | | COMPLETED RUNNING |
action_result.summary.vault_id | string | `sha1` `vault id` | 2fd4e1c67a2d28fced849ee1bb76e7391b93eb12 |
action_result.summary.file_availability | boolean | | True False |
summary.total_objects | numeric | | 1 |
summary.total_objects_successful | numeric | | 1 |

## action: 'delete pcap'

Delete the specified PCAP

Type: **correct** <br>
Read only: **False**

#### Action Parameters

PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**pcap_id** | required | PCAP ID | string | `pcap id` |

#### Action Output

DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.parameter.pcap_id | string | `pcap id` | 1dad7408-1a14-4266-901a-6c07aad2c1a8 |
action_result.data.\*.messages.\*.type | string | | success |
action_result.data.\*.messages.\*.name | string | | datamineDeleted |
action_result.data.\*.messages.\*.description | string | | Datamine 1dad7408-1a14-4266-901a-6c07aad2c1a8 deleted |
action_result.status | string | | success failed |
action_result.message | string | | Datamine 1dad7408-1a14-4266-901a-6c07aad2c1a8 deleted |
action_result.summary.name | string | | datamineDeleted |
action_result.summary.type | string | | success |
summary.total_objects | numeric | | 1 |
summary.total_objects_successful | numeric | | 1 |

## action: 'get status'

Get the status of a previously executed query

Type: **investigate** <br>
Read only: **True**

Request the status of a query and when complete it will include a link for downloading the PCAP.

#### Action Parameters

PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**pcap_id** | required | PCAP ID | string | `pcap id` |

#### Action Output

DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.parameter.pcap_id | string | `pcap id` | 17147e4b-e73e-4888-9599-f38d43e814f0 |
action_result.data.\*.datamine.status.bytesTotal | numeric | | 1979711440 |
action_result.data.\*.datamine.status.name | string | | download |
action_result.data.\*.datamine.status.bytesRead | numeric | | 1073676191 |
action_result.data.\*.datamine.status.bytesWritten | numeric | | 302485752 |
action_result.data.\*.datamine.status.destinationFormat | string | | pcap erf |
action_result.data.\*.datamine.status.state | string | | COMPLETED RUNNING |
action_result.data.\*.datamine.status.progressPercentage | numeric | | 0.34555259730702 |
action_result.data.\*.datamine.status.type | string | | Download |
action_result.data.\*.datamine.status.description | string | | Completed Running |
action_result.data.\*.datamine.username | string | | |
action_result.data.\*.datamine.timeCreated | numeric | | 1402981924 |
action_result.data.\*.datamine.links.\*.href | string | `url` | http://endace-probe-101/api/v5/datamines/17147e4b-e73e-4888-9599-f38d43e814f0 |
action_result.data.\*.datamine.links.\*.name | string | | getDatamine |
action_result.data.\*.datamine.links.\*.method | string | | GET |
action_result.data.\*.datamine.datamineID | string | `pcap id` | 17147e4b-e73e-4888-9599-f38d43e814f0 |
action_result.data.\*.datamine.timeCreated3339 | string | `rfc3339` | 2014-06-17T05:12:04.802Z |
action_result.data.\*.datamine.rotationFiles | string | | beda7946-7bca-5756-9040-f37b481434a0 |
action_result.data.\*.datamine.deduplicate | boolean | | True False |
action_result.data.\*.datamine.endTime3339 | string | | 2014-06-10T03:37:09.500Z |
action_result.data.\*.datamine.startTime | numeric | | 1402367830 |
action_result.data.\*.datamine.endTime | numeric | | 1402371429 |
action_result.data.\*.datamine.startTime3339 | string | | 2014-06-10T02:37:09.500Z |
action_result.data.\*.datamine.status.bytesTotalToWriteEstimate | numeric | | 875368191 |
action_result.data.\*.datamine.status.timeStarted3339 | string | `rfc3339` | 2014-06-17T05:12:04.808Z |
action_result.data.\*.datamine.status.stateUpdateTime | numeric | | 1402981929 |
action_result.data.\*.datamine.status.stateUpdateTime3339 | string | | 2014-06-17T05:12:09.909Z |
action_result.data.\*.datamine.status.timeStarted | numeric | | 1402981924 |
action_result.data.\*.datamine.filterAppsInclude | string | | HTTP |
action_result.status | string | | success failed |
action_result.message | string | | COMPLETED RUNNING; 35% complete |
action_result.summary.state | string | | COMPLETED RUNNING |
action_result.summary.progress | numeric | | 0.34555259730702 |
summary.total_objects | numeric | | 1 |
summary.total_objects_successful | numeric | | 1 |

## action: 'run query'

Run a query to create a PCAP

Type: **generic** <br>
Read only: **False**

#### Action Parameters

PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**time** | optional | The time of interest, in RFC-3339 format | string | `rfc3339` |
**start_time** | optional | The start time of the data, in RFC-3339 format | string | `rfc3339` |
**end_time** | optional | The end time of the data, in RFC-3339 format | string | `rfc3339` |
**span_before** | optional | The span, in seconds, before the value specified by the 'time' parameter | numeric | |
**span_after** | optional | The span, in seconds, after the value specified by the 'time' parameter | numeric | |
**host1** | required | The flow initiator, expressed as <IP Address>\[/<CIDR prefix>\] | string | `ip` `endace ip network` |
**host2** | required | The flow target, expressed as <IP Address>\[/<CIDR prefix>\]. Use 0.0.0.0/0 for directionless IP of host2 | string | `ip` `endace ip network` |
**port1** | optional | The flow initiator port number | numeric | `port` |
**port2** | optional | The flow target port number | numeric | `port` |
**protocol** | required | The name of the IP protocol; for example, 'udp', 'tcp' | string | |

#### Action Output

DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.parameter.span_after | string | | 30 |
action_result.parameter.time | string | `rfc3339` | 2014-06-10T02:43:23.1234Z |
action_result.parameter.span_before | string | | 30 |
action_result.parameter.port2 | string | `port` | 80 |
action_result.parameter.port1 | string | `port` | 80 |
action_result.parameter.protocol | string | | tcp udp |
action_result.parameter.host1 | string | `ip` `endace ip network` | 10.0.0.1 10.0.0.0/8 |
action_result.parameter.start_time | string | `rfc3339` | 2014-06-10T02:18:42.1234Z |
action_result.parameter.host2 | string | `ip` `endace ip network` | 10.0.0.5 0.0.0.0/0 |
action_result.parameter.end_time | string | `rfc3339` | 2014-06-10T02:43:23.1234Z |
action_result.data.\*.datamine.messages.\*.type | string | | success |
action_result.data.\*.datamine.messages.\*.name | string | | datamineCreated |
action_result.data.\*.datamine.messages.\*.description | string | | Datamine 983c5fd4-ea17-4e3a-b11f-78bc281644f9 created |
action_result.data.\*.datamine.results.\*.datamineID | string | `pcap id` | 983c5fd4-ea17-4e3a-b11f-78bc281644f9 |
action_result.data.\*.datamine.links.\*.href | string | `url` | http://endace-probe-101/api/v5/datamines/983c5fd4-ea17-4e3a-b11f-78bc281644f9 |
action_result.data.\*.datamine.links.\*.name | string | | getDatamine |
action_result.data.\*.datamine.links.\*.method | string | | GET |
action_result.data.\*.flow.meta.protocol | string | | tcp |
action_result.data.\*.flow.meta.startTime | numeric | | 1402366722 |
action_result.data.\*.flow.meta.port2 | boolean | | True False |
action_result.data.\*.flow.meta.endTime3339 | string | `rfc3339` | 2014-06-10T02:43:23.1234Z |
action_result.data.\*.flow.meta.host2 | string | `ip` `endace ip network` | 10.0.0.5 0.0.0.0/0 |
action_result.data.\*.flow.meta.host1 | string | `ip` `endace ip network` | 10.0.0.1 0.0.0.0/0 |
action_result.data.\*.flow.meta.endTime | numeric | | 1402368203 |
action_result.data.\*.flow.meta.startTime3339 | string | `rfc3339` | 2014-06-10T02:18:42.1234Z |
action_result.data.\*.flow.meta.port1 | boolean | | True False |
action_result.data.\*.flow.results.total.flowPacketCount | numeric | | 5288 |
action_result.data.\*.flow.results.total.totalByteCount | numeric | | 76367448 |
action_result.data.\*.flow.results.total.links.\*.fields.\*.type | string | | String |
action_result.data.\*.flow.results.total.links.\*.fields.\*.name | string | | rotationFiles |
action_result.data.\*.flow.results.total.links.\*.fields.\*.value | string | | localhost:data,localhost:capture |
action_result.data.\*.flow.results.total.links.\*.href | string | `url` | http://endace-probe-101/api/v5/datamines |
action_result.data.\*.flow.results.total.links.\*.name | string | | createDatamine |
action_result.data.\*.flow.results.total.links.\*.method | string | | POST |
action_result.data.\*.flow.results.total.flowByteCount | numeric | | 1977002 |
action_result.data.\*.flow.results.total.totalPacketCount | numeric | | 74980 |
action_result.data.\*.flow.results.rotationFiles.\*.rotationFileID | string | | 0f73e00a-92fa-cbb2-72d5-b5e3419b6b37 |
action_result.data.\*.flow.results.rotationFiles.\*.links.\*.fields.\*.type | string | | String |
action_result.data.\*.flow.results.rotationFiles.\*.links.\*.fields.\*.name | string | | rotationFiles |
action_result.data.\*.flow.results.rotationFiles.\*.links.\*.fields.\*.value | string | | localhost:data |
action_result.data.\*.flow.results.rotationFiles.\*.links.\*.href | string | `url` | http://endace-probe-101/api/v5/datamines |
action_result.data.\*.flow.results.rotationFiles.\*.links.\*.name | string | | createDatamine |
action_result.data.\*.flow.results.rotationFiles.\*.links.\*.method | string | | POST |
action_result.data.\*.flow.results.rotationFiles.\*.rotationFileName | string | | data |
action_result.data.\*.flow.results.rotationFiles.\*.flowPacketCount | numeric | | 349 |
action_result.data.\*.flow.results.rotationFiles.\*.probe | string | | localhost |
action_result.data.\*.flow.results.rotationFiles.\*.flowByteCount | numeric | | 127034 |
action_result.data.\*.flow.results.rotationFiles.\*.totalPacketCount | numeric | | 4623 |
action_result.data.\*.flow.results.rotationFiles.\*.totalByteCount | numeric | | 3777138 |
action_result.status | string | | success failed |
action_result.message | string | | Datamine 983c5fd4-ea17-4e3a-b11f-78bc281644f9 created |
action_result.summary.flow_byte_count | numeric | | 1977002 |
action_result.summary.message_type | string | | success |
action_result.summary.pcap_id | string | `pcap id` | 983c5fd4-ea17-4e3a-b11f-78bc281644f9 |
summary.total_objects | numeric | | 1 |
summary.total_objects_successful | numeric | | 1 |

______________________________________________________________________

Auto-generated Splunk SOAR Connector documentation.

Copyright 2026 Splunk Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing,
software distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and limitations under the License.
