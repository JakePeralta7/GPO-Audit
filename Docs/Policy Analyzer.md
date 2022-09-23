# Policy Analyzer

Policy Analyzer is a utility for analyzing and comparing sets of Group Policy Objects (GPOs). It can highlight when a set of Group Policies has redundant settings or internal inconsistencies, and can highlight the differences between versions or sets of Group Policies. It can also compare GPOs against current local policy settings and against local registry settings. And you can export its findings to a Microsoft Excel spreadsheet.

Policy Analyzer lets you treat a set of GPOs as a single unit.  This makes it easy to determine whether particular settings are duplicated across the GPOs or are set to conflicting values.  It also lets you capture a baseline and then compare it to a snapshot taken at a later time to identify changes anywhere across the set.

For example, the US Government Configuration Baseline (USGCB) for Windows 7 includes seven different GPOs.  Policy Analyzer can treat them as a single set, and show all the differences between them and the Microsoft recommended baselines for Windows 10 and Internet Explorer 11 with a single comparison.  You can also use it to verify changes that were made to your production GPOs.

The following screenshot shows two baselines compared with each other and to corresponding registry values on the local system. The lower pane displays the Group Policy setting, location, and other information associated with the selected row. Conflicting settings are highlighted in yellow; absent settings are shown as a grey cell. Policy Analyzer also offers options to display only rows containing conflicts or other differences.

![Policy Analyzer GUI](/Img/119320i7FDC58E883D5F3BA.png "Title")

he following screenshot shows Policy Analyzer’s Excel output. Policy Analyzer sorts results primarily by the Group Policy path and setting name columns, which are the leftmost columns.

![Policy Analyzer Excel](/Img/119321i3E69AD9EA5121875.png "Title")

Policy Analyzer is a lightweight standalone application that doesn’t require installation, and doesn’t require administrative rights (except for the “local policy” feature).
