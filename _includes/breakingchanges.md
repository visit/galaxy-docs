# Breaking changes

## V3

- <a href="#create-basket">`basket/create`</a> now expects a JSON body containing the parameters PointOfSalesId and Currency instead of `basket/create/{pointofSalesId}/{currency}` query string.

- <a href="#get-previous-search">Get Previous Search</a> now has an endpoint of  `~api/availability/accommodation/get` instead of `~api/availability/get`.

- <a href="#add-accommodation-booking-item">`basket/add/accommodation`</a> and <a href="#add-fuzzy-booking-item">`basket/add/accommodation/fuzzy`</a> now returns an object with Success and BookItemIds list instead of just a success bool.

- `/api/reservation/cancel/info/{bookingCode} ` has been deprecated and will be removed in the future. Use LastCancellation from BookingConfirmation instead.
