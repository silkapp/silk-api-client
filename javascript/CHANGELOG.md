# Changelog

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
