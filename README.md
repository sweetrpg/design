# sweetrpg-design

## Architecture

* [Architecture](Architecture.md)
* [Figma](https://www.figma.com/)

## Icons

UI icons are defined in the platform's [icon vocabulary](https://github.com/sweetrpg/platform/blob/master/docs/visual-design-conventions.md#icon-vocabulary): one icon per action, with source and license.

## Concepts

<a name="audit"></a>
### Audit Fields

Each model object contains several date/time fields that track when the database record for the model object
was created, and when it was modified. Fluent keeps these fields up-to-date automatically.

<a name="delete"></a>
### Deleted Records

Instead of truly deleting a record from the database, a date/time field is used to mark the time of deletion.
If this field's value is non-`nil`, the record is considered deleted.

<a name="slug"></a>
### Slugs vs. Identifiers

Identifiers are typically UUIDs, but these make for nastly looking URLs, so a slug is used as a secondary
identifier (a unique field on the database record), and will be used for the lookup.
