Endpoints
=========

The API contains eight different types of civic data. A unique endpoint represents each category:

* bills

* boundaries

* divisions

* events

* jurisdictions

* organizations

* people

* votes

Independently filterable and searchable, the endpoints organize individual entries, each receiving a unique id. Displaying an entry reveals detailed information about a specified instance of civic data. 

Elements of an Endpoint
~~~~~~~~~~~~~~~~~~~~~~~

Each endpoint has two parts: (1) the listing pages, which contain general information on each entity, and (2) the detail pages, which contain all available data on a given entity. Some entries also contain the names and ids of related entities stored in different endpoints.

a. To access the listing page for a given endpoint, enter the following URL:

::

    ocd.datamade.us/{end_point_name}/

The endpoint name should be one of the following categories listed above. Example:

:: 

    ocd.datamade.us/events

b. Each entity displayed on the listing page is assigned a unique id that can be used to access the entity’s detail page. To access a detail page, enter the following URL: 

:: 

    ocd.datamade.us/{id}/

The unique identifier has two parts: a label indicative of the category, and a slug of randomized numbers and letters. Example: 

::

    ocd.datamade.us/ocd-event/fe2dde3c-b526-4abc-b5f0-7d62c6cd9b04/


Endpoint Details
~~~~~~~~~~~~~~~~

Bills (http://ocd.datamade.us/bills/)

The bills library contains information on individual pieces of legislation. The name and id of the organization that proposed the each bill can also be found on both the listing and detail pages. The listing page also contains the name and id of the bill’s specific jurisdiction.

Boundaries (http://ocd.datamade.us/boundaries/)

The boundaries endpoint contains geographic information on many of the divisions tracked by the API, primarily Illinois congressional districts, wards and precincts. Unlike the other endpoints, boundary entities aren’t assigned an id, but rather a url. Each entry on the boundaries listing page contains the url for the specific boundary, the url of the boundary set (the parent set of the specific boundary), and the name and id of the division the boundary describes. The boundary-specific detail page contains urls for the boundary’s simple shape, centeroid, boundary set and shape, as well as coordinates on its bound box.

Divisions (http://ocd.datamade.us/divisions/)

The divisions library contains data on the various geographic divisions of federal, state, county and local governments. These include but are not limited to court precincts, commission districts, school districts, congressional districts, counties, townships, cities, towns, villages, boroughs, etc. The division detail pages also contain the ids of all “children” divisions. For instance, the children of the United States [http://ocd.datamade.us/ocd-division/country:us/] are the individual states.

Events (http://ocd.datamade.us/events/)

The events endpoint contains information on meetings, hearings and other gatherings of various governing bodies. The detail pages for each event also contain names and ids for all people, jurisdictions, organizations and bills affiliated with the event.

Jurisdictions (http://ocd.datamade.us/jurisdictions/)

The jurisdictions endpoint includes details on each individual governing body contained within the API. (Chicago city government, Miami-Dade County government, Ferguson City Council, etc.) 

Organizations (http://ocd.datamade.us/organizations/)

The organizations endpoint includes entries for the various executive offices, legislative bodies, committees and parties tracked by the API. (Chicago City Council, Republican Party, etc.) The listing page includes names and ids for all relevant jurisdictions and parent organizations. The detail pages for each organization also contain names, ids, term dates and organizational positions for each member, as well as names and ids for all parent organizations, children organizations, and overarching jurisdictions and divisions.

People (http://ocd.datamade.us/people/)

The people endpoint contains detailed information on the members of each jurisdiction tracked by the API The membership array on the people listing and detail pages includes relevant organization and jurisdiction names and ids.

Votes (http://ocd.datamade.us/votes/)

The votes endpoint contains information about every motion made on every piece of legislation within each jurisdiction tracked by the OCD API. The listing and detail pages within the votes endpoint also contain the name and id of the bill being voted on, and the organization conducting the vote. The detail page for each vote also lists the name and id of every voter and how they voted.



