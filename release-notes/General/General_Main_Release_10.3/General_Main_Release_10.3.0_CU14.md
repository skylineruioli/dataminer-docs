---
uid: General_Main_Release_10.3.0_CU14
---

# General Main Release 10.3.0 CU14 – Preview

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

> [!TIP]
> For information on how to upgrade DataMiner, see [Upgrading a DataMiner Agent](xref:Upgrading_a_DataMiner_Agent).

### Enhancements

#### APIGateway now runs on .NET 8 and allows you to enable kernel response buffering [ID_38710]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

APIGateway has been upgraded. It now runs on Microsoft .NET 8.

This service now allows you to enable kernel response buffering, which should improve throughput and responsiveness over high-latency connections. This setting is disabled by default. To enable it, do the following:

1. In the `C:\Program Files\Skyline Communications\DataMiner APIGateway\` folder of the DataMiner Agent, create a JSON file named *appsettings.custom.json*.
1. Open this JSON file, and add the following content:

   ```json
   { "HostingOptions": { "EnableKernelResponseBuffering": true } }
   ```

#### New SLTimeToLive.txt log file containing all changes made to the TTL settings [ID_38851]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

In the `C:\Skyline DataMiner\Logging\SLTimeToLive` folder, you can now find a new *SLTimeToLive.txt* log file, listing all changes made to the TTL settings in Cube's *System Center > System settings > Time to live* page.

> [!NOTE]
> The contents of this folder will not be deleted during either a DataMiner restart or a DataMiner upgrade. However, in the *SLTimeToLive.txt* file, the oldest entries will be removed when the maximum log file size is exceeded.

#### Security enhancements [ID_37345] [ID_38904]

<!-- RN 37345: MR 10.3.0 [CU14] - FR 10.3.11 -->
<!-- RN 38904: MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

A number of security enhancements have been made.

### Fixes

#### Databases: Problem when starting a migration from MySQL to Cassandra [ID_37589]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.1 -->

When you started a migrating from a MySQL database to a Cassandra database, an error could occur when the connection to the MySQL database took a long time to get established.

#### Automatic incident tracking: Incomplete or empty alarm groups after DataMiner startup [ID_38441]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

After a DataMiner startup, in some cases, certain alarm groups would either be incomplete or empty due to missing remote base alarms.

#### Not possible to delete a service created via an SRM booking when it had been assigned a name that was already being used [ID_38914]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

When a service created via an SRM booking got into an error state because it had been assigned a name that was already being used by another object, it would not be possible to delete it as it would be considered invalid.
