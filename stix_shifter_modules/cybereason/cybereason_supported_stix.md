##### Updated on 10/25/23
## Cybereason
### Results STIX Domain Objects
* Identity
* Observed Data
<br>
### Supported STIX Operators
*Comparison AND/OR operators are inside the observation while observation AND/OR operators are between observations (square brackets).*

| STIX Operator | Data Source Operator |
|--|--|
| AND (Comparison) | AND |
| > | GreaterThan |
| >= | GreaterOrEqualsTo |
| < | LessThan |
| <= | LessOrEqualsTo |
| = | Equals |
| != | NotEquals |
| LIKE | ContainsIgnoreCase |
| IN | Equals |
| MATCHES | ContainsIgnoreCase |
| AND (Observation) | OR |
| OR (Observation) | OR |
| <br> | |
### Searchable STIX objects and properties
*The Cybereason connector can only join specific linked fields with the AND operator as defined in its [configmap](https://github.com/opencybersecurityalliance/stix-shifter/blob/develop/stix_shifter_modules/aws_athena/stix_translation/json/operators.json).*

| STIX Object and Property | Mapped Data Source Fields |
|--|--|
| **ipv4-addr**:value | Connection.localAddress, Connection.remoteAddress |
| **ipv6-addr**:value | Connection.localAddress, Connection.remoteAddress |
| **network-traffic**:src_port | Connection.localPort |
| **network-traffic**:dst_port | Connection.remotePort |
| **network-traffic**:protocols[*] | Connection.transportProtocol |
| **network-traffic**:src_ref.value | Connection.localAddress |
| **network-traffic**:dst_ref.value | Connection.remoteAddress |
| **network-traffic**:src_byte_count | Connection.aggregatedTransmittedBytesCount |
| **network-traffic**:dst_byte_count | Connection.aggregatedReceivedBytesCount, Connection.receivedBytesCount |
| **email-addr**:value | User.emailAddress, User.adMail, User.adLogonName |
| **domain-name**:value | Connection.domainName, Connection.urlDomains, Machine.domainFqdn, Machine.adDNSHostName, User.domain, User.adAssociatedDomain |
| **url**:value | Proxy.pacUrl |
| **mac-addr**:value | NetworkInterface.macAddressFormat |
| **process**:command_line | Process.commandLine, Process.decodedCommandLine |
| **process**:created | Process.creationTime, DetectionEvents.firstSeen |
| **process**:pid | Process.applicablePid |
| **process**:name | Process.elementDisplayName, Process.parentProcess, Process.execedBy |
| **process**:creator_user_ref.user_id | Process.user |
| **process**:parent_ref.pid | Process.applicablePid |
| **process**:parent_ref.name | Process.parentProcess |
| **process**:binary_ref.name | Process.elementDisplayName |
| **user-account**:user_id | Machine.adSid, Process.user, Process.hostUser, User.elementDisplayName |
| **user-account**:account_login | LogonSession.user, LogonSession.winLogonDetails |
| **user-account**:is_privileged | User.isAdmin |
| **user-account**:display_name | User.elementDisplayName, User.adDisplayName, User.adCanonicalName |
| **file**:name | File.elementDisplayName, File.originalFileName, DetectionEvents.file, Driver.file, Service.binaryFile, Service.oldBinaryFile |
| **file**:size | File.size |
| **file**:hashes.MD5 | File.md5String |
| **file**:hashes.'SHA-1' | File.sha1String |
| **file**:hashes.'SHA-256' | File.sha256String |
| **file**:parent_directory_ref.path | File.canonizedPath, File.correctedPath, File.path, FileAccessEvent.path, Service.unitFilePath |
| **directory**:path | File.canonizedPath, File.correctedPath, File.path, FileAccessEvent.path, Service.unitFilePath |
| **windows-registry-key**:key | Autorun.elementDisplayName |
| **windows-registry-key**:values[*] | Autorun.value |
| **x-cybereason-file**:company_name | File.companyName |
| **x-cybereason-file**:extension_type | File.extensionType, File.secondExtensionType |
| **x-cybereason-file**:classification_type | File.maliciousClassificationType |
| **x-cybereason-file**:description | File.fileDescription |
| **x-cybereason-file**:internal_name | File.internalName |
| **x-cybereason-file**:product_name | File.productName |
| **x-cybereason-file**:product_type | File.productType |
| **x-cybereason-file**:product_version | File.productVersion |
| **x-cybereason-file**:version | File.fileVersion, File.originalVersion |
| **x-cybereason-file**:copyright | File.legalCopyright |
| **x-cybereason-file**:build | File.privateBuild, File.specialBuild |
| **x-cybereason-file**:classification_link | File.classificationLink |
| **x-cybereason-file**:is_sign_verified | File.signatureVerifiedInternalOrExternal |
| **x-cybereason-file**:signer | File.signerInternalOrExternal, File.signer |
| **x-cybereason-file**:is_file_signed | File.signedInternalOrExternal |
| **x-cybereason-file**:registry_key | File.autorun |
| **x-cybereason-file**:quarantined_file_version | File.fileIsQuarantinedVersion |
| **x-cybereason-file**:event | File.fileAccessEvents |
| **x-cybereason-file**:downloaded_domain | File.downloadedFromDomain |
| **x-cybereason-file**:owner_machine | File.ownerMachine |
| **x-cybereason-file**:mount_point | File.mount |
| **x-cybereason-file**:mounted_as | File.mountedAs |
| **x-cybereason-file**:quarantined_action[*] | File.fileIsQuarantined |
| **x-cybereason-logonsession**:session[*] | LogonSession.clientRemoteSession, LogonSession.serverRemoteSession |
| **x-cybereason-logonsession**:user_id | LogonSession.LUID |
| **x-cybereason-logonsession**:type | LogonSession.logonType |
| **x-cybereason-logonsession**:application | LogonSession.logonApplication |
| **x-cybereason-logonsession**:name | LogonSession.elementDisplayName |
| **x-cybereason-logonsession**:machine | LogonSession.ownerMachine, LogonSession.remoteMachine, LogonSession.remoteNetworkMachine |
| **x-cybereason-logonsession**:processes | LogonSession.processes |
| **x-cybereason-logonsession**:proxies[*] | LogonSession.proxies |
| **x-cybereason-logonsession**:ip_address | LogonSession.sourceIp |
| **x-oca-asset**:name | Machine.elementDisplayName, Machine.adDisplayName, Machine.adCanonicalName |
| **x-oca-asset**:os_version | Machine.osVersionType |
| **x-oca-asset**:platform | Machine.platformArchitecture |
| **x-oca-asset**:os_type | Machine.osType |
| **x-oca-asset**:timezone | Machine.timezoneUTCOffsetMinutes |
| **x-oca-asset**:mbr_hash | Machine.mbrHashString |
| **x-oca-asset**:hosts_file | Machine.hostsFile |
| **x-oca-asset**:company | Machine.ownerOrganization |
| **x-oca-asset**:department_or_unit | Machine.adOU |
| **x-oca-asset**:removable_devices[*] | Machine.removableDevices |
| **x-oca-asset**:last_communication_with_server | Machine.timeStampSinceLastConnectionTime |
| **x-oca-asset**:activity_time | Machine.uptime |
| **x-oca-asset**:model | Machine.deviceModel |
| **x-oca-asset**:location | Machine.adLocation |
| **x-oca-asset**:network_interface[*] | Machine.networkInterfaces |
| **x-cybereason-service**:execution[*] | Service.automaticExecution |
| **x-cybereason-service**:arguments | Service.commandLineArguments |
| **x-cybereason-service**:description | Service.description |
| **x-cybereason-service**:name | Service.displayName, Service.oldServiceStartName, Service.elementDisplayName, Service.serviceStartName, Driver.service, Process.service |
| **x-cybereason-service**:driver | Service.driver |
| **x-cybereason-service**:state | Service.serviceState |
| **x-cybereason-service**:sub_state | Service.serviceSubState |
| **x-cybereason-service**:type | Service.serviceType |
| **x-cybereason-service**:start_type | Service.startType |
| **x-cybereason-service**:machine | Service.ownerMachine |
| **x-cybereason-connection**:name | Connection.elementDisplayName |
| **x-cybereason-connection**:location | Connection.remoteAddressCountryName |
| **x-cybereason-connection**:dns_query[*] | Connection.dnsQuery |
| **x-cybereason-connection**:direction | Connection.direction |
| **x-cybereason-connection**:port_type | Connection.portType |
| **x-cybereason-connection**:state | Connection.state |
| **x-cybereason-connection**:remote_address_type | Connection.remoteAddressInternalExternalLocal |
| **x-cybereason-connection**:parent_listening_socket | Connection.parent |
| **x-cybereason-connection**:classification_type | Connection.remoteAddressMaliciousClassificationType |
| **x-cybereason-connection**:machine | Connection.ownerMachine, Connection.remoteMachine |
| **x-cybereason-connection**:owner_process | Connection.ownerProcess, Connection.processName |
| **x-cybereason-process**:architecture | Process.architecture |
| **x-cybereason-process**:block_listed_domain | Process.unresolvedQueryFromBlackListDomain |
| **x-cybereason-process**:extension_type | Process.imageFileExtensionType |
| **x-cybereason-process**:integrity | Process.integrity |
| **x-cybereason-process**:thread_id | Process.tid |
| **x-cybereason-process**:openedFiles[*] | Process.openedFiles |
| **x-cybereason-process**:injection_method | Process.injectionMethod |
| **x-cybereason-process**:executed_a_file_with_malicious_hash | Process.maliciousOpenedFiles |
| **x-cybereason-process**:machine | Process.ownerMachine |
| **x-cybereason-process**:connections[*] | Process.connectionsToMaliciousDomain, Process.connectionsToBlackListDomain, Process.internalConnections, Process.connectionsToMalwareAddresses, Process.connections, Process.outgoingConnections, Process.outgoingConnectionsOfHostProcess, Process.connectionsOfHostProcess, Process.outgoingExternalConnections, Process.outgoingInternalConnections |
| **x-cybereason-process**:total_connections | Process.totalNumberOfConnections |
| **x-cybereason-process**:powershell_modules[*] | Process.powerShellModules |
| **x-cybereason-process**:loaded_modules[*] | Process.modulesFromTemp, Process.loadedModules |
| **x-cybereason-process**:product_type | Process.productType |
| **x-cybereason-process**:registry_events[*] | Process.registryEvents |
| **x-cybereason-process**:ransomware_classification_modules[*] | Process.ransomwareClassificationModules |
| **x-cybereason-process**:remote_session[*] | Process.remoteSession |
| **x-cybereason-process**:resolved_dns_domain_to_domain | Process.resolvedDnsQueriesDomainToDomain |
| **x-cybereason-process**:resolved_dns_domain_to_ip[*] | Process.resolvedDnsQueriesDomainToIp |
| **x-cybereason-process**:resolved_dns_ip_to_domain[*] | Process.resolvedDnsQueriesIpToDomain |
| **x-cybereason-process**:suspicious_domain_to_domain[*] | Process.suspiciousDnsQueryDomainToDomain |
| **x-cybereason-process**:suspicious_unresolved_dns[*] | Process.unresolvedQueryFromSuspiciousDomain |
| **x-cybereason-process**:suspicious_external_connections[*] | Process.suspiciousExternalConnections |
| **x-cybereason-process**:suspicious_internal_connections[*] | Process.suspiciousInternalConnections |
| **x-cybereason-process**:scheduled_task | Process.scheduledTask |
| **x-cybereason-process**:service | Process.service |
| **x-cybereason-process**:received_bytes | Process.totalReceivedBytes |
| **x-cybereason-process**:transmitted_bytes | Process.totalTransmittedBytes |
| **x-cybereason-process**:unresolved_domain_lookups[*] | Process.unresolvedDnsQueriesFromDomain |
| **x-cybereason-process**:unresolved_ip_lookups[*] | Process.unresolvedDnsQueriesFromIp |
| **x-cybereason-process**:unresolved_record_not_exist | Process.unresolvedRecordNotExist |
| **x-cybereason-process**:unwanted_classification_modules[*] | Process.unwantedClassificationModules |
| **x-cybereason-process**:unsigned_with_signed_version_modules[*] | Process.unsignedWithSignedVersionModules |
| **x-cybereason-process**:well_known_port_connection | Process.wellKnownPortConnections |
| **x-cybereason-process**:wmi_activities[*] | Process.wmiActivities |
| **x-cybereason-user**:total_machines | User.numberOfMachines |
| **x-cybereason-user**:privileges[*] | User.privileges |
| **x-cybereason-user**:security_id | User.sid, User.adSid |
| **x-cybereason-user**:company | User.adCompany |
| **x-cybereason-user**:country | User.adCountry, User.adTextCountry |
| **x-cybereason-user**:department | User.adDepartment |
| **x-cybereason-user**:member | User.adMemberOf |
| **x-cybereason-user**:organization | User.adOU |
| **x-cybereason-user**:organizational_unit | User.ownerOrganization |
| **x-cybereason-user**:group_id | User.adPrimaryGroupID |
| **x-cybereason-user**:sam_account_name | User.adSamAccountName |
| **x-cybereason-user**:logged_last_machine | User.ownerMachine |
| **x-cybereason-user**:process_count | User.newProcessesCount |
| **x-cybereason-driver**:name | Driver.elementDisplayName |
| **x-cybereason-driver**:service | Driver.service |
| **x-cybereason-driver**:machine | Driver.ownerMachine |
| **x-oca-event**:name | DetectionEvents.elementDisplayName, RegistryEvent.elementDisplayName, FileAccessEvent.elementDisplayName |
| **x-oca-event**:detection_event_user[*] | DetectionEvents.user |
| **x-oca-event**:file_event_user | FileAccessEvent.ownerUser |
| **x-oca-event**:connection[*] | DetectionEvents.connection |
| **x-oca-event**:detection_value | DetectionEvents.detectionValue |
| **x-oca-event**:detection_value_type | DetectionEvents.detectionValueType |
| **x-oca-event**:status | DetectionEvents.decisionStatus |
| **x-oca-event**:engine | DetectionEvents.detectionEngine |
| **x-oca-event**:script_engine | DetectionEvents.scriptEngine |
| **x-oca-event**:domain[*] | DetectionEvents.domain |
| **x-oca-event**:process | DetectionEvents.process, RegistryEvent.registryProcess, FileAccessEvent.ownerProcess |
| **x-oca-event**:collection_of_machines[*] | DetectionEvents.machine |
| **x-oca-event**:machine | DetectionEvents.ownerMachine, RegistryEvent.ownerMachine, FileAccessEvent.ownerMachine |
| **x-oca-event**:file_event_type | FileAccessEvent.fileEventType |
| **x-oca-event**:data | RegistryEvent.data |
| **x-oca-event**:detection_time | RegistryEvent.detectionTimesNumber |
| **x-oca-event**:time | RegistryEvent.firstTime, RegistryEvent.timestamp, FileAccessEvent.firstAccessTime |
| **x-oca-event**:registry_entry | RegistryEvent.registryEntry |
| **x-oca-event**:data_type | RegistryEvent.registryDataType |
| **x-oca-event**:registry_entry_type | RegistryEvent.registryEntryType |
| **x-oca-event**:operation_type | RegistryEvent.registryOperationType |
| <br> | |
### Supported STIX Objects and Properties for Query Results
| STIX Object | STIX Property | Data Source Field |
|--|--|--|
| directory | path | correctedPath |
| directory | path | canonizedPath |
| directory | path | path |
| directory | path | unitFilePath |
| <br> | | |
| domain-name | value | domainName |
| domain-name | value | urlDomains |
| domain-name | value | adAssociatedDomain |
| domain-name | value | domainFqdn |
| domain-name | value | adDNSHostName |
| <br> | | |
| email-addr | value | adLogonName |
| email-addr | value | emailAddress |
| email-addr | value | adMail |
| <br> | | |
| file | name | ownerProcess |
| file | name | elementDisplayName |
| file | hashes.SHA-1 | imageFile.sha1String |
| file | hashes.SHA-256 | imageFile.sha256String |
| file | hashes.MD5 | imageFile.md5String |
| file | name | imageFile |
| file | name | parentProcess |
| file | name | execedBy |
| file | hashes.SHA-1 | sha1String |
| file | hashes.MD5 | md5String |
| file | hashes.SHA-256 | sha256String |
| file | created | createdTime |
| file | modified | modifiedTime |
| file | size | size |
| file | parent_directory_ref | correctedPath |
| file | parent_directory_ref | canonizedPath |
| file | parent_directory_ref | path |
| file | extensions.x-cybereason-file.description | fileDescription |
| file | extensions.x-cybereason-file.version | fileVersion |
| file | extensions.x-cybereason-file-product.product_name | productName |
| file | name | originalFileName |
| file | extensions.x-cybereason-file-product.product_version | productVersion |
| file | extensions.x-cybereason-file.is_file_signed | signedInternalOrExternal |
| file | extensions.x-cybereason-file.extension_type | extensionType |
| file | extensions.x-cybereason-file.is_pefile | isPEFile |
| file | extensions.x-cybereason-file-product.copyright | legalCopyright |
| file | extensions.x-cybereason-file.is_sign_verified | signatureVerifiedInternalOrExternal |
| file | extensions.x-cybereason-file.company_name | companyName |
| file | extensions.x-cybereason-file.av_remediation_status | avRemediationStatus |
| file | extensions.x-cybereason-file.signer | signerInternalOrExternal |
| file | extensions.x-cybereason-file.autoruns | autoruns |
| file | extensions.x-cybereason-file.owner_machine | ownerMachine |
| file | extensions.x-cybereason-file.mount | mount |
| file | extensions.x-cybereason-file.registry_key | autorun |
| file | extensions.x-cybereason-file.dual_extension_evidence | dualExtensionEvidence |
| file | extensions.x-cybereason-file.hidden_file_extension_evidence | hiddenFileExtensionEvidence |
| file | extensions.x-cybereason-file.right_to_left_file_extension_evidence | rightToLeftFileExtensionEvidence |
| file | extensions.x-cybereason-file.hacking_tool_classification_evidence | hackingToolClassificationEvidence |
| file | extensions.x-cybereason-file.classification_link | classificationLink |
| file | extensions.x-cybereason-file.executed_by_process_evidence | executedByProcessEvidence |
| file | extensions.x-cybereason-file.has_autorun | hasAutorun |
| file | extensions.x-cybereason-file.is_installer_properties | isInstallerProperties |
| file | extensions.x-cybereason-file.is_from_removable_device | isFromRemovableDevice |
| file | extensions.x-cybereason-file-product.product_type | productType |
| file | extensions.x-cybereason-file.second_extension_type | secondExtensionType |
| file | extensions.x-cybereason-file.temporary_folder_evidence | temporaryFolderEvidence |
| file | extensions.x-cybereason-file.multiple_company_names_evidence | multipleCompanyNamesEvidence |
| file | extensions.x-cybereason-file.multiple_hash_for_unsigned_pe_info_evidence | multipleHashForUnsignedPeInfoEvidence |
| file | extensions.x-cybereason-file.unsigned_has_signed_version_evidence | unsignedHasSignedVersionEvidence |
| file | extensions.x-cybereason-file.classification_comment | classificationComment |
| file | extensions.x-cybereason-file.is_downloaded_from_internet | isDownloadedFromInternet |
| file | extensions.x-cybereason-file.downloaded_domain | downloadedFromDomain |
| file | extensions.x-cybereason-file.downloaded_from_ip_address | downloadedFromIpAddress |
| file | extensions.x-cybereason-file.downloaded_from_url | downloadedFromUrl |
| file | extensions.x-cybereason-file.downloaded_from_url_referrer | downloadedFromUrlReferrer |
| file | extensions.x-cybereason-file.downloaded_from_email_from | downloadedFromEmailFrom |
| file | extensions.x-cybereason-file.downloaded_from_email_message_id | downloadedFromEmailMessageId |
| file | extensions.x-cybereason-file.downloaded_from_email_subject | downloadedFromEmailSubject |
| file | extensions.x-cybereason-file.legal_trademarks | legalTrademarks |
| file | extensions.x-cybereason-file.private_build | privateBuild |
| file | extensions.x-cybereason-file.special_build | specialBuild |
| file | extensions.x-cybereason-file.internal_name | internalName |
| file | extensions.x-cybereason-file.comments | comments |
| file | extensions.x-cybereason-file.application_identifier | applicationIdentifier |
| file | name | registryProcess |
| file | name | process |
| file | name | file |
| file | created | creationTime |
| file | extensions.x-cybereason-file-event.name | elementDisplayName |
| file | extensions.x-cybereason-file-event.machine | ownerMachine |
| file | extensions.x-cybereason-file-event.file_info | fileInfo |
| file | extensions.x-cybereason-file-event.new_path | newPath |
| file | extensions.x-cybereason-file-event.is_hidden | isHidden |
| file | name | binaryFile |
| file | name | oldBinaryFile |
| file | parent_directory_ref | unitFilePath |
| <br> | | |
| ipv4-addr | value | localAddress |
| ipv4-addr | value | remoteAddress |
| ipv4-addr | extensions.x-cybereason-networkinterface.name | elementDisplayName |
| ipv4-addr | extensions.x-cybereason-networkinterface.ip_address | ipAddress |
| ipv4-addr | extensions.x-cybereason-networkinterface.owner_machine | ownerMachine |
| ipv4-addr | extensions.x-cybereason-networkinterface.dns_server | dnsServer |
| ipv4-addr | value | dhcpServer |
| ipv4-addr | resolves_to_refs | macAddressFormat |
| ipv4-addr | extensions.x-cybereason-networkinterface.interface_id | id |
| ipv4-addr | extensions.x-cybereason-networkinterface.proxies | proxies |
| ipv4-addr | value | sourceIp |
| <br> | | |
| ipv6-addr | value | localAddress |
| ipv6-addr | value | remoteAddress |
| ipv6-addr | value | dhcpServer |
| ipv6-addr | value | sourceIp |
| <br> | | |
| mac-addr | value | macAddressFormat |
| <br> | | |
| network-traffic | src_ref | localAddress |
| network-traffic | protocols | transportProtocol |
| network-traffic | dst_ref | remoteAddress |
| network-traffic | dst_port | remotePort |
| network-traffic | src_port | localPort |
| network-traffic | src_byte_count | aggregatedTransmittedBytesCount |
| network-traffic | dst_byte_count | aggregatedReceivedBytesCount |
| network-traffic | start | calculatedCreationTime |
| network-traffic | end | endTime |
| network-traffic | extensions.x-cybereason-connection.direction | direction |
| network-traffic | extensions.x-cybereason-connection.machine | ownerMachine |
| network-traffic | extensions.x-cybereason-connection.port_type | portType |
| network-traffic | extensions.x-cybereason-connection.dns_query | dnsQuery |
| network-traffic | extensions.x-cybereason-connection.port_description | portDescription |
| network-traffic | extensions.x-cybereason-connection.name | elementDisplayName |
| network-traffic | extensions.x-cybereason-connection.state | state |
| network-traffic | extensions.x-cybereason-connection.location | remoteAddressCountryName |
| network-traffic | extensions.x-cybereason-connection.remote_address_type | remoteAddressInternalExternalLocal |
| network-traffic | extensions.x-cybereason-connection.parent_listening_socket | parent |
| network-traffic | extensions.x-cybereason-connection.external_connection | isExternalConnection |
| network-traffic | extensions.x-cybereason-connection.incoming | isIncoming |
| network-traffic | extensions.x-cybereason-connection.well_known_port | isWellKnownPort |
| network-traffic | extensions.x-cybereason-connection.legit_process | isProcessLegit |
| <br> | | |
| process | name | ownerProcess |
| process | binary_ref | ownerProcess |
| process | name | elementDisplayName |
| process | binary_ref | elementDisplayName |
| process | pid | applicablePid |
| process | command_line | commandLine |
| process | created | creationTime |
| process | name | parentProcess |
| process | parent_ref | parentProcess |
| process | creator_user_ref | calculatedUser |
| process | extensions.x-cybereason-process.company_name | imageFile.companyName |
| process | extensions.x-cybereason-process.product_name | imageFile.productName |
| process | extensions.x-cybereason-process.machine | ownerMachine |
| process | extensions.x-cybereason-process.extension_type | imageFileExtensionType |
| process | extensions.x-cybereason-process.integrity | integrity |
| process | extensions.x-cybereason-process.tid | tid |
| process | extensions.x-cybereason-process.is_aggregate | isAggregate |
| process | extensions.x-cybereason-process.is_dot_net_protected | isDotNetProtected |
| process | extensions.x-cybereason-process.multiple_size_for_hash_evidence | multipleSizeForHashEvidence |
| process | extensions.x-cybereason-process.is_verified | isImageFileVerified |
| process | extensions.x-cybereason-process.multiple_company_evidence | imageFileMultipleCompanyNamesEvidence |
| process | extensions.x-cybereason-process.multiple_hash_unsigned_pe_evidence | multipleHashForUnsignedPeInfoEvidence |
| process | extensions.x-cybereason-process.multiple_name_hash_evidence | multipleNameForHashEvidence |
| process | extensions.x-cybereason-process.unknown_evidence | unknownEvidence |
| process | extensions.x-cybereason-process.rare_pe_mismatch_evidence | rareHasPeMismatchEvidence |
| process | extensions.x-cybereason-process.signed_internal_or_external | imageFile.signedInternalOrExternal |
| process | extensions.x-cybereason-process.unknown_unsigned_sign_company | unknownUnsignedBySigningCompany |
| process | extensions.x-cybereason-process.unsigned_evidence | imageFileUnsignedEvidence |
| process | extensions.x-cybereason-process.unsigned_has_signed_version | imageFileUnsignedHasSignedVersionEvidence |
| process | extensions.x-cybereason-process.signer_internal_or_external | imageFile.signerInternalOrExternal |
| process | extensions.x-cybereason-process.architecture | architecture |
| process | extensions.x-cybereason-process.command_line_contains_temp | commandLineContainsTempEvidence |
| process | extensions.x-cybereason-process.has_children | hasChildren |
| process | extensions.x-cybereason-process.has_visible_windows | hasVisibleWindows |
| process | extensions.x-cybereason-process.has_windows | hasWindows |
| process | extensions.x-cybereason-process.is_installer | isInstaller |
| process | extensions.x-cybereason-process.is_identified_product | isIdentifiedProduct |
| process | extensions.x-cybereason-process.has_module_temp_evidence | hasModuleFromTempEvidence |
| process | extensions.x-cybereason-process.non_executable_extension | nonExecutableExtensionEvidence |
| process | extensions.x-cybereason-process.is_not_shell_runner | isNotShellRunner |
| process | extensions.x-cybereason-process.running_from_temp | runningFromTempEvidence |
| process | extensions.x-cybereason-process.shell_elevated_privileges | shellWithElevatedPrivilegesEvidence |
| process | extensions.x-cybereason-process.system_user_evidence | systemUserEvidence |
| process | extensions.x-cybereason-process.unresolved_record_not_exists | multipleUnresolvedRecordNotExistsEvidence |
| process | extensions.x-cybereason-process.non_default_resolver | hasNonDefaultResolverEvidence |
| process | extensions.x-cybereason-process.parent_process_not_admin | parentProcessNotAdminUserEvidence |
| process | extensions.x-cybereason-process.parent_process_removable_device | parentProcessFromRemovableDeviceEvidence |
| process | extensions.x-cybereason-process.autorun | autorun |
| process | extensions.x-cybereason-process.children_created_thread | childrenCreatedByThread |
| process | extensions.x-cybereason-process.elevated_privilege_children | elevatedPrivilegeChildren |
| process | extensions.x-cybereason-process.hacker_tool_children | hackerToolChildren |
| process | extensions.x-cybereason-process.host_process | hostProcess |
| process | extensions.x-cybereason-process.hosted_children | hostedChildren |
| process | extensions.x-cybereason-process.injected_children | injectedChildren |
| process | extensions.x-cybereason-process.loaded_modules | loadedModules |
| process | extensions.x-cybereason-process.logon_session | logonSession |
| process | extensions.x-cybereason-process.remote_session | remoteSession |
| process | extensions.x-cybereason-process.service | service |
| process | name | execedBy |
| process | extensions.x-cybereason-process.low_ttl_dns_queries | lowTtlDnsQueries |
| process | extensions.x-cybereason-process.non_default_resolver_queries | nonDefaultResolverQueries |
| process | extensions.x-cybereason-process.resolved_dns_domain_to_domain | resolvedDnsQueriesDomainToDomain |
| process | extensions.x-cybereason-process.resolved_dns_domain_to_ip | resolvedDnsQueriesDomainToIp |
| process | extensions.x-cybereason-process.resolved_dns_ip_to_domain | resolvedDnsQueriesIpToDomain |
| process | extensions.x-cybereason-process.unresolved_record_not_exist | unresolvedRecordNotExist |
| process | extensions.x-cybereason-process.unresolved_domain_lookups | unresolvedDnsQueriesFromDomain |
| process | extensions.x-cybereason-process.unresolved_ip_lookups | unresolvedDnsQueriesFromIp |
| process | extensions.x-cybereason-process.modules_not_db_list | modulesNotInLoaderDbList |
| process | extensions.x-cybereason-process.modules_from_temp | modulesFromTemp |
| process | extensions.x-cybereason-process.unsigned_signed_version_module | unsignedWithSignedVersionModules |
| process | extensions.x-cybereason-process.unwanted_classification_modules | unwantedClassificationModules |
| process | extensions.x-cybereason-process.external_connection_evidence | hasRareExternalConnectionEvidence |
| process | extensions.x-cybereason-process.remote_address_evidence | hasRareRemoteAddressEvidence |
| process | extensions.x-cybereason-process.high_volume_external_outgoing_connection | hasAbsoluteHighVolumeExternalOutgoingConnectionEvidence |
| process | extensions.x-cybereason-process.high_data_volume_transmitted_by_unknown_process | highDataVolumeTransmittedByUnknownProcess |
| process | extensions.x-cybereason-process.high_number_internal_outgoing_embryonic_connections_evidence | absoluteHighNumberOfInternalOutgoingEmbryonicConnectionsEvidence |
| process | extensions.x-cybereason-process.low_ttl_dns_query_evidence | hasLowTtlDnsQueryEvidence |
| process | extensions.x-cybereason-process.high_unresolved_to_resolved_rate_evidence | highUnresolvedToResolvedRateEvidence |
| process | extensions.x-cybereason-process.many_unresolved_record_not_exists_evidence | manyUnresolvedRecordNotExistsEvidence |
| process | extensions.x-cybereason-process.child_known_hacker_tool_evidence | hasChildKnownHackerToolEvidence |
| process | extensions.x-cybereason-process.hacking_tool_non_tool_runner_evidence | hackingToolOfNonToolRunnerEvidence |
| process | extensions.x-cybereason-process.rare_child_process_known_hacker_tool_evidence | hasRareChildProcessKnownHackerToolEvidence |
| process | extensions.x-cybereason-process.deleted_parent_process_evidence | deletedParentProcessEvidence |
| process | extensions.x-cybereason-process.dual_extension_name_evidence | dualExtensionNameEvidence |
| process | extensions.x-cybereason-process.hidden_file_extension_evidence | hiddenFileExtensionEvidence |
| process | extensions.x-cybereason-process.right_to_left_file_extension_evidence | rightToLeftFileExtensionEvidence |
| process | extensions.x-cybereason-process.screen_saver_with_children_evidence | screenSaverWithChildrenEvidence |
| process | extensions.x-cybereason-process.has_pe_floating_code_evidence | hasPeFloatingCodeEvidence |
| process | extensions.x-cybereason-process.has_section_mismatch_evidence | hasSectionMismatchEvidence |
| process | extensions.x-cybereason-process.detected_injected_evidence | detectedInjectedEvidence |
| process | extensions.x-cybereason-process.detected_injecting_evidence | detectedInjectingEvidence |
| process | extensions.x-cybereason-process.detected_injecting_to_protected_process_evidence | detectedInjectingToProtectedProcessEvidence |
| process | extensions.x-cybereason-process.has_injected_children | hasInjectedChildren |
| process | extensions.x-cybereason-process.hosting_injected_thread_evidence | hostingInjectedThreadEvidence |
| process | extensions.x-cybereason-process.injected_protected_process_evidence | injectedProtectedProcessEvidence |
| process | extensions.x-cybereason-process.injection_method | injectionMethod |
| process | extensions.x-cybereason-process.is_hosting_injected_thread | isHostingInjectedThread |
| process | extensions.x-cybereason-process.high_internal_outgoing_evidence | highInternalOutgoingEmbryonicConnectionRateEvidence |
| process | extensions.x-cybereason-process.high_number_of_internal_connections_evidence | highNumberOfInternalConnectionsEvidence |
| process | extensions.x-cybereason-process.new_processes_above_threshold_evidence | newProcessesAboveThresholdEvidence |
| process | extensions.x-cybereason-process.has_rare_internal_connection_evidence | hasRareInternalConnectionEvidence |
| process | extensions.x-cybereason-process.elevating_privileges_to_child_evidence | elevatingPrivilegesToChildEvidence |
| process | extensions.x-cybereason-process.parent_process_not_system_user_evidence | parentProcessNotSystemUserEvidence |
| process | extensions.x-cybereason-process.privilege_escalation_evidence | privilegeEscalationEvidence |
| process | extensions.x-cybereason-process.first_execution_of_downloaded_process_evidence | firstExecutionOfDownloadedProcessEvidence |
| process | extensions.x-cybereason-process.has_autorun | hasAutorun |
| process | extensions.x-cybereason-process.new_process_evidence | newProcessEvidence |
| process | extensions.x-cybereason-process.ransomware_auto_remediation_suspended | ransomwareAutoRemediationSuspended |
| process | extensions.x-cybereason-process.total_num_of_instances | totalNumOfInstances |
| process | extensions.x-cybereason-process.last_minute_num_of_instances | lastMinuteNumOfInstances |
| process | extensions.x-cybereason-process.last_seen_time_stamp | lastSeenTimeStamp |
| process | extensions.x-cybereason-process.wmi_query_strings | wmiQueryStrings |
| process | extensions.x-cybereason-process.is_executed_by_wmi | isExectuedByWmi |
| process | extensions.x-cybereason-process.absolute_high_number_of_internal_connections | absoluteHighNumberOfInternalConnectionsEvidence |
| process | extensions.x-cybereason-process.is_downloaded_from_internet | imageFile.isDownloadedFromInternet |
| process | extensions.x-cybereason-process.downloaded_from_domain | imageFile.downloadedFromDomain |
| process | extensions.x-cybereason-process.downloaded_from_ip_address | imageFile.downloadedFromIpAddress |
| process | extensions.x-cybereason-process.user_id | imageFile.downloadedFromUrl |
| process | extensions.x-cybereason-process.downloaded_from_url_referrer | imageFile.downloadedFromUrlReferrer |
| process | extensions.x-cybereason-process.downloaded_from_email_from | imageFile.downloadedFromEmailFrom |
| process | extensions.x-cybereason-process.downloaded_from_email_message_id | imageFile.downloadedFromEmailMessageId |
| process | extensions.x-cybereason-process.downloaded_from_email_subject | imageFile.downloadedFromEmailSubject |
| process | extensions.x-cybereason-process.rpc_requests | rpcRequests |
| process | extensions.x-cybereason-process.icon_base64 | iconBase64 |
| process | extensions.x-cybereason-process.matched_white_list_rule_ids | matchedWhiteListRuleIds |
| process | name | registryProcess |
| process | binary_ref | registryProcess |
| process | name | process |
| process | binary_ref | process |
| process | created | process.creationTime |
| process | created | firstSeen |
| process | created | firstAccessTime |
| <br> | | |
| url | value | pacUrl |
| <br> | | |
| user-account | user_id | calculatedUser |
| user-account | user_id | hostUser |
| user-account | user_id | elementDisplayName |
| user-account | display_name | elementDisplayName |
| user-account | user_id | username |
| user-account | is_privileged | isAdmin |
| user-account | account_created | adCreated |
| user-account | extensions.x-cybereason-user.domain | domain |
| user-account | extensions.x-cybereason-user.organizational_unit | ownerOrganization.name |
| user-account | extensions.x-cybereason-user.last_logged_machine | ownerMachine |
| user-account | extensions.x-cybereason-user.is_local_system | isLocalSystem |
| user-account | extensions.x-cybereason-user.department | adDepartment |
| user-account | extensions.x-cybereason-user.country | adCountry |
| user-account | extensions.x-cybereason-user.company | adCompany |
| user-account | extensions.x-cybereason-user.total_machines | numberOfMachines |
| user-account | extensions.x-cybereason-user.password_age_days | passwordAgeDays |
| user-account | extensions.x-cybereason-user.privileges | privileges |
| user-account | extensions.x-cybereason-user.comment | comment |
| user-account | extensions.x-cybereason-user.canonical_name | adCanonicalName |
| user-account | display_name | adDisplayName |
| user-account | extensions.x-cybereason-user.member_of | adMemberOf |
| user-account | extensions.x-cybereason-user.organization | adOU |
| user-account | extensions.x-cybereason-user.group_id | adPrimaryGroupID |
| user-account | extensions.x-cybereason-user.sam_account_name | adSamAccountName |
| user-account | extensions.x-cybereason-user.title | adTitle |
| user-account | extensions.x-cybereason-user.sid | sid |
| user-account | extensions.x-cybereason-user.has_power_tool | hasPowerTool |
| user-account | extensions.x-cybereason-user.unusual_process_ext_connection | hasRareProcessWithExternalConnections |
| user-account | user_id | user |
| user-account | user_id | adSid |
| user-account | account_login | user |
| <br> | | |
| windows-registry-key | extensions.x-cybereason-registry-event.name | elementDisplayName |
| windows-registry-key | extensions.x-cybereason-registry-event.registry_operation_type | registryOperationType |
| windows-registry-key | extensions.x-cybereason-registry-event.first_seen | firstTime |
| windows-registry-key | extensions.x-cybereason-registry-event.last_seen | timestamp |
| windows-registry-key | extensions.x-cybereason-registry-event.detection_time_number | detectionTimesNumber |
| windows-registry-key | key | registryEntry |
| windows-registry-key | extensions.x-cybereason-registry-event.owner_machine | ownerMachine |
| windows-registry-key | key | elementDisplayName |
| windows-registry-key | extensions.x-cybereason-registryentry.value | value |
| windows-registry-key | extensions.x-cybereason-registryentry.depend_in_file | dependInFile |
| windows-registry-key | extensions.x-cybereason-registryentry.owner_machine | ownerMachine |
| windows-registry-key | extensions.x-cybereason-registryentry.is_pointing_to_tmp | isPointingToTemp |
| windows-registry-key | extensions.x-cybereason-registryentry.registry_entry | registryEntry |
| windows-registry-key | extensions.x-cybereason-registryentry.end_time | endTime |
| <br> | | |
| x-cybereason-connection | has_external_connection | hasExternalConnection |
| x-cybereason-connection | external_connection_known_port | hasExternalConnectionToWellKnownPortEvidence |
| x-cybereason-connection | has_incoming_connection | hasIncomingConnection |
| x-cybereason-connection | has_internal_connection | hasInternalConnection |
| x-cybereason-connection | mail_connection_for_non_mail_process | hasMailConnectionForNonMailProcessEvidence |
| x-cybereason-connection | has_listening_connection | hasListeningConnection |
| x-cybereason-connection | has_outgoing_connection | hasOutgoingConnection |
| x-cybereason-connection | has_unresolved_dns_query | hasUnresolvedDnsQueriesFromDomain |
| x-cybereason-connection | connections | connections |
| x-cybereason-connection | external_connections | externalConnections |
| x-cybereason-connection | absolute_high_vol_external_connections | absoluteHighVolumeExternalConnections |
| x-cybereason-connection | incoming_connections | incomingConnections |
| x-cybereason-connection | incoming_external_connections | incomingExternalConnections |
| x-cybereason-connection | incoming_internal_connections | incomingInternalConnections |
| x-cybereason-connection | internal_connections | internalConnections |
| x-cybereason-connection | listening_connections | listeningConnections |
| x-cybereason-connection | local_connections | localConnections |
| x-cybereason-connection | mail_connections | mailConnections |
| x-cybereason-connection | outgoing_connections | outgoingConnections |
| x-cybereason-connection | outgoing_external_connections | outgoingExternalConnections |
| x-cybereason-connection | outgoing_internal_connections | outgoingInternalConnections |
| x-cybereason-connection | well_known_port_connections | wellKnownPortConnections |
| <br> | | |
| x-cybereason-detectionevent | process_name | process.calculatedName |
| x-cybereason-detectionevent | user | process.calculatedUser |
| x-cybereason-detectionevent | end_time | process.endTime |
| x-cybereason-detectionevent | classification_type | process.imageFile.maliciousClassificationType |
| <br> | | |
| x-cybereason-driver | file_ref | file |
| x-cybereason-driver | name | elementDisplayName |
| x-cybereason-driver | machine | ownerMachine |
| x-cybereason-driver | service | service |
| x-cybereason-driver | end_time | endTime |
| x-cybereason-driver | new_driver_evidence | newDriverEvidence |
| <br> | | |
| x-cybereason-logonsession | name | elementDisplayName |
| x-cybereason-logonsession | processes | processes |
| x-cybereason-logonsession | owner_machine | ownerMachine |
| x-cybereason-logonsession | remote_machine | remoteMachine |
| x-cybereason-logonsession | logon_type | logonType |
| x-cybereason-logonsession | creation_time | creationTime |
| x-cybereason-logonsession | last_seen | lastSeenTime |
| x-cybereason-logonsession | application | logonApplication |
| x-cybereason-logonsession | end_time | endTime |
| <br> | | |
| x-cybereason-malops | malops | hasMalops |
| x-cybereason-malops | suspicions | hasSuspicions |
| x-cybereason-malops | related_to_malop | relatedToMalop |
| x-cybereason-malops | malware_process | isProcessMalware |
| x-cybereason-malops | has_malops | hasMalops |
| x-cybereason-malops | has_suspicions | hasSuspicions |
| x-cybereason-malops | malicious_tool_suspicion | knownMaliciousToolSuspicion |
| x-cybereason-malops | malware_suspicion | knownMalwareSuspicion |
| x-cybereason-malops | unwanted_suspicion | knownUnwantedSuspicion |
| x-cybereason-malops | malicious_hash_evidence | isMaliciousByHashEvidence |
| x-cybereason-malops | unwanted_module_suspicion | unwantedModuleSuspicion |
| x-cybereason-malops | has_classification | hasClassification |
| x-cybereason-malops | non_shell_runner_suspicion | shellOfNonShellRunnerSuspicion |
| x-cybereason-malops | parent_process_not_hierarchy_suspicion | parentProcessNotMatchHierarchySuspicion |
| x-cybereason-malops | connections_to_malicious_domain | connectionsToMaliciousDomain |
| x-cybereason-malops | connections_to_malware_addresses | connectionsToMalwareAddresses |
| x-cybereason-malops | absolute_high_vol_malicious_address_connections | absoluteHighVolumeMaliciousAddressConnections |
| x-cybereason-malops | suspicious_external_connections | suspiciousExternalConnections |
| x-cybereason-malops | suspicious_internal_connections | suspiciousInternalConnections |
| x-cybereason-malops | suspicious_domain_to_domain | suspiciousDnsQueryDomainToDomain |
| x-cybereason-malops | suspicious_unresolved_dns | unresolvedQueryFromSuspiciousDomain |
| x-cybereason-malops | dns_query_from_suspicious_domain | dnsQueryFromSuspiciousDomain |
| x-cybereason-malops | dns_query_to_suspicious_domain | dnsQueryToSuspiciousDomain |
| x-cybereason-malops | malicious_tool_classification_modules | maliciousToolClassificationModules |
| x-cybereason-malops | malware_classification_modules | malwareClassificationModules |
| x-cybereason-malops | access_to_malware_address_infected_process | accessToMalwareAddressInfectedProcess |
| x-cybereason-malops | connecting_to_bad_reputation_address_suspicion | connectingToBadReputationAddressSuspicion |
| x-cybereason-malops | has_malicious_connection_evidence | hasMaliciousConnectionEvidence |
| x-cybereason-malops | has_suspicious_external_connection_suspicion | hasSuspiciousExternalConnectionSuspicion |
| x-cybereason-malops | high_number_of_external_connections_suspicion | highNumberOfExternalConnectionsSuspicion |
| x-cybereason-malops | non_default_resolver_suspicion | nonDefaultResolverSuspicion |
| x-cybereason-malops | suspicious_mail_connections | suspiciousMailConnections |
| x-cybereason-malops | access_to_malware_address | accessToMalwareAddressByUnknownProcess |
| x-cybereason-malops | high_volume_connection_to_malicious_address | hasAbsoluteHighVolumeConnectionToMaliciousAddressEvidence |
| x-cybereason-malops | high_data_transmitted_suspicion | highDataTransmittedSuspicion |
| x-cybereason-malops | high_data_volume_transmitted_to_malicious_address_suspicion | highDataVolumeTransmittedToMaliciousAddressSuspicion |
| x-cybereason-malops | dga_suspicion | dgaSuspicion |
| x-cybereason-malops | hacking_tool_non_tool_runner_suspicion | hackingToolOfNonToolRunnerSuspicion |
| x-cybereason-malops | malicious_tool_module_suspicion | maliciousToolModuleSuspicion |
| x-cybereason-malops | malware_module_suspicion | malwareModuleSuspicion |
| x-cybereason-malops | suspicions_screen_saver_evidence | suspicionsScreenSaverEvidence |
| x-cybereason-malops | malicious_injecting_code_suspicion | maliciousInjectingCodeSuspicion |
| x-cybereason-malops | injected_code_suspicion | maliciousInjectedCodeSuspicion |
| x-cybereason-malops | pe_execution_suspicion | maliciousPeExecutionSuspicion |
| x-cybereason-malops | suspicious_internal_connection | hasSuspiciousInternalConnectionEvidence |
| x-cybereason-malops | marked_for_prevention | markedForPrevention |
| x-cybereason-malops | scanning_process_suspicion | scanningProcessSuspicion |
| x-cybereason-malops | malicious_classification_type | imageFile.maliciousClassificationType |
| x-cybereason-malops | execution_prevented | executionPrevented |
| x-cybereason-malops | is_white_list_classification | isWhiteListClassification |
| x-cybereason-malops | classification_type | maliciousClassificationType |
| x-cybereason-malops | classification_blocking | classificationBlocking |
| x-cybereason-malops | has_malicious_process | hasMaliciousProcess |
| x-cybereason-malops | has_suspicious_process | hasSuspiciousProcess |
| x-cybereason-malops | running_malicious_process_evidence | runningMaliciousProcessEvidence |
| x-cybereason-malops | is_isolated | isIsolated |
| x-cybereason-malops | suspicious_process_or_file | isSuspiciousOrHasSuspiciousProcessOrFile |
| x-cybereason-malops | malicious_tools | maliciousTools |
| x-cybereason-malops | malicious_processes | maliciousProcesses |
| x-cybereason-malops | suspicious_processes | suspiciousProcesses |
| <br> | | |
| x-cybereason-proxy | name | elementDisplayName |
| x-cybereason-proxy | discovery_type | discoveryType |
| x-cybereason-proxy | host | host |
| x-cybereason-proxy | ip_address | ipAddress |
| x-cybereason-proxy | pac_url | pacUrl |
| x-cybereason-proxy | port | port |
| <br> | | |
| x-cybereason-service | name | elementDisplayName |
| x-cybereason-service | file_ref | binaryFile |
| x-cybereason-service | file_ref | oldBinaryFile |
| x-cybereason-service | machine | ownerMachine |
| x-cybereason-service | start_name | serviceStartName |
| x-cybereason-service | arguments | commandLineArguments |
| x-cybereason-service | description | description |
| x-cybereason-service | display_name | displayName |
| x-cybereason-service | end_time | endTime |
| x-cybereason-service | is_active | isActive |
| x-cybereason-service | start_type | startType |
| x-cybereason-service | state | serviceState |
| x-cybereason-service | sub_state | serviceSubState |
| x-cybereason-service | auto_restart_service | isAutoRestartService |
| x-cybereason-service | new_service_evidence | newServiceEvidence |
| x-cybereason-service | rare_service_evidence | rareServiceEvidence |
| x-cybereason-service | type | serviceType |
| x-cybereason-service | driver | driver |
| <br> | | |
| x-oca-asset | user_ref | username |
| x-oca-asset | active_probe_connected | ownerMachine.isActiveProbeConnected |
| x-oca-asset | os_version | ownerMachine.osVersionType |
| x-oca-asset | name | elementDisplayName |
| x-oca-asset | mount_points | mountPoints |
| x-oca-asset | processes | processes |
| x-oca-asset | services | services |
| x-oca-asset | logon_sessions | logonSessions |
| x-oca-asset | has_removable_device | hasRemovableDevice |
| x-oca-asset | timezone | timezoneUTCOffsetMinutes |
| x-oca-asset | version_type | osVersionType |
| x-oca-asset | platform | platformArchitecture |
| x-oca-asset | mbr_hash | mbrHashString |
| x-oca-asset | os_type | osType |
| x-oca-asset | owner_organization | ownerOrganization |
| x-oca-asset | pylum_id | pylumId |
| x-oca-asset | department_or_unit | adOU |
| x-oca-asset | ad_organization | adOrganization |
| x-oca-asset | name | adCanonicalName |
| x-oca-asset | ad_company | adCompany |
| x-oca-asset | department | adDepartment |
| x-oca-asset | name | adDisplayName |
| x-oca-asset | location | adLocation |
| x-oca-asset | machine_role | adMachineRole |
| x-oca-asset | description | adDescription |
| x-oca-asset | free_disk_space | freeDiskSpace |
| x-oca-asset | total_disk_space | totalDiskSpace |
| x-oca-asset | free_memory | freeMemory |
| x-oca-asset | total_memory | totalMemory |
| x-oca-asset | cpu_count | cpuCount |
| x-oca-asset | is_laptop | isLaptop |
| x-oca-asset | model | deviceModel |
| x-oca-asset | is_active_probe_connected | isActiveProbeConnected |
| x-oca-asset | activity_time | uptime |
| x-oca-asset | last_communication_with_server | timeStampSinceLastConnectionTime |
| <br> | | |
| x-oca-event | network_ref | transportProtocol |
| x-oca-event | file_ref | elementDisplayName |
| x-oca-event | name | elementDisplayName |
| x-oca-event | user_ref | user |
| x-oca-event | engine | detectionEngine |
| x-oca-event | status | decisionStatus |
| x-oca-event | detection_value | detectionValue |
| x-oca-event | machine | ownerMachine |
| x-oca-event | detection_value_type | detectionValueType |
| x-oca-event | file_event_type | fileEventType |
| x-oca-event | src_ref | sourceIp |
| <br> | | |
| x-windows-registry-value-type | data_type | registryDataType |
| x-windows-registry-value-type | data | data |
| <br> | | |
