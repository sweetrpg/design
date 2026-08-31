# Notes

OpenFGA for authorization?

catalog-entity-versioning, group 7

Error page icons:
  - "400": bad request
  - "401": unauthorized
  - "403": forbidden
  - "404": not found
  - "500": internal server error
  - "502": bad gateway
  - "503": service unavailable
  - "504": gateway timeout

## Feedback

### User Profile

- pictures of your actual shelves, limit 10
- display name
- username?
- bio/description
- birthday (month, day only)
- messages from other users

### Game Room Web Landing Page

Next feedback, no images since you can't use them. This is for the game-room-web landing page:
- all user-facing text should be localized
 volumes in the library card should have titles, not ID (this will require some multi-repo updates, since game-room-api's model for library entries only includes volume ID -- the endpoint should behave as a JSON-API endpoint and include related documents, so a cross-service call to catalog-api will need to occur to get volume details, but it should not be wasteful [i.e., one call per volume], so catalog-api may need a bulk-get endpoint for volumes

### Game Room Web Library Detail Page

- Volumes should have titles, not ID (denormalize volume data from catalog-api when the volume is added, add "refresh volume info" to library detail to get current volumes titles, etc.)
    - library items should support multi-select so multiple volumes can have their visibility changed at once
    - "remove" button should follow platform standard: icon with tooltip, destructive actions are colored apporpriately and include confirmation before actually executing
    - show icon and text for "effective visibility" with localized value, not internal value
    - native dropdown for visibility override is ugly: use menu like visibility for library itself, present confirmation that shows new effective visibility value and warn if new visibility value is more open than before

- Hover over a title shows a popover with the volume's title, ID (in subtitle color) and the cover

- Override visibility icon in library detail should be an "eye" icon with tooltip
- Combine effective visibility and override into a single column

- Add column for notes/info - shows loaned out status and other info
- Add "loan out" action button

- Delete button should confirm before deleting

- Show activity spinner when looking up volumes in "add to library" dialog

- Tooltip for visibility menu should show the current visibility level and what the button does

### Game Room Web Tables Browse Page

- 500 error, plain and simple
