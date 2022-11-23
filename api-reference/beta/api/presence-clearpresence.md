---
title: "presence: clearPresence"
description: "Clear the presence information for a user's application presence session."
author: "mkhribech"
ms.localizationpriority: medium
doc_type: apiPageType
ms.prod: "cloud-communications"
---

# presence: clearPresence

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Clear a [presence session](presence-setpresence.md#presence-sessions) of an application for a user. If it is the user's only presence session, a successful **clearPresence** changes the user's presence to `Offline/Offline`.

Read more about [presence sessions](presence-setpresence.md#presence-sessions) and their [time-out and expiration](presence-setpresence.md#timeout-expiration-and-keep-alive). 

## Permissions
The following permission is required to call the API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
| :------------------------------------- | :------------------------------------------ |
| Delegated (work or school account)     | Presence.ReadWrite                          |
| Delegated (personal Microsoft account) | Not Supported.                              |
| Application                            | Presence.ReadWrite.All                      |

## HTTP Request
<!-- { "blockType": "ignored" } -->
```http
POST /users/{userId}/presence/clearPresence
```

## Request headers
| Name          | Description                 |
| :------------ | :-------------------------- |
| Authorization | Bearer {token}. Required.   |
| Content-Type  | application/json. Required. |

## Request body

Do not supply a request body for this method.

> [!NOTE]
>- `sessionId` body parameter is deprecated. It is deduced from application id encoded in the authorization token.

## Response
If successful, this method returns a `200 OK` response code.

If the presence session doesn't exist, this method returns a `404 NotFound` response code.

## Examples
The following request shows the application with ID `22553876-f5ab-4529-bffb-cfe50aa89f87` that clears its presence session for user `fa8bf3dc-eca7-46b7-bad1-db199b62afc3`.

### Request

<!-- {
  "blockType": "request",
  "name": "clear--presence"
}-->

```msgraph-interactive
POST https://graph.microsoft.com/beta/users/fa8bf3dc-eca7-46b7-bad1-db199b62afc3/presence/clearPresence
```

---


### Response

<!-- {
  "blockType": "response",
  "truncated": true
} -->
```http
HTTP/1.1 200 OK
```
