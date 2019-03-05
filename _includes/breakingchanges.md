# Breaking changes

## V3

- <a href="#create-basket">`basket/create`</a> now expects a JSON body containing the parameters PointOfSalesId and Currency instead of `basket/create/{pointofSalesId}/{currency}` query string.

- <a href="#get-previous-search">Get Previous Search</a> now has an endpoint of  `~api/availability/accommodation/get` instead of `~api/availability/get`.

- <a href="#add-accommodation-booking-item">`basket/add/accommodation`</a> and <a href="#add-fuzzy-accommodation-booking-item">`basket/add/accommodation/fuzzy`</a> now returns an object with Success and BookItemIds list instead of just a success bool.

- `/api/reservation/cancel/info/{bookingCode} ` has been deprecated and will be removed in the future. Use the `LastCancellation` field from <a href="#get-latest-reservation-version">`reservation/latest`</a> instead.

- `Optional products` are now called `addons` and have been refactored to be easier to use. The call updating the addons has been splitted in an update and a delete call to give you more control. Booked addons are now found in <a href="#get-basket">the basket</a>.
