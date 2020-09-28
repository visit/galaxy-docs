# Breaking changes

## From V4 to V5

- Response from endpoints <a href="#addon-products">`basket/addon/{basketId}`</a> and <a href="#addon-products">`basket/addon/{basketId}/{bookItemId}`</a> are now restructured to return addon groups which contain available addons.

- Response from endpoints <a href="#calendar-search">`availability/accommodation/placement/calendar`</a> and <a href="#calendar-search-by-day">`availability/activity/calendar/byday`</a> now return only available dates, therefore isAvailble flag is removed.

## From V3 to V4

- <a href="#availability---placement-accommodation">Accommodation availability search with placement</a> (the previous default) has endpoints moved from `availability/accommodation`, `availability/accommodation/get` and `basket/add/accommodation` to `availability/accommodation/placement`, `availability/accommodation/placement/get` and `basket/add/accommodation/placement`.

- <a href="#availability---accommodation">Accommodation availability search without placement</a> (the new default) has endpoints moved from `availability/accommodation/noplacement`, `availability/accommodation/noplacement/get` and `basket/add/accommodation/noplacement` to `availability/accommodation`, `availability/accommodation/get` and `basket/add/accommodation`.

- <a href="#get-basket">`basket/{basketId}`</a> no longer includes any `VatAmount` fields since it was incorrectly showing product tax and did not account for tour operator margin schemes.

- <a href="#get-basket">`basket/{basketId}`</a> product addons integer fields `BookItemId`, `PriceGroupId` and `AddonId` have been replaced by a string field `AddonId`.

- <a href="#addon-products">`basket/addon/{basketId}`</a> and <a href="#addon-products">`basket/addon/{basketId}/{bookItemId}`</a> available addons are further simplified and now provides you with a total price, `MinimumNumberOfUnits` and `MaximumNumberOfUnits`. The integer fields `AddonId` and `PriceGroupId` are replaced by a string field `AddonId`. Addons DELETE verb is removed, you can remove addons by posting zero to `Quantity`.

- `availability/accommodation/placement`, `availability/accommodation/placement/get`, `availability/accommodation` and `availability/accommodation/get` now include list of mandatory addons that have been renamed from IncludedSubProducts to IncludedAddons.

- `reservation/cancel/info` was removed. Use the `LastCancellation` field from <a href="#get-latest-reservation-version">`reservation/latest`</a> instead.

- `basket/commit/async` has moved to <a href="#commit-basket">`basket/commit`</a> and replaced the previous synchronous commit call, poll <a href="#commit-status">`basket/commit/status/{id}`</a> to check status.

- <a href="#cancel-reservation">`reservation/cancel`</a> is now asynchronous, poll <a href="#commit-status">`basket/commit/status/{id}`</a> to check status.

- `availability/accommodation/fuzzy/scan`, `availability/accommodation`, `availability/accommodation/placement`, `availability/accommodation/calendar`, `availability/activity`, `availability/activity/calendar/byproduct` and `availability/activity/calendar/byday` now includes a list of `Operations` which will indicate the duration, success and error message, if any, on all the systems involved in the search.

## From V2 to V3

- <a href="#create-basket">`basket/create`</a> now expects a JSON body containing the parameters PointOfSalesId and Currency instead of `basket/create/{pointofSalesId}/{currency}` query string.

- <a href="#get-previous-search">Get Previous Search</a> now has an endpoint of  `availability/accommodation/get` instead of `availability/get`.

- <a href="#add-accommodation-booking-item">`basket/add/accommodation`</a> and <a href="#add-fuzzy-accommodation-booking-item">`basket/add/accommodation/fuzzy`</a> now returns an object with Success and BookItemIds list instead of just a success bool.

- `reservation/cancel/info/{bookingCode} ` has been deprecated and will be removed in the future. Use the `LastCancellation` field from <a href="#get-latest-reservation-version">`reservation/latest`</a> instead.

- `Optional products` are now called `addons` and have been refactored to be easier to use. The call updating the addons has been splitted in an update and a delete call to give you more control. Booked addons are now found in <a href="#get-basket">the basket</a>.
