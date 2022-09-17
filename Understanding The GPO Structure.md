# Understanding The GPO Structure

The GPO is divided to two, User Configuration and Computer Configuration

## GPO Assignment
A GPO can be associated (linked) to one or more Active Directory containers.
Multiple containers can be linked to the same GPO, and a single container can have more than one GPO linked to it. 
If multiple GPOs are linked to one container, you can prioritize the order in which GPOs are applied.

## GPO Inheritence
By default, Group Policy is inherited and cumulative, and it affects all computers and users in an Active Directory container.

GPOs are processed in the following order:

1. The local GPO is applied.
2. GPOs linked to sites are applied.
3. GPOs linked to domains are applied.
4. GPOs linked to organizational units are applied. For nested organizational units, GPOs linked to parent organizational units are applied before GPOs linked to child organizational units are applied.

The last GPO to be applied is the first to try and solve a conflict (different explicit settings)