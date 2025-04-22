---
title: Hidden troubleshooting
description: Hidden trouble
type: Troubleshooting
hide: yes
hidefromtoc: yes
exl-id: dfb54d2d-e4f4-420f-8e91-f1aba704cb31
---
# Hidden troubleshooting

There is `type: Troubleshooting` applied to this page. Does it have a left nav?

## Code table

**outside of table**

```json
PrimaryIdentities [
  {"id": "ccid-2", "namespace": "CCID"},
  {"id": "ecid-1", "namespace": "ECID"},
  {"id": "ecid-2", "namespace": "ECID"}
  ]
NonPrimaryIdentities [
  {"id": "ccid-1", "namespace": "CCID"},
  {"id": "ecid-3", "namespace": "ECID"}
  ]
  "id": "ccid-1",
    "namespace": "CCID"
```

**straight code in table**

<table>
    <tr>
      <th>Sorted identities list</th>
      <th>Selected identity</th>
    </tr>
    <tr>
      <td><code>PrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-2", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-1", "namespace": "ECID"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "namespace": "ECID"}<br/>&nbsp;]<br/>&nbsp;NonPrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-1", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-3", "namespace": "ECID"}<br/>]</code> </td>
      <td><code>"id": "ccid-1",<br/>&nbsp;"namespace": "CCID"</code> </td>
    </tr>
  </table>

**using pre lang code in table**

<table>
    <tr>
      <th>Sorted identities list</th>
      <th>Selected identity</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>PrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-2", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-1", "namespace": "ECID"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "namespace": "ECID"}<br/>&nbsp;]<br/>&nbsp;NonPrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-1", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-3", "namespace": "ECID"}<br/>]</pre></code> </td>
      <td><pre lang="json"><code>"id": "ccid-1",<br/>&nbsp;"namespace": "CCID"</pre></code> </td>
    </tr>
  </table>

## Deep links with new tab

Click here: [Relative link to article open in new tab](hidden/bug-fixes.md#test-for-autoactivate){target=_blank}

```
Click here: [Relative link to article open in new tab](hidden/bug-fixes.md#test-for-autoactivate){target=_blank}
```
