# Nager.Date review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-24  
**Category:** Public holiday data APIs  
**Method:** Source-led desk review; no hands-on testing is claimed.

Nager.Date’s catalog URL currently redirects to Nager.Holidays, a public-holiday data project with an API and country coverage pages. Its current API documentation describes country-and-year requests with fields for dates, subdivisions and holiday types.

## Editorial verdict

Nager.Date is relevant to an application that needs holiday reference data, provided the team verifies the countries and kinds of dates it requires. A holiday listing should not be treated as a complete definition of every organization’s working calendar.

## A calendar integration needs the correct kind of date

A booking app, a public calendar and an internal work planner may ask different questions of holiday data. The current documentation lists holiday types including public, bank, school and observance categories. Decide which kinds belong in the application instead of treating every returned date as the same instruction.

Give a user enough context to understand what the date means. A named holiday can be useful information without implying that a particular shop, office or individual is unavailable. Keep organization-specific opening hours and exceptions in their own deliberate part of the product.


## Check the region the user actually selected

A country is not always a sufficient description of the calendar someone needs. The documented response includes subdivision information and a national-holiday indicator. Use representative regional cases when evaluating whether the dataset fits the application’s audience.

The published coverage page is a starting point, not proof that every date and subtype needed by your workflow is present. Record the cases the app depends on and compare the resulting display with appropriate authoritative references before relying on it for important scheduling decisions.


## A website redirect is not an API migration test

The catalog’s Nager.Date URL currently redirects to Nager.Holidays, whose checked quick start documents a v4 request path. An existing application may use a different path. Inventory its actual requests and review the relevant change information before replacing an endpoint.

Test a complete response and an invalid request using the version you intend to operate. Keep the application’s parsing rules tied to that documented model. This review did not establish backward compatibility for every historical endpoint or execute a migration.


## Represent calendar dates without accidental shifts

A holiday date belongs to a calendar context. An application should preserve that intended date when it stores and displays the value, especially when its users are in different time zones. Define the representation and inspect the result around year changes and the regions the product supports.

Choose a recoverable refresh and caching process so a temporary service problem does not silently erase the calendar. Roseram did not certify the dataset’s completeness or measure the service’s availability. The review provides source-based integration questions and identifies the current documentation path.


## Features and decision criteria

- Public holiday data service
- Country and year API queries
- Subdivision and holiday-type fields
- Published country coverage information

## Pricing considerations

The checked current API page advertises no rate limits and links service terms. That statement does not establish an uptime commitment, historical endpoint compatibility or the terms of any separate offering. Verify the current arrangement for the intended deployment.

## Frequently asked questions

### Why does the Nager.Date website open Nager.Holidays?

The catalog URL redirected to that site during this documentation check. Preserve the identity relationship while verifying the API version your application uses.

### Is a public holiday automatically a day every business is closed?

No. An application should distinguish reference holiday data from the organization’s actual operating schedule.

### Should I assume all regional dates are covered?

No. Review the published country coverage and verify representative subdivision cases required by the application.


## Sources and further reading

- [Nager.Date website](https://date.nager.at/)
- [Nager.Holidays current API documentation](https://nagerholidays.com/api)
- [Nager.Holidays country coverage](https://nagerholidays.com/country/coverage)
- [publicapi listing](https://publicapi.dev/nager-date-api)

For the complete Roseram buyer guide, see [Nager.Date review](https://roseram.com/reviews/scams/nager-date-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
