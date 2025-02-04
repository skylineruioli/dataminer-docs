---
uid: Web_apps_Feature_Release_10.4.5
---

# DataMiner web apps Feature Release 10.4.5 – Preview

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

> [!TIP]
> For release notes for this release that are not related to the web applications, see [General Feature Release 10.4.5](xref:General_Feature_Release_10.4.5).

## Highlights

*No highlights have been selected yet.*

## New features

#### Dashboards app & Low-Code Apps - Node edge graph component: New features & enhanced performance [ID_38974]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->
<!-- For fixes in RN 38974, see Fixes section below -->

A number of new features have been added to the *Node edge graph* component:

- In low-code apps, a new node edge graph action can now be used: *Clear the data*. When executed, this action will clear the feed status of the node edge graph in question.
- Similar to other GQI components, a node edge graph is now able to recover selections (coming from the URL or when navigating between pages in low-code apps).
- You can now force edge labels to become fully visible by pressing *CTRL+SPACE*.

Also, because of a number of enhancements, overall node edge graph performance has increased.

#### Dashboards app & Low-Code Apps: Web component and Text component can now be linked to a feed [ID_38993]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

Both a *Web* component and a *Text* component can now be linked to a feed.

In case of a *Web* component:

- When *Type* is set to "Custom HTML", the feed syntax can be inserted in the HTML code.
- When *Type* is set to "Webpage", the feed syntax can be inserted in the URL.

In case of a *Text* component, the feed syntax can be inserted in the text.

> [!TIP]
> For more information on feeds, see [Feeds](xref:Using_dashboard_feeds).

> [!NOTE]
>
> - When linking a feed to either a *Web* component or a *Text* component in a dashboard, *Source name* needs to be omitted.
> - Limitations:
>  
>   - When you set a *Web* component to "Custom HTML", the *HTML* box is limited to 100,000 characters. HTML syntax highlighting will be disabled from 15,000 characters onwards.
>   - When you set a *Web* component to "Webpage", the *URL* box is limited to 2,000 characters.
>   - The *Text* box of a *Text* component is limited to 200,000 characters.

#### Dashboards app & Low-Code Apps: Client metric logging [ID_39000]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

In the `C:\Skyline DataMiner\Logging\Web` folder, apart from Web API logging, you can now also find client metric logging.

Client metric logging is employed to record different performance and issue indicators of clients connecting to Dashboards and Low-Code Apps. These logs encompass everything from unexpected errors to the load time of a dashboard or low-code app page. This logging data is stored in the `Client` subfolder of the web logs.

> [!TIP]
> For more information, see [Dashboards and Low-Code Apps logging](xref:Dashboards_and_Low_Code_Apps_Logging).

## Changes

### Breaking changes

#### Low-Code Apps: Parameters of a script action linked to an empty feed will now be filled with an empty array [ID_39027]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

Up to now, when a script parameter of a *Launch a script* action was linked to a feed, that parameters would be set to null when the feed was empty.

From now on, linking a script parameter to an empty feed will fill it with an empty array instead. The dialog to manually enter a parameter will no longer be shown when the action is launched. This change can break existing implementations when it is not handled by the script.

### Enhancements

#### Web apps - DataMiner Object Models: Enhanced behavior of DOMInstanceFieldDescriptor and DomInstanceValueFieldDescriptor fields on DOM forms when not all possible values have been retrieved yet [ID_38719]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

A number of enhancements have been made with regard to the way in which `DOMInstanceFieldDescriptor` and `DomInstanceValueFieldDescriptor` fields are displayed on DOM forms when not all possible values have been retrieved yet.

Up to now, as long as not all values of a dropdown box had been retrieved, its label and its border would be highlighted in orange as a warning. From now on, this will only occur when the dropbox box in question has the focus.

#### Dashboards app & Low-Code Apps - Query filter component: Enhanced button coloring [ID_38754]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

Up to now, the buttons in the *Query filter* component would be barely visible when the color of the app was similar to the background color of the theme. From now on, the buttons in the *Query filter* component will always have the text color of the theme.

#### Dashboards app & Low-Code Apps: Grouping of GQI event messages [ID_38959]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

From now on, GQI event messages sent by the same GQI session within a time frame of 100 ms will be grouped into one single message.

#### Dashboards app & Low-Code Apps: Template editor will now inherit the background color of the component [ID_38996]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

