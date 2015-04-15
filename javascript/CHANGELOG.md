# Changelog

## 4.0.0

* Update to API version `1.16`

#### Changes in V1.16:

The format of all timestamps has been unified to be in the format `YYYY-MM-DDTHH:MM:SSZ`, the following types and properties are affected:
* `Autosave.Full`: `created`, `modified`
* `Autosave`: `created`, `modified`
* `File`: `created`, `modified`
* `Page.Version`: `created`
* `Permission.Site`: `created`
* `Pin.Version`: `created`
* `Pin`: `created`, `modified`
* `Tag.Version`: `created`
* `Tag`: `created`, `modified`
* `User.Invite`: `created`, `modified`, `sent`

Properties named `repository` have been renamed to `site`, the following types are affected:
* `Autosave`
* `Permission`
* `User.Invite`

Other breaking changes:
* `Import.SiteStatus`: Contains a new version of `Status`
* `Import.Status`: Contains a new state `computingTagList` which occurs after `inProgress` and before `complete`/`errored`.
* `Site`: The `public` property has been removed, use `privacy` instead.

Non-breaking additions:
* `Import.Progress`: Added `errorInfo : Array<ErrorInfo>`
* `Import.Status`:
  * The `complete` state now contains `optional VersionIds`
  * The `errored` state now contains `{ versions : optional VersionIds, errors : Array<ErrorInfo> }`

New types:

* `Import.ErrorInfo`: If importing a page fails this type contains the row in the CSV/spreadsheet along with the uri and title the page would have had if it imported successfully. You can use this to know which pages to retry or create manually.
* `VersionIds { pageId : int, tagId : int }`

### 3.0.0

* Update to API version `1.14`

Breaking changes:

* New interface for subscriptions, modify a user's subscription by using `SilkApi:User:SubscriptionSite`, and see the subscribers of a site with `SilkApi:Site:Subscription`

Additions:

* `SilkApi:Site:Import.uploadSheetsUrl`
* `SilkApi:Site:Import.uploadSheets`
* `SilkApi:Site:Import.selectSheet`
* Subscription frequency can now be `"none"`, which will disable e-mail digests

### 2.1.0

Additions:

* `Silk:suggestPage` takes the title of a page and suggest a non-occupied uri using the same normalization scheme as Silk uses internally.

## 2.0.0

Breaking changes:
* The `cookieJar` instance member is no longer available on sub resources. It can still be accessed on the top-level api object.

Additions:
* You can now optionally supply `modifyRequest(RequestObject) : RequestObject` as a third argument to `SilkApi`. This function, if present, will be called before every request and lets you modify the request object.

## 1.0.0

* Initial release, using API version `1.13.4`.
