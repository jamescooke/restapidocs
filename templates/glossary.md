# Terms

A guide to the terms used in the templates with suggestions on how to complete
them, or when to remove them. Items appear in the order that they are used in
the templates.

## Endpoint title

Use "[action] a [thing]" structure for title.

For example, "Confirm a User", "Create a Post".

## Endpoint description

A short description of the purpose of the endpoint.

## URL

The [path, query and any
fragments](https://en.wikipedia.org/wiki/Uniform_Resource_Identifier#Generic_syntax)
for the URL of this service. Prefix any variables used in the URL with colon
`:` and describe them in the URL_variable section below the URL.

Examples:

    /api/session/:pk/confirm/
    /books/?author=:a_id

The convention in these templates has been to use `:pk` as the variable for a
primary key, but there is no necessity to stick to that.

### URL_variable, URL_var_type, URL_var_desc

For each colon-prefixed URL variable, create a row in the info table describing
how the variable must be formatted and populated.

Examples

```
| URL `:pk` | `[int]` ID of Account        |
| URL `:mk` | `[int]` ID of Account member |
```

Delete this row when endpoint URL has no variables.

## Data constraint JSON

When particular data is required, outlined the data requirements in this
section. Describe the type of each value in the JSON structure as a string, for
example, `"[int]"` or `"[str max 255]"`.

```json
{
    "invitation_key": "[str 40 char hex]",
    "name": "[str max 255, unique]",
    "partner_name": "[str max 255, optional]"
}
```

Assume that all fields are required, and mark optional fields with "optional".

## Data constraint

Where more detail is required for any particular element of the Data constraint
JSON, outline this here. If there are no data constraints, write "None" and
delete the "Where:".

Examples:

* TODO

## Request method

A valid [HTTP request
method](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods). For
example, GET or POST.

## Success pl

When there is only one "Success Response" then ensure that this title is
singular and do not include a sub-sub-title for the single success. See [Login
Success Response](/examples/login.md#success-response) for an example of an
endpoint with a single success response.

Otherwise, there is more than one type of success response. Pluralise the
title "Success Responses" and include a sub-sub-title for each one. See [Show
Accessible Accounts](/examples/accounts/get.md#success-responses) for an
example of an endpoint with multiple success responses.

## Response title

## Response condition

## Response code

The response code given in this example response selected from the [list of
http status codes](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes).
The convention of this documentation system is to capitalise the text of the
code, for example `204 NO CONTENT`.

## JSON example

When there is no response body used with a particular HTTP response code, then
remove the JSON example and the "Content example" heading for that Success /
Failure example.