From now on, the template editor will inherit the background color of the component. This will enhance overall visibility regardless of the chosen theme.

#### Web apps: Enhanced performance when starting up [ID_38999]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

Because of a number of enhancements, overall performance has increased when starting up a DataMiner web app.

#### Landing page - Other apps: No longer possible to right-click apps on mobile devices [ID_39036]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

When you open the landing page of a DataMiner Agent (e.g. `https://myDMA/root/`) on a mobile device, it will no longer be possible to open the context menu of apps listed in the *Other apps* section.

#### Web apps - Authentication: Enhanced multi-domain support [ID_39061]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

Multi-domain support has been enhanced.

Up to now, on systems with multiple domain controllers, in some cases, users would not be able to log in to a web app with the user name that was known to the system, listed at the bottom of the *Sign in* box. The latter was linked to another domain than the one linked to the user name with which they were logged in.

#### Legacy Reporter: Clearer message in case of an 'out of memory' error [ID_39089]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

When an "out of memory" error was thrown in the legacy Reporter, up to now, an "Unspecified error: 12" message would be displayed. From now on, when an "out of memory" error is thrown, a clearer, more informative message will be displayed instead.

### Fixes

#### Mobile Visual Overview: Problem when trying to open a popup linked to a single-page visual overview of another object [ID_38793]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

When, in a visual overview opened on a mobile device, you tried to open a popup linked to a single-page visual overview of another object, the popup would incorrectly refuse to open.

#### Dashboards app & Low-Code Apps - Stepper component: Problem when two states were able to transition to each other [ID_38820]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

When a *Stepper* component has to display states of a DOM definition for which no DOM history records are being saved, it relies on the states and transitions within the DOM behavior definition to build the steps.

Up to now, when two states were able to transition to each other, an infinite loop would occur, causing the browser to become unresponsive.

#### Dashboards app & Low-Code Apps - Dropdown component: Filter would no longer be applied after losing the focus [ID_38834]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

When a *Dropdown* component with a filter applied lost the focus, the moment it had the focus again, the filter would no longer be applied.

#### Dashboards app: Problem with Dropdown components on shared dashboards [ID_38953]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

When, on a shared dashboard, a *Dropdown* component had a time range or service definition filter applied, it would not be possible to use that component.

#### Dashboards app & Low-Code Apps - Node edge graph component: Issues fixed [ID_38974]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->
<!-- For new features & enhancements in RN 38974, see New features section above -->

A number of issues related to Node edge graph component have been solved:

- When a node edge graph was linked to the query filter, in some cases, the filter would not be applied correctly for nodes/edges that were not visible in the view. Panning towards those nodes/edges would then show them as hidden/visible while they should be visible/hidden.
- Up to now, a node edge graph would incorrectly reset its viewport when the query or filter had changed.
- In some cases, the edge coloring/highlighting would incorrectly not be applied for parameters with very small numeric values.

#### Web apps: Context menu would not close when scrolling on a mobile device [ID_38992]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

When, on a mobile device, you scrolled while a context menu was open, that context menu would incorrectly not close.

#### Dashboards app & Low-Code Apps - Timeline component & Time range component: Problem when the default range was set to '... so far' [ID_39056]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

When you had set the default range of a *Timeline* component or a *Time range* component to "This week so far", "This month so far" or "This year so far", in some cases, the default range would incorrectly revert to "Today so far" when the configuration of the component was saved.

Also, in some cases, a *Timeline* component or a *Time range* component would not get visually updated when the default range was set to a different value.

#### Dashboards app & Low-Code Apps: Protocol versions of mediation protocols would incorrectly not be production versions [ID_39094]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

When, in the *DATA* pane, you opened the *PARAMETERS* section, set the *From* box to "Protocol", and opened the *Protocol* box, the protocol versions of mediation protocols would incorrectly not be the production versions that were actually used.

#### Web apps: Disconnection message would not disappear after the WebSocket connection had been restored [ID_39095]

<!-- MR 10.3.0 [CU14] / 10.4.0 [CU2] - FR 10.4.5 -->

When a web app loses its WebSocket connection, a `Connection has been interrupted` message is displayed in the app's subheader. In some cases, that message would incorrectly not disappear once the WebSocket connection was restored.

From now on, a message will also be displayed in the app's subheader when not all messages received when the app was disconnected could be recovered. That same message will ask the user to refresh the app.
