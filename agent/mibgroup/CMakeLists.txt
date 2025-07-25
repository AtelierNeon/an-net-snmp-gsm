## Add include directories
include_directories (
    ${PROJECT_SOURCE_DIR}/agent)

## Component - netsnmpmibs
set (NETSNMP_NETSNMPMIBSLIB_NAME
    netsnmpmibs)
set (NETSNMP_NETSNMPMIBSLIB_SRCS
    mibII/setSerialNo.c
    mibII/snmp_mib.c
    mibII/sysORTable.c
    mibII/system_mib.c
    mibII/updates.c
    mibII/vacm_context.c
    mibII/vacm_conf.c
    mibII/vacm_vars.c
    disman/event/mteEvent.c
    disman/event/mteEventConf.c
    disman/event/mteEventNotificationTable.c
    disman/event/mteEventSetTable.c
    disman/event/mteEventTable.c
    disman/event/mteObjects.c
    disman/event/mteObjectsConf.c
    disman/event/mteObjectsTable.c
    disman/event/mteScalars.c
    disman/event/mteTrigger.c
    disman/event/mteTriggerBooleanTable.c
    disman/event/mteTriggerConf.c
    disman/event/mteTriggerDeltaTable.c
    disman/event/mteTriggerExistenceTable.c
    disman/event/mteTriggerTable.c
    disman/event/mteTriggerThresholdTable.c
    examples/example.c
    examples/ucdDemoPublic.c
    ucd-snmp/dlmod.c
    ucd-snmp/errormib.c
    ucd-snmp/extensible.c
    ucd-snmp/file.c)
set (NETSNMP_NETSNMPMIBSLIB_SRCS
    ${NETSNMP_NETSNMPMIBSLIB_SRCS}
    ucd-snmp/loadave.c
    ucd-snmp/pass.c
    ucd-snmp/pass_common.c
    ucd-snmp/pass_persist.c
    ucd-snmp/proc.c
    ucd-snmp/proxy.c
    ucd-snmp/versioninfo.c
    snmpv3/snmpEngine.c
    snmpv3/snmpMPDStats.c
    snmpv3/usmConf.c
    snmpv3/usmStats.c
    snmpv3/usmUser.c
    notification/snmpNotifyFilterProfileTable.c
    notification/snmpNotifyFilterProfileTable_data.c
    snmp-notification-mib/snmpNotifyFilterTable/snmpNotifyFilterTable.c
    snmp-notification-mib/snmpNotifyFilterTable/snmpNotifyFilterTable_data_access.c
    snmp-notification-mib/snmpNotifyFilterTable/snmpNotifyFilterTable_data_storage.c
    snmp-notification-mib/snmpNotifyFilterTable/snmpNotifyFilterTable_interface.c
    notification/snmpNotifyTable.c
    notification/snmpNotifyTable_data.c
    target/snmpTargetAddrEntry.c
    target/snmpTargetAddrEntry_data.c
    target/snmpTargetParamsEntry.c
    target/snmpTargetParamsEntry_data.c
    target/target.c
    target/target_counters.c
    agentx/agentx_config.c
    agentx/client.c
    agentx/master.c
    agentx/master_admin.c
    agentx/protocol.c
    agentx/subagent.c
    agent/extend.c
    agent/nsCache.c
    agent/nsDebug.c
    agent/nsLogging.c
    agent/nsModuleTable.c
    agent/nsTransactionTable.c
    utilities/execute.c
    utilities/iquery.c
    utilities/override.c
    util_funcs/header_generic.c
    util_funcs/header_simple_table.c
    header_complex.c
    ../helpers/all_helpers.c
    ../helpers/baby_steps.c
    ../helpers/bulk_to_next.c
    ../helpers/cache_handler.c
    ../helpers/debug_handler.c
    ../helpers/instance.c
    ../helpers/mode_end_call.c
    ../helpers/multiplexer.c
    ../helpers/null.c
    ../helpers/old_api.c
    ../helpers/read_only.c
    ../helpers/row_merge.c
    ../helpers/scalar.c
    ../helpers/scalar_group.c
    ../helpers/serialize.c
    ../helpers/snmp_get_statistic.c
    ../helpers/stash_cache.c
    ../helpers/stash_to_next.c
    ../helpers/table.c
    ../helpers/table_array.c
    ../helpers/table_container.c
    ../helpers/table_data.c
    ../helpers/table_dataset.c
    ../helpers/table_iterator.c
    ../helpers/table_tdata.c
    ../helpers/watcher.c
    ../mib_modules.c
    util_funcs.c
    util_funcs/Exit.c
    util_funcs/restart.c
    smux/smux.c)
