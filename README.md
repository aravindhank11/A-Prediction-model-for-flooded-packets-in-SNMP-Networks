# A-Prediction-model-for-flooded-packets-in-SNMP-Networks
## (IEEE - ICCS 2018)
A Prediction Model to classify the SNMP Dataset into flood and normal packets by means of ensemble of classifiers using Machine Learning Techniques.

## Network Topology Used for Creating Cloud Security dataset

The cloud security dataset is built using open source cloud. It is free software and you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or any later version.

DDoS Attack datasets are generated using virtual instances running in a cloud security testbed.  OpenStack private cloud is deployed in the cloud security testbed along with virtual instances running on them. The virtual instances are acting as zombies from different public and private networks of Open Stack private cloud. The attack generation is done using virtual instances as zombies and the data collection is performed at the victim with network monitoring software. The DDoS flood attacks that are considered in the experiment are ICMP flood, TCPSYN flood, TCPSYN-ACK flood, UDP flood and Land Flood. The attack duration is half an hour and the dump files collected are in the excel format. 

## About the Dataset
**SNMP dataset.xls**- The dataset contains the SNMP MIB variables during attack and normal mode. The records have class labels based on the attack/normal behavior such as ICMP_Flood, LAND_Flood, TCPSYN_Flood, TCPSYNACK_Flood, UDP_Flood, ICMP_Normal, LAND_Normal, TCPSYN_Normal, TCPSYNACK_Normal and UDP_Normal. The total number of records in the dataset is 2421.

**The SNMP parameters that are used for data collection are as follows:**
**SNMP Parameters:**
      These parameters include all the protocols like IP, ICMP, UDP and TCP OID’s where the following metrics can be obtained:
