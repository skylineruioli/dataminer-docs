---
uid: General_Feature_Release_10.4.5
---

# General Feature Release 10.4.5 – Preview

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

> [!IMPORTANT]
> When downgrading from DataMiner Feature Release version 10.3.8 (or higher) to DataMiner Feature Release version 10.3.4, 10.3.5, 10.3.6 or 10.3.7, an extra manual step has to be performed. For more information, see [Downgrading a DMS](xref:MOP_Downgrading_a_DMS).

> [!TIP]
>
> - For release notes related to DataMiner Cube, see [DataMiner Cube Feature Release 10.4.5](xref:Cube_Feature_Release_10.4.5).
> - For release notes related to the DataMiner web applications, see [DataMiner web apps Feature Release 10.4.5](xref:Web_apps_Feature_Release_10.4.5).
> - For information on how to upgrade DataMiner, see [Upgrading a DataMiner Agent](xref:Upgrading_a_DataMiner_Agent).

## Highlights

*No highlights have been selected yet.*

## New features

#### New SLTimeToLive.txt log file containing all changes made to the TTL settings [ID_38851]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

In the `C:\Skyline DataMiner\Logging\SLTimeToLive` folder, you can now find a new *SLTimeToLive.txt* log file, listing all changes made to the TTL settings in Cube's *System Center > System settings > Time to live* page.

> [!NOTE]
> The contents of this folder will not be deleted during either a DataMiner restart or a DataMiner upgrade. However, in the *SLTimeToLive.txt* file, the oldest entries will be removed when the maximum log file size is exceeded.

#### STaaS: SLDataGateway will now periodically check the health of the storage service [ID_39068]

<!-- MR 10.4.0 [CU2] - FR 10.4.5 -->

When Storage as a Service (STaaS) is used, SLDataGateway will now periodically check the health of that storage service. If the current status cannot be determined or if the current status is "red", SLDataGateway will switch to file offload mode.

> [!NOTE]
>
> - When the current status is "yellow", SLDataGateway will not switch to file offload mode.
> - Whenever the health of the storage service changes, an alarm mentioning the current health status is generated.

#### GQI: The IGQIOnInit and IGQIOnDestroy interfaces can now also be used in custom operators [ID_39088]

<!-- MR 10.5.0 - FR 10.4.5 -->

From now on, the `IGQIOnInit` and `IGQIOnDestroy` interfaces can also be used in custom operators.

For more information on these interfaces, see:

- [IGQIOnInit interface](xref:GQI_IGQIOnInit)
- [IGQIOnDestroy interface](xref:GQI_IGQIOnDestroy)

## Changes

### Breaking changes

#### DOM string fields will now be filtered case-insensitively [ID_38950]

<!-- MR 10.4.0 [CU2] - FR 10.4.5 -->

Up to now, DOM string fields would be filtered case-sensitively. From now on, those fields will by default be filtered case-insensitively.

> [!NOTE]
> If necessary, this default filter behavior can be overruled in code by using `StringComparison.Ordinal`. See the following snippet.
>
> ```csharp
> var filter = DomInstanceExposers.FieldValues.DomInstanceField(_stringFieldDescriptor.ID).Contains("test", StringComparison.Ordinal)
> ```

### Enhancements

#### Service & Resource Management: Enhanced performance of volume license check [ID_38705]

<!-- MR 10.4.0 [CU2] - FR 10.4.5 -->

Because of a number of enhancements, overall performance has increased when performing volume license checks.

#### APIGateway now runs on .NET 8 and allows you to enable kernel response buffering [ID_38710]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

APIGateway has been upgraded. It now runs on Microsoft .NET 8.

This service now allows you to enable kernel response buffering, which should improve throughput and responsiveness over high-latency connections. This setting is disabled by default. To enable it, do the following:

1. In the `C:\Program Files\Skyline Communications\DataMiner APIGateway\` folder of the DataMiner Agent, create a JSON file named *appsettings.custom.json*.
1. Open this JSON file, and add the following content:

   ```json
   { "HostingOptions": { "EnableKernelResponseBuffering": true } }
   ```

#### Automation: Cassandra Ready check will now only be performed on DataMiner Systems using a MySQL database [ID_38760]

<!-- MR 10.4.0 [CU2] - FR 10.4.5 -->

Up to now, Automation scripts would always be checked whether they were Cassandra ready, regardless of the type of database used by the DataMiner System.

From now on, this Cassandra ready check will only be performed on DataMiner Systems using a MySQL database. When the DataMiner System is using a type of database other than MySQL, Automation scripts will always be considered Cassandra ready.

#### Enhanced performance when starting up a DataMiner Agent with a large number of virtual elements [ID_38780]

<!-- MR 10.4.0 [CU2] - FR 10.4.5 -->

Because of a number of enhancements, overall performance has increased when starting up a DataMiner Agent with a large number of virtual elements.

#### Security enhancements [ID_38904]

<!-- RN 38904: MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

A number of security enhancements have been made.

#### Grouping of GQI event messages [ID_38913]

<!-- MR 10.5.0 - FR 10.4.5 -->

From now on, GQI event messages sent by the same GQI session within a time frame of 100 ms will be grouped into one single message.

#### SLAnalytics - Behavioral anomaly detection: Enhancements [ID_39024]

<!-- MR 10.4.0 [CU2] - FR 10.4.5 -->

A number of enhancements have been made with regard to the behavioral anomaly detection feature.

### Fixes

#### Problem with user accounts [ID_38182]

<!-- MR 10.4.0 [CU2] - FR 10.4.5 -->

In some cases, user accounts could become corrupted.

Also, in some cases, SLDataMiner could stop working when an alarm template or trend template was uploaded, removed, assigned or unassigned.

#### Automatic incident tracking: Incomplete or empty alarm groups after DataMiner startup [ID_38441]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

After a DataMiner startup, in some cases, certain alarm groups would either be incomplete or empty due to missing remote base alarms.

#### Problem when migrating SLAnalytics data, DOM data or SRM data to STaaS [ID_38884]

<!-- MR 10.4.0 [CU2] - FR 10.4.5 -->

When being migrated to STaaS, SLAnalytics data, DOM data or SRM data would incorrectly not be replicated. This could cause data created during the migration to be missing after the migration.

#### Not possible to delete a service created via an SRM booking when it had been assigned a name that was already being used [ID_38914]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

When a service created via an SRM booking got into an error state because it had been assigned a name that was already being used by another object, it would not be possible to delete it as it would be considered invalid.

#### GQI: Problem when loading extensions [ID_38998]

<!-- MR 10.5.0 - FR 10.4.5 -->

When GQI extensions (i.e. ad hoc data sources or custom operators) were being loaded, in some cases, an exception could be thrown when inspecting the assembly of an extension that prevented subsequent extensions from being loaded.

This type of exceptions will be now be properly caught and logged as warnings so that other extensions will no longer be prevented from being loaded.

> [!TIP]
> See also: [GQI: Full logging [ID_38870]](xref:General_Feature_Release_10.4.4#gqi-full-logging-id_38870)

#### Problem while checking whether the DataMiner System was licensed to use the ModelHost DxM [ID_39001]

<!-- MR 10.5.0 - FR 10.4.5 -->

A *ModelHostException* could be thrown while checking whether the DataMiner System was licensed to use the ModelHost DxM.

#### STaaS: Database queries could time out [ID_39081]

<!-- MR 10.4.0 [CU2] - FR 10.4.5 -->

When a database query was performed against a STaaS database, in some cases, the query could time out, leading to no results being returned.
