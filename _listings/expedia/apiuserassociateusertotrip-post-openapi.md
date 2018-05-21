---
swagger: "2.0"
x-collection-name: Expedia
x-complete: 0
info:
  title: Expedia Associate User To Trip
  description: Mobile API User Associate To Trip
  version: 0.0.1
host: apim.expedia.com
basePath: x/
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /api/flight/search:
    get:
      summary: Search
      description: Mobile API Flights
      operationId: flights-search
      x-api-path-slug: apiflightsearch-get
      parameters:
      - in: query
        name: arrivalAirport
        description: The three letter airport code to where the customer is going
      - in: query
        name: childTravelerAge
        description: childTravelerAge represents the age of a single child traveler
      - in: query
        name: correlationId
        description: Optional parameter to define a correlation between a hotel search
          and a flight search
      - in: query
        name: departureAirport
        description: The three letter airport code for where the customer is leaving
          from
      - in: query
        name: departureDate
        description: Date the customer wants to leave for their flight on, in ISO
          format
      - in: query
        name: featureOverride
        description: Optional field to specify a comma separated list of feature toggling
          flag names, use _ (underscore) ahead of flag name to disable feature ex,
          Flex,FlightSearchCacheGet,_FlightSearchCachePut
      - in: query
        name: infantSeatingInLap
        description: Set to true if infant(s) are without a reserved seat (in an adults
          lap)
      - in: query
        name: lccAndMerchantFareCheckoutAllowed
        description: flag to indicate whether lcc and merchant fares should be returned
          in search response
      - in: query
        name: maxOfferCount
        description: Maximum number of offers to return
      - in: query
        name: nonStopFlight
        description: 'Set to true to return only non stop flights in the search response '
      - in: query
        name: numberOfAdultTravelers
        description: 'Number of Adult Travelers (Default: 1)'
      - in: query
        name: prettyPrint
        description: Controls JSON response formatting
      - in: query
        name: returnDate
        description: Date the customer wants to return on
      - in: query
        name: showRefundableFlight
        description: 'Set to true to return only refundable(Free cancellation available)
          flights in the search response '
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Airports
      - Airplanes
      - Airlines
  /api/flight/trip/create:
    post:
      summary: Create A Trip
      description: Mobile API Flights Create Trip Operation
      operationId: flights-create-trip
      x-api-path-slug: apiflighttripcreate-post
      parameters:
      - in: formData
        name: fareFamilyCode
      - in: formData
        name: fareFamilyTotalPrice
      - in: formData
        name: mobileShoppingKey
        description: The mobile shopping key we are going to create a trip for
      - in: formData
        name: productKey
        description: The product key, obtained from /api/flight/search, we are going
          to create a trip for
      - in: formData
        name: qualifyAirAttach
        description: Whether to return a qualified air attach product for this trip
      - in: formData
        name: tripTitle
        description: The name of this itinerary as it will appear to customer service
          and in the itinerary list
      - in: formData
        name: withInsurance
        description: Whether to return the available insurance options for this trip
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Airports
      - Airplanes
      - Trips
      - Airlines
  /api/flight/trip/cardFee:
    post:
      summary: Get the credit card fee for a trip
      description: This api provides an accurate credit card fee that a user would
        have to pay when booking a trip.
      operationId: flights-trip-fee
      x-api-path-slug: apiflighttripcardfee-post
      parameters:
      - in: formData
        name: clientId
        description: Client Id
      - in: formData
        name: creditCardId
        description: This is a string that identifies the credit card that will be
          used to pay for the trip
      - in: formData
        name: tripId
        description: The id of the trip to get the credit card fee for
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Airports
      - Airplanes
      - Airlines
  /api/flight/details:
    get:
      summary: Details
      description: Mobile API Flight Details Operation
      operationId: flights-details
      x-api-path-slug: apiflightdetails-get
      parameters:
      - in: query
        name: arrivalAirport
        description: The three letter airport code for where the customer is going
      - in: query
        name: childTravelerAge
        description: childTravelerAge represents the age of a single child traveler
      - in: query
        name: departureAirport
        description: The three letter airport code for where the customer is leaving
          from
      - in: query
        name: departureDate
        description: Date the customer wants to leave for their flight on, in ISO
          format
      - in: query
        name: infantSeatingInLap
        description: Set to true if infant(s) are without a reserved seat (in an adults
          lap)
      - in: query
        name: numberOfAdultTravelers
        description: 'Number of Adult Travelers (Default: 1)'
      - in: query
        name: productKey
        description: A productKey, obtained from a call to flight search, within the
          past 20 minutes
      - in: query
        name: returnDate
        description: Date the customer wants to return on
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Airports
      - Airplanes
      - Airlines
  /api/flight/image:
    get:
      summary: Flight Image
      description: Mobile API Flight Image Operation
      operationId: flights-image
      x-api-path-slug: apiflightimage-get
      parameters:
      - in: query
        name: destinationCode
        description: The three letter airport code or metro code of the destination
      - in: query
        name: imageHeight
        description: Requested height of the image
      - in: query
        name: imageWidth
        description: Requested width of the image
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Airports
      - Airplanes
      - Images
      - Airlines
  /api/mobile/image:
    get:
      summary: Mobile Image
      description: Mobile API Flight Mobile Image Operation
      operationId: flights-mobile-image
      x-api-path-slug: apimobileimage-get
      parameters:
      - in: query
        name: imageCode
        description: image primary key, for example CAR:ECONOMY ACTIVITY:DISNEY DESTINATION:JFK
          DESTINATIONMOBILEWEB:JFK CARMOBILEWEB:MINI
      - in: query
        name: imageHeight
        description: Requested height of the image
      - in: query
        name: imageType
        description: type of image
      - in: query
        name: imageWidth
        description: Requested width of the image
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Airports
      - Airplanes
      - Images
      - Airlines
  /api/flight/airportDropDown:
    get:
      summary: Airport Dropdown
      description: Mobile API Flight Airport Dropdown Operation
      operationId: flights-airport-dropdown
      x-api-path-slug: apiflightairportdropdown-get
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Airports
      - Airplanes
      - Airlines
  /api/flight/checkout:
    post:
      summary: Mobile Flight Checkout
      description: Checkout a previously created flight trip, requiring payment fields,
        the trip id, and the passenger fields
      operationId: flights-checkout
      x-api-path-slug: apiflightcheckout-post
      parameters:
      - in: formData
        name: associatedFlightPassengers[0].birthDate
        description: Birth date of the associated flight passenger fields
      - in: formData
        name: associatedFlightPassengers[0].gender
        description: Gender of the associated flight passenger fields
      - in: formData
        name: associatedFlightPassengers[0].knownTravelerNumber
        description: knownTravelerNumber(PreCheckNumber) of the associated flight
          passenger fields
      - in: formData
        name: associatedFlightPassengers[0].passengerCategory
        description: :Passenger category of the associated flight passenger fields
      - in: formData
        name: associatedFlightPassengers[0].passportCountryCode
        description: Passport country code of the associated flight passenger fields
      - in: formData
        name: associatedFlightPassengers[0].seatPreference
        description: Seat preference of the associated flight passenger fields
      - in: formData
        name: associatedFlightPassengers[0].seats[0].arrivalAirportCode
        description: The arrival airport code for the selected seat of the associated
          flight passenger fields
      - in: formData
        name: associatedFlightPassengers[0].seats[0].departureAirportCode
        description: The departure airport code for the selected seat of the associated
          flight passenger fields
      - in: formData
        name: associatedFlightPassengers[0].seats[0].seatNumber
        description: Selected Seat Number of the associated flight passenger fields
      - in: formData
        name: associatedFlightPassengers[0].specialAssistanceOption
        description: Special assistance option for the associated flight passenger
          fields
      - in: formData
        name: associatedFlightPassengers[0].title
        description: Title of the associated flight passenger fields
      - in: formData
        name: associatedFlightPassengers[0].TSARedressNumber
        description: TSA redress number of the associated flight passenger fields
      - in: formData
        name: birthDate
        description: Birth date of the associated flight passenger fields
      - in: formData
        name: city
        description: The city of the travelers billing address
      - in: formData
        name: country
        description: The 3 letter country code of the travelers billing address
      - in: formData
        name: creditCardNumber
        description: The credit card number used for this booking, if checking out
          with a new card
      - in: formData
        name: cvv
        description: The CVV of the travelers credit card used for this booking
      - in: formData
        name: doIThinkImSignedIn
        description: As a client I am checking-out with the assumption that I am signed
          in
      - in: formData
        name: email
        description: Email address of the main flight passenger
      - in: formData
        name: expectedCardFee
        description: The expected credit card fee, as returned by the createTrip call
          in the validFormsOfPayment object for whatever credit card the user is paying
          with
      - in: formData
        name: expectedCardFeeCurrencyCode
        description: Three letter 4217 ISO currency code of the expected credit card
          fee
      - in: formData
        name: expectedFareCurrencyCode
        description: Three letter 4217 ISO currency code of the expected total price
      - in: formData
        name: expectedTotalFare
        description: The expected total price of the trip, matching exactly whatever
          the user last saw
      - in: formData
        name: expediaEmailOptIn
        description: If the main flight passenger wishes to opt out for Expedia emails
          or not
      - in: formData
        name: expirationDateMonth
        description: The expiration date month of the credit card used for this booking
      - in: formData
        name: expirationDateYear
        description: The 4 digit expiration date year of the credit card used for
          this booking
      - in: formData
        name: firstName
        description: The first name of the traveler
      - in: formData
        name: frequentFlyerDetails[0].flightAirlineCode
        description: Airline code for the flight to be booked
      - in: formData
        name: frequentFlyerDetails[0].frequentFlyerPlanAirlineCode
        description: Airline code for the airline whose frequent Flyer programme is
          to be used
      - in: formData
        name: frequentFlyerDetails[0].frequentFlyerPlanCode
        description: Plan code for Airline program
      - in: formData
        name: frequentFlyerDetails[0].membershipNumber
        description: User specific membership number for the frequent flyer programme
      - in: formData
        name: gender
        description: Gender of the associated flight passenger fields
      - in: formData
        name: knownTravelerNumber
        description: knownTravelerNumber(PreCheckNumber) of the associated flight
          passenger fields
      - in: formData
        name: lastName
        description: The last name of the traveler
      - in: formData
        name: mainFlightPassenger[0].email
        description: Email address of the main flight passenger
      - in: formData
        name: mainFlightPassenger[0].expediaEmailOptIn
        description: If the main flight passenger wishes to opt out for Expedia emails
          or not
      - in: formData
        name: mainFlightPassenger[0].password
        description: Password of the main flight passenger
      - in: formData
        name: mainFlightPassenger[0].phone
        description: Phone number of the main flight passenger
      - in: formData
        name: mainFlightPassenger[0].phoneCountryCode
        description: Country code of the phone of the main flight passenger
      - in: formData
        name: middleName
        description: The middle name of the traveler
      - in: formData
        name: nameOnCard
        description: The card holders name
      - in: formData
        name: omniturePartnerId
        description: Omniture partner identification string
      - in: formData
        name: passengerCategory
        description: :Passenger category of the associated flight passenger fields
      - in: formData
        name: passportCountryCode
        description: Passport country code of the associated flight passenger fields
      - in: formData
        name: password
        description: Password of the main flight passenger
      - in: formData
        name: phone
        description: Phone number of the main flight passenger
      - in: formData
        name: phoneCountryCode
        description: Country code of the phone of the main flight passenger
      - in: formData
        name: postalCode
        description: The postal code of the travelers billing address
      - in: formData
        name: prettyPrint
        description: If true, return JSON with tabs, spaces and newlines to be human
          readable
      - in: formData
        name: seatPreference
        description: Seat preference of the associated flight passenger fields
      - in: formData
        name: seats[0].arrivalAirportCode
        description: The arrival airport code for the selected seat of the Main flight
          passenger fields
      - in: formData
        name: seats[0].departureAirportCode
        description: The departure airport code for the selected seat of the Main
          flight passenger fields
      - in: formData
        name: seats[0].seatNumber
        description: Selected Seat Number of the Main flight passenger fields
      - in: formData
        name: sendEmailConfirmation
        description: Used to check if confirmation email needs to be sent or not
      - in: formData
        name: specialAssistanceOption
        description: Special assistance option for the associated flight passenger
          fields
      - in: formData
        name: state
        description: The state (or province) of the travelers billing address
      - in: formData
        name: storeCreditCardInUserProfile
        description: Indicates whether to save the credit card information as a stored
          credit card in the user profile
      - in: formData
        name: storedCreditCardId
        description: The GUID for the stored credit card information to be used for
          payment
      - in: formData
        name: streetAddress
        description: The street part of the credit card owners billing address
      - in: formData
        name: streetAddress2
        description: Apartment or suite number of the travelers billing address
      - in: formData
        name: suppressFinalBooking
        description: If true, do not actually charge for and book the trip, stop after
          creating the itinerary
      - in: formData
        name: tealeafTransactionId
        description: The unique transaction ID used in TeaLeaf PSR tracking
      - in: formData
        name: title
        description: Title of the associated flight passenger fields
      - in: formData
        name: tripId
        description: The trip ID of an existing trip, from /api/flight/trip/create
      - in: formData
        name: TSARedressNumber
        description: TSA redress number of the associated flight passenger fields
      - in: formData
        name: validateWithChildren
        description: Set this flag to true to enable child validation logic on the
          server
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Airports
      - Airplanes
      - Airlines
  /m/api/flight/trip/V2/create:
    post:
      summary: Create a trip for partner
      description: Creates a flight trip, passing a product key and all required fields.
      operationId: flights-checkout
      x-api-path-slug: mapiflighttripv2create-post
      parameters:
      - in: formData
        name: childTravelerAge[0]
        description: childTravelerAge represents the age of a single child traveler
      - in: formData
        name: infantSeatingInLap
        description: Set to true if infant(s) are without a reserved seat (in an adults
          lap)
      - in: formData
        name: numberOfAdultTravelers
        description: 'Number of Adult Travelers (Default: 1)'
      - in: formData
        name: productKey
        description: The product key we are going to create a trip for
      - in: formData
        name: tripTitle
        description: The name of this itinerary as it will appear to customer service
          and in the itinerary list
      - in: formData
        name: withInsurance
        description: Whether to return the available insurance options for this trip
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Airplanes
      - Airlines
  /api/flight/fareRules/{tripId}:
    get:
      summary: Fare Rules for the trip
      description: Air Fare Rule information of the trip created
      operationId: flights-fareRules
      x-api-path-slug: apiflightfarerulestripid-get
      parameters:
      - in: path
        name: tripId
        description: The trip ID of an existing trip, from /api/flight/trip/create
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Airports
      - Airplanes
      - Airlines
  /m/api/hotel/search:
    get:
      summary: Search
      description: |-
        Mobile API Hotels Search

        There are multiple successful responses for this operation.
        See the examples below for more information.
      operationId: hotels-search
      x-api-path-slug: mapihotelsearch-get
      parameters:
      - in: query
        name: airAttachQualificationCode
        description: Qualification code needed to get air attached hotel prices
      - in: query
        name: checkInDate
        description: Check in date in ISO format (yyyy-MM-dd)
      - in: query
        name: checkOutDate
        description: Check out date in ISO format (yyyy-MM-dd)
      - in: query
        name: city
        description: A string to identify the city to search
      - in: query
        name: correlationId
        description: Define a correlation between a hotel search and a flight search
      - in: query
        name: enableSponsoredListings
        description: Used to check for sponsoredListing
      - in: query
        name: filterAmenities
        description: Used to filter by amenities
      - in: query
        name: filterHotelName
        description: Hotel name used to filter the search results
      - in: query
        name: filterInventoryType
        description: A parameter to filter by inventory type
      - in: query
        name: filterPrice
        description: Used to filter by price, make sure it matches filterPriceBuckets
          if counts are desired
      - in: query
        name: filterPriceBuckets
        description: Used to define custom price filter buckets
      - in: query
        name: filterStarRatings
        description: Used to filter by star rating
      - in: query
        name: filterUnavailable
        description: Unavailable hotels will be removed from the response if set to
          true
      - in: query
        name: forceV2Search
        description: A flag to indicate whether the api should do a domain V2 search
          for the mobile app
      - in: query
        name: hgid
        description: If the hotel group ID parameter (hgid) is present it will take
          precedence over city, location or lat/long
      - in: query
        name: latitude
        description: Latitude to be used in combination with longitude for a coordinate
          search
      - in: query
        name: longitude
        description: Longitude to be used in combination with latitude for a coordinate
          search
      - in: query
        name: pageIndex
        description: The zero-based index of the page that you are requesting
      - in: query
        name: regionId
        description: An Expedia region ID to limit the search to a particular region
      - in: query
        name: resultsPerPage
        description: The number of hotels to return per page
      - in: query
        name: returnOpaqueHotels
        description: Return Opaque hotels if set to true
      - in: query
        name: room
        description: '[Optional if room1 field is specified] A Comma Separated Value
          of #OfAdults, followed by childrens ages for all children that are 18 and
          under'
      - in: query
        name: room1
        description: '[Optional if room field is specified] A Comma Separated Value
          of #OfAdults, followed by childrens ages for all children that are 18 and
          under'
      - in: query
        name: sortOrder
        description: Order to sort the list of hotels by Expedia picks, star rating,
          price and guest rating
      - in: query
        name: sortOrderFilter
        description: A post process sort order filter used to apply post sort order
          filtering to the sorted (sortOrder) search results
      - in: query
        name: sourceType
        description: Source type for the request
      - in: query
        name: tripId
        description: This field is optional and will default to the the POS default
          PriceType
      - in: query
        name: vipOnly
        description: Used to filter only VIP type hotels
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Hotels
  /m/api/hotel/offers:
    get:
      summary: Get Offers
      description: Mobile API Hotels Offers
      operationId: hotels-offers
      x-api-path-slug: mapihoteloffers-get
      parameters:
      - in: query
        name: checkInDate
        description: Checkin Date
      - in: query
        name: checkOutDate
        description: Checkout Date
      - in: query
        name: hotelId
        description: a 32-bit integer, currently between 1 through 7 digit number
      - in: query
        name: priceType
        description: Price Type, can only be TOTAL_PRICE or BASE_PRICE_ONLY
      - in: query
        name: room
        description: '[Optional if room1 field is specified] A Comma Separated Value
          of #OfAdults, followed by childrens ages for all children that are 18 and
          under'
      - in: query
        name: room1
        description: '[Optional if room field is specified] A Comma Separated Value
          of #OfAdults, followed by childrens ages for all children that are 18 and
          under'
      - in: query
        name: sourceType
        description: Source Type, for example mobilweb or mobileapp
      - in: query
        name: useCacheForAirAttach
        description: '[Optional] If this flag is set then the hotel offers (on a successful
          offers call) and the search fields will be cached'
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Hotels
  /m/api/hotel/offers/v3:
    get:
      summary: Get Offers
      description: Mobile API Hotels Offers
      operationId: hotels-offers
      x-api-path-slug: mapihoteloffersv3-get
      parameters:
      - in: query
        name: checkInDate
        description: Checkin Date
      - in: query
        name: checkOutDate
        description: Checkout Date
      - in: query
        name: hotelId
        description: a 32-bit integer, currently between 1 through 7 digit number
      - in: query
        name: priceType
        description: Price Type, can only be TOTAL_PRICE or BASE_PRICE_ONLY
      - in: query
        name: room
        description: '[Optional if room1 field is specified] A Comma Separated Value
          of #OfAdults, followed by childrens ages for all children that are 18 and
          under'
      - in: query
        name: room1
        description: '[Optional if room field is specified] A Comma Separated Value
          of #OfAdults, followed by childrens ages for all children that are 18 and
          under'
      - in: query
        name: sourceType
        description: Source Type, for example mobilweb or mobileapp
      - in: query
        name: useCacheForAirAttach
        description: '[Optional] If this flag is set then the hotel offers (on a successful
          offers call) and the search fields will be cached'
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Hotels
  /m/api/hotel/trip/create:
    post:
      summary: Create A Trip
      description: Mobile API Hotels Create Trip
      operationId: hotels-create-trip
      x-api-path-slug: mapihoteltripcreate-post
      parameters:
      - in: formData
        name: productKey
        description: The product key, obtained by calling /m/api/hotel/offers,  we
          are going to create a trip for
      - in: formData
        name: qualifyAirAttach
        description: '[Optional] Whether to return a qualified air attach product
          for this trip'
      - in: formData
        name: roomInfoFields[0].room
        description: 'A Comma Separated Value of #OfAdults, followed by childrens
          ages for all children that are 18 and under'
      - in: formData
        name: tripTitle
        description: '[Optional] The name of this itinerary as it will appear to customer
          service and in the itinerary list'
      - in: formData
        name: withInsurance
        description: '[Optional] Whether to return the available insurance options
          for this trip'
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Hotels
  /m/api/hotel/trip/checkout:
    post:
      summary: Checkout
      description: Mobile API Hotels Checkout
      operationId: hotels-checkout
      x-api-path-slug: mapihoteltripcheckout-post
      parameters:
      - in: formData
        name: bedTypeId
        description: Parameter that indicates the selected bed Type
      - in: formData
        name: checkInDate
        description: Check in date in ISO format (yyyy-MM-dd)
      - in: formData
        name: checkOutDate
        description: Check out date in ISO format (yyyy-MM-DD)
      - in: formData
        name: city
        description: The city of the travelers billing address
      - in: formData
        name: country
        description: The 3 letter country code of the travelers billing address
      - in: formData
        name: creditCardNumber
        description: The credit card number used for this booking, if checking out
          with a new card
      - in: formData
        name: cvv
        description: The CVV of the travelers credit card used for this booking
      - in: formData
        name: doIThinkImSignedIn
        description: As a client I am checking-out with the assumption that I am signed
          in
      - in: formData
        name: email
        description: This passengers email address
      - in: formData
        name: expectedCardFee
        description: The expected credit card fee, as returned by the createTrip call
          in the validFormsOfPayment object for whatever credit card the user is paying
          with
      - in: formData
        name: expectedCardFeeCurrencyCode
        description: Three letter 4217 ISO currency code of the expected total price
      - in: formData
        name: expectedFareCurrencyCode
        description: Three letter 4217 ISO currency code of the expected credit card
          fee
      - in: formData
        name: expectedTotalFare
        description: The expected total price of the trip, matching exactly whatever
          the user last saw
      - in: formData
        name: expediaEmailOptIn
        description: Whether to opt-in the users email to travel deals
      - in: formData
        name: expirationDateMonth
        description: The expiration date month of the credit card used for this booking
      - in: formData
        name: expirationDateYear
        description: The 4 digit expiration date year of the credit card used for
          this booking
      - in: formData
        name: firstName
        description: The first name of the traveler
      - in: formData
        name: lastName
        description: The last name of the traveler
      - in: formData
        name: middleName
        description: The middle name of the traveler
      - in: formData
        name: nameOnCard
        description: The card holders name
      - in: formData
        name: omniturePartnerId
        description: Omniture partner identification string
      - in: formData
        name: password
        description: The password provided by the expedia user
      - in: formData
        name: phone
        description: The phone number of the traveler
      - in: formData
        name: phoneCountryCode
        description: The country code of the phone number of the traveler
      - in: formData
        name: postalCode
        description: The postal code of the travelers billing address
      - in: formData
        name: prettyPrint
        description: If true, return JSON with tabs, spaces and newlines to be human
          readable
      - in: formData
        name: rooms
        description: A list of room preferences to be applied to the rooms being booked
      - in: formData
        name: rooms[0].accessibilityOptionIds
        description: A Comma Separated Value of accessibility option Ids
      - in: formData
        name: rooms[0].specialRequests
        description: A text field for special requests
      - in: formData
        name: sendEmailConfirmation
        description: Used to check if confirmation email needs to be sent or not
      - in: formData
        name: state
        description: The state (or province) of the travelers billing address
      - in: formData
        name: storeCreditCardInUserProfile
        description: Indicates whether to save the credit card information as a stored
          credit card in the user profile
      - in: formData
        name: storedCreditCardId
        description: The GUID for the stored credit card information to be used for
          payment
      - in: formData
        name: streetAddress
        description: The street part of the credit card owners billing address
      - in: formData
        name: streetAddress2
        description: Apartment or suite number of the travelers billing address
      - in: formData
        name: suppressFinalBooking
        description: If true, do not actually charge for and book the trip, stop after
          creating the itinerary
      - in: formData
        name: tealeafTransactionId
        description: The unique transaction ID used in TeaLeaf PSR tracking
      - in: formData
        name: tripId
        description: The trip ID of an existing trip, from /m/api/hotel/trip/create
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Hotels
  /m/api/hotel/trip/V2/checkout:
    post:
      summary: Hotel Checkout With JSON Request Body
      description: Mobile API Hotel Checkout V2
      operationId: checkoutV2
      x-api-path-slug: mapihoteltripv2checkout-post
      parameters:
      - in: body
        name: body
        description: JSON body with all the fields required for a Hotel checkout
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Hotels
  /m/api/hotel/trip/checkoutfields:
    get:
      summary: Get Required Checkout Fields
      description: Service that returns the fields that are required or optional for
        a given point of sale.
      operationId: hotels-checkout-fields
      x-api-path-slug: mapihoteltripcheckoutfields-get
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Hotels
  /m/api/hotel/trip/cancelEnquiry:
    get:
      summary: Cancel Enquiry
      description: Cancel Enquiry for hotel, pass in itinerary id, email address of
        trip owner.
      operationId: hotels-cancel-enquiry
      x-api-path-slug: mapihoteltripcancelenquiry-get
      parameters:
      - in: query
        name: emailAddress
        description: Email address of the traveler
      - in: query
        name: itineraryId
        description: Itinerary containing trip to cancel
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Hotels
  /m/api/hotel/trip/V2/cancelEnquiry:
    get:
      summary: Cancel Enquiry
      description: Cancel Enquiry for hotel, pass in itinerary id, email address of
        trip owner.
      operationId: hotels-cancel-enquiry
      x-api-path-slug: mapihoteltripv2cancelenquiry-get
      parameters:
      - in: query
        name: emailAddress
        description: Email address of the traveler
      - in: query
        name: itineraryId
        description: Itinerary containing trip to cancel
      - in: query
        name: orderLineGUIDs
        description: Comma separated order line guids
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Hotels
  /m/api/hotel/product:
    get:
      summary: Product
      description: Hotel Product
      operationId: hotels-product
      x-api-path-slug: mapihotelproduct-get
      parameters:
      - in: query
        name: opaqueProduct
        description: Set to true if the product key is an opaque hotel product key
      - in: query
        name: productKey
        description: The product key of the offer, obtained by calling /m/api/hotel/offers
      - in: query
        name: roomOccupants[0].childGuestAge
        description: represents the age of a single child guest staying in this room
      - in: query
        name: roomOccupants[0].numberOfAdultGuests
        description: 'Number of adults staying in this room (default: 1)'
      - in: query
        name: sourceType
        description: Source type for the request
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Hotels
  /m/api/hotel/info:
    get:
      summary: Info
      description: Hotel Information
      operationId: hotels-info
      x-api-path-slug: mapihotelinfo-get
      parameters:
      - in: query
        name: hotelId
        description: Hotel Id usually 5 digits
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Hotels
  /m/api/hotel/trip/cancel:
    post:
      summary: Cancel Trip
      description: Hotel Trip Cancellation
      operationId: hotels-trip-cancel
      x-api-path-slug: mapihoteltripcancel-post
      parameters:
      - in: formData
        name: emailAddress
        description: Email address of the traveler
      - in: formData
        name: itineraryId
        description: Itinerary id of the trip to cancel
      - in: formData
        name: sendConfirmationEmail
        description: Email the traveler after cancellation or not
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Hotels
  /m/api/hotel/rooms/cancel:
    post:
      summary: Cancel Room
      description: Hotel Room Cancellation
      operationId: hotels-room-cancel
      x-api-path-slug: mapihotelroomscancel-post
      parameters:
      - in: formData
        name: orderLineGUIDs
        description: The list of order line guids
      - in: formData
        name: orderNumber
        description: The order number ( returned by OMS ) associated with the trip
      - in: formData
        name: tripId
        description: The trip ID ( returned while checkout ) associated with the trip
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Hotels
  /m/api/trip/calculatePoints:
    post:
      summary: Points Conversion
      description: |-
        Converts from a given currency amount to the equivalent in rewards points.
        [Note: Works only if the User is signed-in and is the owner of the trip.]
      operationId: hotels-trip-calculate
      x-api-path-slug: mapitripcalculatepoints-post
      parameters:
      - in: formData
        name: amount
        description: The amount the user would want to convert to points
      - in: formData
        name: programName
        description: The Rewards program name
      - in: formData
        name: rateId
        description: The rate id to use for this conversion
      - in: formData
        name: tripId
        description: The trip ID of an existing trip, from /api/packages/createTrip
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Trips
  /getpackages/v1:
    get:
      summary: Get Packages
      description: Gets packages and supports changed flights and hotels for flexible
        shopping.
      operationId: get-packages
      x-api-path-slug: getpackagesv1-get
      parameters:
      - in: query
        name: adultsPerRoom[1]
        description: How many adults will stay in the given room
      - in: query
        name: destination
        description: The userss search string
      - in: query
        name: destinationId
        description: Region ID of the origin or destination
      - in: query
        name: fromDate
        description: The date the customer wants to leave the origin
      - in: query
        name: ftla
        description: TLA (airport code or metrocode) for the origin (ftla) or destination
          (ttla)
      - in: query
        name: numberOfRooms
        description: How many hotel rooms you want
      - in: query
        name: origin
        description: The users search string
      - in: query
        name: originId
        description: Region ID of the origin or destination
      - in: query
        name: packagePIID
        description: Taken from a previous package response
      - in: query
        name: packageTripType
        description: i
      - in: query
        name: packageType
        description: Supports different views of F+H package
      - in: query
        name: pageType
        description: Only for change hotel
      - in: query
        name: searchProduct
        description: i
      - in: query
        name: toDate
        description: The date the customer wants to leave the destination
      - in: query
        name: ttla
        description: TLA (airport code or metrocode) for the origin (ftla) or destination
          (ttla)
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Packages
  /api/packages/hotelOffers:
    get:
      summary: Get Package Offers
      description: Mobile API Packages
      operationId: packages-offers
      x-api-path-slug: apipackageshoteloffers-get
      parameters:
      - in: query
        name: checkInDate
        description: Date the traveler will be checking in to their hotel
      - in: query
        name: checkOutDate
        description: Date the traveler will be checking out of their hotel
      - in: query
        name: childTravelerAge
        description: childTravelerAge represents the age of a single child traveler
      - in: query
        name: infantSeatingInLap
        description: Set to true if infant(s) are without a reserved seat (in an adults
          lap)
      - in: query
        name: numberOfAdultTravelers
        description: 'Number of Adult Travelers (Default: 1)'
      - in: query
        name: productKey
        description: The product ID (piid) of the package you would like to get hotel
          offers for
      - in: query
        name: ratePlanCode
        description: Rate Plan Code of the selected hotel offer
      - in: query
        name: roomTypeCode
        description: Room Type Code of the selected hotel offer
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Packages
      - Offers
      - Hotels
  /api/packages/createTrip:
    post:
      summary: Create A Trip
      description: Mobile API Packages Create Trip operation
      operationId: packages-create-trip
      x-api-path-slug: apipackagescreatetrip-post
      parameters:
      - in: formData
        name: destinationId
        description: stubbed
      - in: formData
        name: productKey
        description: The product ID (piid) of the package you would like to get hotel
          offers for
      - in: formData
        name: roomOccupants[0].childGuestAge
        description: represents the age of a single child guest staying in this room
      - in: formData
        name: roomOccupants[0].infantsInSeat
        description: Any infants in seat
      - in: formData
        name: roomOccupants[0].numberOfAdultGuests
        description: 'Number of adults staying in this room (default: 1)'
      - in: formData
        name: roomOccupants[0].seniorCount
        description: 'Number of seniors staying in this room (default: 0)'
      - in: formData
        name: tripName
        description: stubbed
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Packages
  /api/packages/checkout:
    post:
      summary: Checkout
      description: Mobile API Packages Checkout
      operationId: packages-checkout
      x-api-path-slug: apipackagescheckout-post
      parameters:
      - in: formData
        name: city
        description: The city of the travelers billing address
      - in: formData
        name: country
        description: The 3 letter country code of the travelers billing address
      - in: formData
        name: creditCardNumber
        description: The credit card number used for this booking, if checking out
          with a new card
      - in: formData
        name: cvv
        description: The CVV of the travelers credit card used for this booking
      - in: formData
        name: doIThinkImSignedIn
        description: As a client I am checking-out with the assumption that I am signed
          in
      - in: formData
        name: expectedCardFee
        description: The expected credit card fee, as returned by the createTrip call
          in the validFormsOfPayment object for whatever credit card the user is paying
          with
      - in: formData
        name: expectedCardFeeCurrencyCode
        description: Three letter 4217 ISO currency code of the expected total price
      - in: formData
        name: expectedFareCurrencyCode
        description: Three letter 4217 ISO currency code of the expected credit card
          fee
      - in: formData
        name: expectedTotalFare
        description: The expected total price of the trip, matching exactly whatever
          the user last saw
      - in: formData
        name: expirationDateMonth
        description: The expiration date month of the credit card used for this booking
      - in: formData
        name: expirationDateYear
        description: The 4 digit expiration date year of the credit card used for
          this booking
      - in: formData
        name: flight[0].associatedFlightPassengers[0].birthDate
        description: Birth date of the associated flight passenger fields
      - in: formData
        name: flight[0].associatedFlightPassengers[0].gender
        description: Gender of the associated flight passenger fields
      - in: formData
        name: flight[0].associatedFlightPassengers[0].knownTravelerNumber
        description: knownTravelerNumber(PreCheckNumber) of the associated flight
          passenger fields
      - in: formData
        name: flight[0].associatedFlightPassengers[0].passengerCategory
        description: :Passenger category of the associated flight passenger fields
      - in: formData
        name: flight[0].associatedFlightPassengers[0].passportCountryCode
        description: Passport country code of the associated flight passenger fields
      - in: formData
        name: flight[0].associatedFlightPassengers[0].seatPreference
        description: Seat preference of the associated flight passenger fields
      - in: formData
        name: flight[0].associatedFlightPassengers[0].specialAssistanceOption
        description: Special assistance option for the associated flight passenger
          fields
      - in: formData
        name: flight[0].associatedFlightPassengers[0].title
        description: Title of the associated flight passenger fields
      - in: formData
        name: flight[0].associatedFlightPassengers[0].TSARedressNumber
        description: TSA redress number of the associated flight passenger fields
      - in: formData
        name: flight[0].mainFlightPassenger[0].email
        description: Email address of the main flight passenger
      - in: formData
        name: flight[0].mainFlightPassenger[0].expediaEmailOptIn
        description: If the main flight passenger wishes to opt out for Expedia emails
          or not
      - in: formData
        name: flight[0].mainFlightPassenger[0].password
        description: Password of the main flight passenger
      - in: formData
        name: flight[0].mainFlightPassenger[0].phone
        description: Phone number of the main flight passenger
      - in: formData
        name: flight[0].mainFlightPassenger[0].phoneCountryCode
        description: Country code of the phone of the main flight passenger
      - in: formData
        name: hotel[0].bedTypeId
        description: Indicates the selected bed Type
      - in: formData
        name: hotel[0].primaryContactFullName
        description: Full name of the person who will be checking in
      - in: formData
        name: nameOnCard
        description: The card holders name
      - in: formData
        name: omniturePartnerId
        description: Omniture partner identification string
      - in: formData
        name: postalCode
        description: The postal code of the travelers billing address
      - in: formData
        name: sendEmailConfirmation
        description: Used to check if confirmation email needs to be sent or not
      - in: formData
        name: state
        description: The state (or province) of the travelers billing address
      - in: formData
        name: storeCreditCardInUserProfile
        description: Indicates whether to save the credit card information as a stored
          credit card in the user profile
      - in: formData
        name: storedCreditCardId
        description: The GUID for the stored credit card information to be used for
          payment
      - in: formData
        name: streetAddress
        description: The street part of the credit card owners billing address
      - in: formData
        name: streetAddress2
        description: Apartment or suite number of the travelers billing address
      - in: formData
        name: tealeafTransactionId
        description: The unique transaction ID used in TeaLeaf PSR tracking
      - in: formData
        name: tripId
        description: The trip ID of an existing trip, from /api/packages/createTrip
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Packages
  /api/m/trip/coupon:
    post:
      summary: Apply Coupon
      description: Mobile API Packages Apply Coupon
      operationId: packages-apply-coupon
      x-api-path-slug: apimtripcoupon-post
      parameters:
      - in: formData
        name: coupon.code
        description: Coupon Code
      - in: formData
        name: coupon.instanceId
        description: Instance ID
      - in: formData
        name: coupon.name
        description: Coupon Name
      - in: formData
        name: tripId
        description: The tripId we are going to apply the coupon to
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Airports
      - Airplanes
      - Coupons
      - Airlines
  /api/m/trip/remove/coupon:
    post:
      summary: Remove Coupon
      description: Mobile API Packages Remove Coupon
      operationId: packages-remove-coupon
      x-api-path-slug: apimtripremovecoupon-post
      parameters:
      - in: formData
        name: tripId
        description: The tripId we are going to apply the coupon to
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Airports
      - Airplanes
      - Coupons
      - Airlines
  /api/trips:
    get:
      summary: Get Trips
      description: Mobile API Trips
      operationId: trips-search
      x-api-path-slug: apitrips-get
      parameters:
      - in: query
        name: filterBookingStatus
        description: An optional parameter to filter by booking status
      - in: query
        name: filterLineOfBusiness
        description: An optional parameters to filter by line of business
      - in: query
        name: filterTimePeriod
        description: An optional parameter to filter by time period
      - in: query
        name: getCachedDetails
        description: Optionally get full details for the first N trips
      - in: query
        name: sort
        description: An optional parameter to sort by date
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Search
  /api/trips/{tripId}:
    get:
      summary: Trips by tripId
      description: Mobile API Trips
      operationId: trips-search-id
      x-api-path-slug: apitripstripid-get
      parameters:
      - in: query
        name: currencyCode
        description: Currency parameter
      - in: query
        name: decimalPlaceCount
        description: Decimal place count for the expected amount
      - in: query
        name: decorator
        description: Nullifies complex elements of a Trip with exception of Price
          related elements and their parents
      - in: query
        name: email
        description: To pull a guest itinerary specify the email address associated
          with the trip
      - in: query
        name: expectedAmount
        description: Expected Amount during car cancellation
      - in: path
        name: tripId
        description: The trip ID
      - in: query
        name: useCache
        description: An optional flag to make a cached read trip call
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Search
      - Trips
  /api/trips/{tripId}/updateTripNameDescription:
    post:
      summary: Update Trip Name and Description
      description: Mobile API Trips update trip name and description operation
      operationId: trips-update-trip
      x-api-path-slug: apitripstripidupdatetripnamedescription-post
      parameters:
      - in: path
        name: tripId
        description: Trip ID
      - in: formData
        name: tripname
        description: The name of the trip
      - in: formData
        name: tripnote
        description: The comments of the trip
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Search
      - Trips
  /api/users/{userId}/trips/{tripId}:
    get:
      summary: (Internal Only)
      description: (Internal Only) Retrieve trip (tripId) for given customer (userId)
      operationId: trips-user-trips
      x-api-path-slug: apiusersuseridtripstripid-get
      parameters:
      - in: query
        name: currencyCode
        description: currency paramater
      - in: query
        name: decimalPlaceCount
        description: Decimal place count for the expected amount
      - in: query
        name: decorator
        description: Nullifies complex elements of a Trip with exception of Price
          related elements and their parents
      - in: query
        name: email
        description: To pull a guest itinerary specify the email address associated
          with the trip
      - in: query
        name: expectedAmount
        description: Expected Amount during car cancellation
      - in: path
        name: tripId
        description: Trip ID
      - in: query
        name: useCache
        description: An optional flag to make a cached read trip call
      - in: path
        name: userId
        description: User ID
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Users
  /api/users/{userId}/trips:
    get:
      summary: (Internal Only)
      description: (Internal Only) Returns array of trips for passed userId
      operationId: trips-by-user-id
      x-api-path-slug: apiusersuseridtrips-get
      parameters:
      - in: path
        name: userId
        description: User ID
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Users
  /m/api/rails/trip/cardFee:
    post:
      summary: Get the credit card fee for a trip
      description: This api provides an accurate credit card fee that a user would
        have to pay when booking a trip.
      operationId: rails-trip-fee
      x-api-path-slug: mapirailstripcardfee-post
      parameters:
      - in: formData
        name: clientId
        description: Client Id
      - in: formData
        name: creditCardId
        description: This is a string that identifies the credit card that will be
          used to pay for the trip
      - in: formData
        name: tdoToken
        description: This is a string that identifies the ticket delivery option that
          will be used for the trip
      - in: formData
        name: tripId
        description: The id of the trip to get the credit card fee for
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Trips
  /m/api/rails/trip/checkout:
    post:
      summary: Rails Checkout With JSON Request Body
      description: Mobile API Rails Checkout
      operationId: rails-cko
      x-api-path-slug: mapirailstripcheckout-post
      parameters:
      - in: body
        name: body
        description: JSON body with all the fields required for a Rails checkout
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Trains
      - Rails
  /api/user/sign-in:
    post:
      summary: User Sign-In
      description: Mobile API User Sign-In
      operationId: signin-user
      x-api-path-slug: apiusersignin-post
      parameters:
      - in: formData
        name: email
        description: Email Address
      - in: formData
        name: firstTimeSigin
        description: Boolean to indicate if this is a first time sign-in
      - in: formData
        name: guestLoginWithItin
        description: When logging in with an Itin Number and Email set this field
          to True
      - in: formData
        name: includeFullPaymentProfile
      - in: formData
        name: itinNumber
        description: The Itinerary Number can be used instead of a password to authenticate
          the user
      - in: formData
        name: password
        description: User Password
      - in: formData
        name: profileOnly
        description: If true, dont provide username/password fields and just re-retrieve
          the currently signed on users profile
      - in: formData
        name: profileTypes
        description: This is a comma-separated list of profile types to retrieve when
          the login is processed
      - in: formData
        name: retrieveCoupons
        description: Whether to include user coupons in the response
      - in: formData
        name: staySignedIn
        description: Sign Me In checkbox
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Users
  /api/user/profile:
    get:
      summary: Profile
      description: Mobile API User Profile
      operationId: profile-user
      x-api-path-slug: apiuserprofile-get
      parameters:
      - in: query
        name: profileTypes
        description: This is a comma-separated list of profile types to retrieve when
          the login is processed
      - in: query
        name: retrieveCoupons
        description: Whether to include user coupons in the response
      - in: query
        name: tuid
        description: The tuid of the user/account whose profile you would like
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Users
  /api/user/create:
    post:
      summary: Create User
      description: Mobile API User Create
      operationId: create-user
      x-api-path-slug: apiusercreate-post
      parameters:
      - in: formData
        name: email
        description: Users email address
      - in: formData
        name: enrollInLoyalty
        description: Whether to enroll the user in loyalty
      - in: formData
        name: expediaEmailOptIn
        description: Whether to opt-in the users email to travel deals
      - in: formData
        name: firstName
        description: Users first name
      - in: formData
        name: lastName
        description: Users last name
      - in: formData
        name: middleName
        description: Users middle name
      - in: formData
        name: password
        description: Users password
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Users
  /api/user/update-traveler:
    post:
      summary: Update
      description: Mobile API User Update Traveler
      operationId: update-traveler
      x-api-path-slug: apiuserupdatetraveler-post
      parameters:
      - in: formData
        name: birthDate
        description: TSA required field; passengers birth date
      - in: formData
        name: email
        description: This passengers email address
      - in: formData
        name: expediaEmailOptIn
        description: Whether to opt-in the users email to travel deals
      - in: formData
        name: firstName
        description: The first name of the traveler
      - in: formData
        name: gender
        description: TSA required field, MALE or FEMALE
      - in: formData
        name: knownTravelerNumber
        description: Passengers knownTravelerNumber(PreCheckNumber), a 9 digit number
      - in: formData
        name: lastName
        description: The last name of the traveler
      - in: formData
        name: middleName
        description: The middle name of the traveler
      - in: formData
        name: passengerCategory
        description: The passengers category
      - in: formData
        name: passportCountryCode
        description: Passport country, UPPERCASE three letter country code
      - in: formData
        name: password
        description: The password provided by the Expedia user
      - in: formData
        name: phone
        description: The phone number of the traveler
      - in: formData
        name: phoneCountryCode
        description: The country code of the phone number of the traveler
      - in: formData
        name: seatPreference
        description: Passengers seat preference
      - in: formData
        name: specialAssistanceOption
        description: Special assistance choice
      - in: formData
        name: title
        description: Title of passenger
      - in: formData
        name: TSARedressNumber
        description: Passengers TSA redress number, which is, in theory a 7 digit
          number
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Users
  /api/user/associateUserToTrip:
    post:
      summary: Associate User To Trip
      description: Mobile API User Associate To Trip
      operationId: user-associate-to-trip
      x-api-path-slug: apiuserassociateusertotrip-post
      parameters:
      - in: formData
        name: foo
        description: stubbed
      responses:
        200:
          description: OK
      tags:
      - Travel
      - Search
      - Trips
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---