ipForwarding: The indication of whether this entity is acting as an IP router in respect to the forwarding of datagrams received by, but not addressed to, this entity. IP routers forward datagrams. IP hosts do not (except those source-routed via the host).
- ipDefaultTTL: The default value inserted into the Time-To-Live field of the IP header of datagrams originated at this entity, whenever a TTL value is not supplied by the transport layer protocol.	
- ipInReceives:  The total number of input datagrams received from interfaces, including those received in error."	
- ipInHdrErrors: The number of input datagrams discarded due to errors in their IP headers, including bad checksums, version number mismatch, other format errors, time-to-live exceeded, errors discovered in processing their IP options, etc."	
- ipInAddrErrors: The number of input datagrams discarded because the IP address in their IP header's destination field was not a valid address to be received at this entity. This count includes invalid addresses (e.g., 0.0.0.0) and addresses of unsupported Classes (e.g., Class E). For entities which are not IP routers and therefore do not forward datagrams, this counter includes datagrams discarded because the destination address was not a local address."	
- ipForwDatagrams: The number of input datagrams for which this entity was not their final IP destination, as a result of which an attempt was made to find a route to forward them to that final destination. In entities which do not act as IP routers, this counter will include only those packets which were Source-Routed via this entity, and the Source-Route option processing was successful	
- ipInUnknownProtos: The number of locally-addressed datagrams received successfully but discarded because of an unknown or unsupported protocol."ecause of an unknown or unsupported protocol.	
- ipInDiscards: The number of input IP datagrams for which no problems were encountered to prevent their continued processing, but which were discarded (e.g., for lack of buffer space). Note that this counter does not include any datagrams discarded while awaiting re-assembly.
- ipInDelivers: The total number of input datagrams successfully delivered to IP user-protocols (including ICMP).
- ipOutRequests: The total number of IP datagrams which local IP user- protocols (including ICMP) supplied to IP in requests for transmission. Note that this counter does not include any datagrams counted in ipForwDatagrams.
- ipOutDiscards: The number of output IP datagrams for which no problem was encountered to prevent their transmission to their destination, but which were discarded (e.g., for lack of buffer space). Note that this counter would include datagrams counted in ipForwDatagrams if any such packets met this (discretionary) discard criterion.
- ipOutNoRoutes: The number of IP datagrams discarded because no route could be found to transmit them to their destination. Note that this counter includes any packets counted in ipForwDatagrams which meet this 'no-route' criterion. Note that this includes any datagrams which a host cannot route because all of its default routers are down.
- ipReasmTimeout: The maximum number of seconds which received fragments are held while they are awaiting reassembly at this entity
- ip_ReasmReqds: Number of Internet Protocol (IP) fragments received which needed to be reassembled at this entity.
- ipReasmOKs: Number of Internet Protocol (IP) datagrams successfully re-assembled.
- ip_ReasmFails: Number of failures detected by the IP reassembly algorithm (for whatever reason: timed out, errors, etc). Note that this is not necessarily a count of discarded IP fragments since some algorithms (notably the algorithm in RFC 815) can lose track of the number of fragments by combining them as they are received.
- ip_FragOKs: Number of Internet Protocol (IP) datagrams that have been successfully fragmented at this entity.
- ip_FragFails: The number of Internet Protocol (IP) datagrams that have been discarded because they needed to be fragmented at this entity but could not be, e.g. because their Don't Fragment flag was set.
- ip_FragCreates: Number of Internet Protocol (IP) datagram fragments that have been generated as a result of fragmentation at this entity.
- ip_RoutingDiscards: Number of routing entries which were chosen to be discarded even though they are valid.
- tcp_RtoAlgorithm: Algorithm used to determine the timeout value used for retransmitting unacknowledged octets.-
- tcp_RtoMin: The minimum value permitted by a TCP implementation for the retransmission timeout, measured in milliseconds. More refined semantics for objects of this type depend upon the algorithm used to determine the retransmission timeout. In particular, when the timeout algorithm is rsre(3), an object of this type has the semantics of the LBOUND quantity described in RFC 793.
- tcp_RtoMax: The maximum value permitted by a TCP implementation for the retransmission timeout, measured in milliseconds. More refined semantics for objects of this type depend upon the algorithm used to determine the retransmission timeout. In particular, when the timeout algorithm is rsre(3), an object of this type has the semantics of the UBOUND quantity described in RFC 793.
- tcp_MaxConn: The limit on the total number of TCP connections the entity can support. In entities where the maximum number of connections is dynamic, this object should contain the value -1.
- tcp_ActiveOpens: The number of times TCP connections have made a direct transition to the SYN-SENT state from the CLOSED state.
- tcp_PassiveOpens: The number of times TCP connections have made a direct transition to the SYN-RCVD state from the LISTEN state.
- tcp_AttemptFails: The number of times TCP connections have made a direct transition to the CLOSED state from either the SYN-SENT state or the SYN-RCVD state, plus the number of times TCP connections have made a direct transition to the LISTEN state from the SYN-RCVD state.
- tcp_EstabResets: The number of times TCP connections have made a direct transition to the CLOSED state from either the ESTABLISHED state or the CLOSE-WAIT state.
- tcp_CurrEstab: The number of TCP connections for which the current state is either ESTABLISHED or CLOSE WAIT.
- tcp_InSegs: The total number of segments received, including those received in error. This count includes segments received on currently established connections.
- tcp_OutSegs: The total number of segments sent, including those on current connections but excluding those containing only retransmitted octets.
- tcp_RetransSegs: The total number of segments retransmitted – that is, the number of TCP segments transmitted containing one or more previously transmitted octets.
- tcp_InErrs: The total number of segments received in error (e.g., bad TCP checksums).
- tcp_OutRsts: The number of TCP segments sent containing the RST flag.
- udp_InDatagrams: The total number of UDP datagrams delivered to UDP users.
- udp_NoPorts: The total number of received UDP datagrams for which there was no application at the destination port.
- udp_InErrors: The number of received UDP datagrams that could not be delivered for reasons other than the lack of an application at the destination port.
- udp_OutDatagrams: The total number of UDP datagrams sent from this entity.
- icmp_InMsgs: The total number of ICMP messages which the entity received. Note that this counter includes all those counted by icmpInErrors.
- icmp_InErrors: The number of ICMP messages which the entity received but determined as having ICMP-specific errors (bad ICMP checksums, bad length, etc.
- icmp_inDestUnreachs: The number of ICMP Destination Unreachable messages received.
- icmp_InTimeExcds: The number of ICMP Time Exceeded messages received.
- icmp_InParmProbs: The number of ICMP Parameter Problem messages received.
- icmp_InSrcQuenchs: The number of ICMP Source Quench messages received.
- icmp_InRedirects: The number of ICMP Redirect messages received.
- icmp_InEchos: The number of ICMP Echo (request) messages received.
- icmp_InEchoReps: The number of ICMP Echo Reply messages received.
- icmp_InTimestamps: The number of ICMP Timestamp (request) messages received.
- icmp_InTimestampReps: The number of ICMP Timestamp Reply messages received.
- icmp_InAddrMasks: The number of ICMP Address Mask Request messages received.
- icmp_InAddrMaskReps: The number of ICMP Address Mask Reply messages received.
- icmp_OutMsgs: The total number of ICMP messages which this entity attempted to send. Note that this counter includes all those counted by icmpOutErrors.
- icmp_OutErrors: Number of ICMP messages which this entity did not send due to problems discovered within ICMP such as a lack of buffers. This value should not include errors discovered outside the ICMP layer such as the inability of IP to route the resultant datagram. In some implementations there may be no types of error which contribute to this counter's value.
- icmp_OutDestUnreachs: The number of ICMP Destination Unreachable messages sent.
- icmp_OutTimeExcds: The number of ICMP Time Exceeded messages sent.
- icmp_OutParmProbs: The number of ICMP Parameter Problem messages sent.
- icmp_OutSrcQuenchs: The number of ICMP Source Quench messages sent.
- icmp_OutRedirects: The number of ICMP Redirect messages sent. For a host, this object will always be zero, since hosts do not send redirects.
- icmp_OutEchos: The number of ICMP Echo (request) messages sent.
- icmp_OutEchoReps: The number of ICMP Echo Reply messages sent.
- icmp_OutTimestamps: The number of ICMP Timestamp (request) messages sent.
- icmp_OutTimestampReps: The number of ICMP Timestamp Reply messages sent.
- icmp_OutAddrMasks: The number of ICMP Address Mask Request messages sent.
- icmp_OutAddrMaskReps: The number of ICMP Address Mask Reply messages sent.

## Pre-Processing
1. The Database is a time-series collection of packets and so it becomes more intuitive and logical to analyse a group of packets instead of one at a time.
2. 5 consecutive packets of the same group of Flood/Normal are thus grouped for analysis.
3. Parameters of description of message packets that were same for all the packets were dropped in order to enhance parametric reduction for learning.
4. The difference of parameters in message packets of the same group is considered to be the transformed parameters for learning as it proved to have better correlation with the target Class.

## Machine Learning
1. The dataset was subjected to a process of learning where in the prediction accuracy was determined for various well-known models.
2. To avoid over-fitting of data, care was taken and to make sure the results are consistent for all out-of-sample data points, a 10 fold-cross validation score was carried on.
3. The results of the Analysis is well summmarised with appropriate tables, graphs and insights in the Research Paper available in the Repository.