if (NETSNMP_WITH_SDK)
    set (NETSNMP_NETSNMPMIBSLIB_SRCS
        ${NETSNMP_NETSNMPMIBSLIB_SRCS}
        if-mib/ifTable/ifTable.c
        if-mib/ifTable/ifTable_data_access.c
        if-mib/ifTable/ifTable_interface.c
        if-mib/ifXTable/ifXTable.c
        if-mib/ifXTable/ifXTable_data_access.c
        if-mib/ifXTable/ifXTable_interface.c
        if-mib/data_access/interface.c
        mibII/at.c
        mibII/icmp.c
        #mibII/interfaces.c
        notification-log-mib/notification_log.c)
    if (WIN32)
        set (NETSNMP_NETSNMPMIBSLIB_SRCS
            ${NETSNMP_NETSNMPMIBSLIB_SRCS}
            if-mib/data_access/interface_iphlpapi.c
            mibII/data_access/at_iphlpapi.c
            winExtDLL.c)
    endif ()
    if (UNIX)
        set (NETSNMP_NETSNMPMIBSLIB_SRCS
            ${NETSNMP_NETSNMPMIBSLIB_SRCS}
            ip-mib/ipAddressTable/ipAddressTable_interface.c
            ip-mib/ipAddressTable/ipAddressTable_data_access.c
            ip-mib/ipAddressPrefixTable/ipAddressPrefixTable_interface.c
            ip-mib/ipAddressPrefixTable/ipAddressPrefixTable_data_access.c
            ip-mib/ipDefaultRouterTable/ipDefaultRouterTable_interface.c
            ip-mib/ipDefaultRouterTable/ipDefaultRouterTable_data_access.c
            ip-mib/ipDefaultRouterTable/ipDefaultRouterTable_data_get.c
            ip-mib/data_access/arp_common.c
            ip-mib/data_access/systemstats_common.c
            ip-mib/data_access/systemstats_linux.c
            ip-mib/data_access/scalars_linux.c
            ip-mib/ipv6ScopeZoneIndexTable/ipv6ScopeZoneIndexTable_interface.c
            ip-mib/ipv6ScopeZoneIndexTable/ipv6ScopeZoneIndexTable_data_access.c
            ip-mib/ipIfStatsTable/ipIfStatsTable_data_get.c
            ip-forward-mib/ipCidrRouteTable/ipCidrRouteTable_interface.c
            ip-forward-mib/ipCidrRouteTable/ipCidrRouteTable_data_access.c
            ip-forward-mib/inetCidrRouteTable/inetCidrRouteTable_interface.c
            ip-forward-mib/inetCidrRouteTable/inetCidrRouteTable_data_access.c
            tcp-mib/data_access/tcpConn_common.c
            tcp-mib/data_access/tcpConn_linux.c
            tcp-mib/tcpConnectionTable/tcpConnectionTable_interface.c
            tcp-mib/tcpConnectionTable/tcpConnectionTable_data_access.c
            tcp-mib/tcpListenerTable/tcpListenerTable_interface.c
            tcp-mib/tcpListenerTable/tcpListenerTable_data_access.c
            udp-mib/udpEndpointTable/udpEndpointTable_interface.c
            udp-mib/udpEndpointTable/udpEndpointTable_data_access.c
            if-mib/data_access/interface_ioctl.c
            ip-mib/data_access/ipaddress_common.c
            ip-mib/data_access/defaultrouter_common.c
            ip-mib/data_access/ipv6scopezone_common.c
            ip-forward-mib/data_access/route_common.c
            udp-mib/data_access/udp_endpoint_common.c)
        if (APPLE)
            # TODO
        else ()
            set (NETSNMP_NETSNMPMIBSLIB_SRCS
                ${NETSNMP_NETSNMPMIBSLIB_SRCS}
                util_funcs/get_pid_from_inode.c
                mibII/ipv6.c
                if-mib/data_access/interface_linux.c
                ip-mib/data_access/arp_netlink.c
                ip-mib/data_access/ipaddress_ioctl.c
                ip-mib/data_access/ipaddress_linux.c
                ip-mib/data_access/defaultrouter_linux.c
                ip-mib/data_access/ipv6scopezone_linux.c
                ip-forward-mib/data_access/route_ioctl.c
                ip-forward-mib/data_access/route_linux.c
                udp-mib/data_access/udp_endpoint_linux.c)
        endif ()
    endif ()
    if (NOT APPLE)
        set (NETSNMP_NETSNMPMIBSLIB_SRCS
            ${NETSNMP_NETSNMPMIBSLIB_SRCS}
            mibII/ip.c
            mibII/ipAddr.c
            mibII/route_write.c
            mibII/tcp.c
            mibII/tcpTable.c
            mibII/udp.c
            mibII/udpTable.c
            mibII/var_route.c)
    endif ()
endif ()
set (NETSNMP_NETSNMPMIBSLIB_LIBDEPS
    netsnmp)
set (NETSNMP_NETSNMPMIBSLIB_LIBTYPE
    STATIC)
add_library (${NETSNMP_NETSNMPMIBSLIB_NAME} ${NETSNMP_NETSNMPMIBSLIB_LIBTYPE}
    ${NETSNMP_NETSNMPMIBSLIB_SRCS})
target_link_libraries (${NETSNMP_NETSNMPMIBSLIB_NAME}
    ${NETSNMP_NETSNMPMIBSLIB_LIBDEPS})
if (NOT NETSNMP_WITHOUT_INSTALL_LIBRARIES AND NOT NETSNMP_WITHOUT_INSTALL_ALL)
    install (TARGETS ${NETSNMP_NETSNMPMIBSLIB_NAME}
        RUNTIME DESTINATION bin
        LIBRARY DESTINATION lib
        ARCHIVE DESTINATION lib)
endif ()
