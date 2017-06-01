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

Independently filterable and searchable, the endpoints organize individual entries, each receiving a unique id, which points to detailed information about a specified instance of civic data. 

Elements of an Endpoint
~~~~~~~~~~~~~~~~~~~~~~~

An endpoint has two parts: (1) the **listing pages**, which contain general information on entities, and (2) the **detail pages**, which contain all available data on a given entity. Some entries also contain the names and ids of related entities stored in different endpoints.

    i. **Listing Page.** To access the listing page for an endpoint, enter a URL with the following pattern:

      ::

          ocd.datamade.us/{end point name}/

      The endpoint name should be one of the categories listed above. Example:

      :: 

          ocd.datamade.us/events

    ii. **Detail Page.** The listing page displays a collection of entries, and each entry receives a unique id that makes possible the entity detail page. To access a detail page, enter a URL with the following pattern: 

      :: 

          ocd.datamade.us/{id}/

      The unique identifier has two parts – a label indicative of the category, and a slug of randomized numbers and letters. Example: 

      ::

          ocd.datamade.us/ocd-event/fe2dde3c-b526-4abc-b5f0-7d62c6cd9b04/


Endpoint Details
~~~~~~~~~~~~~~~~

Bills
#####

The `bills endpoint <http://ocd.datamade.us/bills/>`_ contains information on individual pieces of legislation, including the classification, identifier, title, and subject of the bill. Each entry also provides the name and id of the organization that proposed the bill, the name and id of the bill jurisdiction, and the unique id of the bill itself.

Boundaries
##########

The `boundaries endpoint <http://ocd.datamade.us/boundaries/>`_ contains geographic information on many of the divisions tracked by the API, such as the Illinois congressional districts, wards, and precincts. Unlike the other endpoints, boundary entities do not receive an id, but rather a URL. Each entry on the boundaries listing page contains the URL for the boundary, the URL of the boundary set (the parent set of the specific boundary), and the name and id of the division the boundary describes. The boundary-specific detail page contains URLs for the simple shape of the boundary, centeroid, boundary set and shape, as well as coordinates on its bound box.

Divisions
#########

The `divisions endpoint <http://ocd.datamade.us/divisions/>`_ contains data on the various geographic divisions of federal, state, county, and local governments. These include but are not limited to court precincts, commission districts, school districts, congressional districts, counties, townships, cities, towns, villages, boroughs, etc. The division detail pages also contain the ids of all “children” divisions: for instance, the children of the `United States <http://ocd.datamade.us/ocd-division/country:us/>`_ are the individual states.

Events
######

The `events endpoint <http://ocd.datamade.us/events/>`_ contains information on meetings, hearings, and other gatherings of various governing bodies. The detail pages for each event also contain names and ids for all people, jurisdictions, organizations, and bills affiliated with the event.

Jurisdictions
#############

The `jurisdictions endpoint <http://ocd.datamade.us/jurisdictions/>`_ includes details on each individual governing body contained within the API. This includes: New York City, Chicago City, Miami-Dade County, Ferguson City Council, and Los Angeles County governments. 

Organizations
#############

The `organizations endpoint <http://ocd.datamade.us/organizations/>`_ includes entries for the various executive offices, legislative bodies, committees, and parties tracked by the API (e.g., Chicago City Council, Republican Party, etc). The listing page includes names and ids for all relevant jurisdictions and parent organizations. The detail pages for each organization also contain names, ids, term dates, and organizational positions for each member, as well as names and ids for all parent organizations, children organizations, and overarching jurisdictions and divisions.

People
######

The `people endpoint <http://ocd.datamade.us/people/>`_ contains detailed information on the members of each jurisdiction tracked by the API. The membership array on the people listing and detail pages includes relevant organization and jurisdiction names and ids.

Votes
#####

The `votes endpoint <http://ocd.datamade.us/votes/>`_ contains information about every motion made on every piece of legislation within each jurisdiction tracked by the OCD API. The listing and detail pages within the votes endpoint also contain the name and id of the bill being voted on, and the organization conducting the vote. The detail page for each vote also lists the name and id of every voter and how they voted.

Further Reading
~~~~~~~~~~~~~~~

More detailed information on the exact contents of listing and detail pages for endpoints can be found `here <http://docs.opencivicdata.org/en/latest/data/index.html>`_.
