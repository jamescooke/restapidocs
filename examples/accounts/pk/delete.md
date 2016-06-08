# Delete User's Account

Delete the Account of the Authenticated User if they are Owner.

**URL** : `/api/accounts/:pk/`

**URL Parameters** : `pk=[integer]` where `pk` is the ID of the Account in the
database.

**Method** : `DELETE`

**Auth required** : YES

**Permissions required** : User is Account Owner

**Data** : `{}`

## Success Response

**Condition** : If the Account exists.

**Code** : `204 NO CONTENT`

**Content** : `{}`

## Error Responses

**Condition** : If there was no Account available to delete.

**Code** : `404 NOT FOUND`

**Content** : `{}`

### Or

**Condition** : Authorized User is not Owner of Account at URL.

**Code** : `403 FORBIDDEN`

**Content** : `{}`


## Notes

* Will remove memberships for this Account for all Users that had access.
