# Show Single Account

Show a single Account if current User has access permissions to it.

**URL** : `/api/accounts/:pk/`

**URL Parameters** : `pk=[integer]` where `pk` is the ID of the Account on the
server.

**Method** : `GET`

**Auth required** : YES

**Permissions required** :

User is at least one of the following in relation to the Account requested:

* Owner `OO`
* Admin `AA`
* Viewer `VV`

**Data**: `{}`

## Success Response

**Condition** : If Account exists and Authorized User has required permissions.

**Code** : `200 OK`

**Content example**

```json
{
    "id": 345,
    "name": "Super Account",
    "enterprise": false,
    "url": "http://testserver/api/accounts/345/"
}
```

## Error Responses

**Condition** : If Account does not exist with `id` of provided `pk` parameter.

**Code** : `404 NOT FOUND`

**Content** : `{}`

### Or

**Condition** : If Account exists but Authorized User does not have required
permissions.

**Code** : `403 FORBIDDEN`

**Content** :

```json
{"detail": "You do not have permission to perform this action."}
```

## Notes

There are security issues:

* This view allows existing users to test for existence of accounts that exist
    but that they do not have access to.
* Account IDs are sequential so an authorized user can count all the Accounts
    on the system.
