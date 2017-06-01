Querying Endpoints
==================

The OCD endpoints, individually filterable and searchable, can return precise results about government data. The API responds to standard URL queries: users can search the API using basic query strings and also advanced query patterns, including certain `Django URL Filters <https://github.com/miki725/django-url-filter>`_.

Query basics
~~~~~~~~~~~~

A question mark (?) always demarcates the beginning of a URL query string: 

      ::

          # Basic pattern
          http://ocd.datamade.us/events/?{query string}

          # Example query - all events in the Los Angeles timezone
          http://ocd.datamade.us/events/?timezone=America/Los_Angeles
        

Queries can contain multiple parameters. An ampersand (&) separates each parameter:

      ::

          # Basic pattern
          http://ocd.datamade.us/events/?{param1}&{param2}&{param3}

          # Example query - all canceled events in the Los Angeles timezone
          http://ocd.datamade.us/events/?timezone=America/Los_Angeles&status=cancelled

A few useful calls
~~~~~~~~~~~~~~~~~~

Filtering on data points
########################

Each entry displays a collection of fields and corresponding data, e.g., an event has a classification, description, start_time, etc. Any of these data points may form the basis of a URL query:

    ::

        # Basic pattern
        http://ocd.datamade.us/bills/{data point}={value}

        # Example query - all bills labeled as claims 
        http://ocd.datamade.us/bills/?classification=claim



Some fields contain arrays of data. Use a double underscore to separate the field names: 

    ::

        # Basic pattern
        http://ocd.datamade.us/bills/{name of array}__{desired subset}

        # Example query - all the bills processed by the Chicago City Council
        http://ocd.datamade.us/bills/?from_organization__name=Chicago%20City%20Council

And again, the API also accepts multiple parameters, separated by an ampersand (&):

    :: 

        # Filtering on more than one data point
        http://ocd.datamade.us/bills/?from_organization__name=Chicago%20City%20Council&classification=claim


*Note: type the spaces if a value has multiple words, e.g, Grants of Privilege. The API will automatically replace spaces with the correct encoding (“%20").*

Page
####

Most endpoints do not contain all entities on a single listing page. To navigate through all entries, run the “page” query:

      ::

          # Returns the second listing page within the bills endpoint
          http://ocd.datamade.us/bills/?page=2 

*Note: The boundaries endpoint is not paginated in this way. For now, this endpoint employs an offset + limit format. "Offset" refers to the index of the entity that is first displayed, and "limit" sets the number of entities viewable on each page.*

Sort
####


The “sort” call orders entities in an endpoint by a specific parameter, in either ascending or descending order:

    :: 

        # Returns bills sorted in alphanumeric order by title
        http://ocd.datamade.us/bills/?sort=title 

    ::

        # Returns bills in reverse alphanumeric order by title
        http://ocd.datamade.us/bills/?sort=-title 

Finding all data points
#######################

The listing page does not show all accessible data points: that is, some data points only appear on the detail page of an entry. Fortunately, API queries can simultaneously sift through data on both the listing and detail pages.


    ::

        # Returns bills with a latest action date of 2013-01-17 
        http://ocd.datamade.us/bills/?actions__date=2013-01-17

        # Returns bills in ascending order (oldest to newest) of their latest action date
        http://ocd.datamade.us/bills/?sort=actions__date

        # Returns the second page of bills from New York City Council
        # In descending order (newest to oldest) of the latest action date
        http://ocd.datamade.us/bills/?sort=-actions__date&from_organization__name=New%20York%20City%20Council&page=2

Djano queries
~~~~~~~~~~~~~

The OCD API also responds to `Django URL filters <https://github.com/miki725/django-url-filter>`_.

contains and icontains
######################

The “contains” parameter is particularly helpful. As the name suggests, the query returns all entries containing a specified string in a given field. The “icontains” parameter performs the same function, but for case insensitive searches.

    :: 

        # Returns all bills with titles that include “Zoning Reclassification”
        http://ocd.datamade.us/bills/?title__contains=Zoning%20Reclassification 


Get even more specific results: tack the two strings together.

    :: 

        # Return all Chicago City Council bills with titles that include “Zoning Reclassification” 
        # In descending order (newest to oldest) of the latest action date
        http://ocd.datamade.us/bills/?from_organization__name=Chicago%20City%20Council&title__contains=Zoning%20Reclassification&sort=-actions__date

Comparison operators
####################


The API supports a number of comparison operators: greater than (gt), less than (lt), greater than or equal to (gte), and less than or equal to (lte).

    :: 

        # Returns all bills with at least one action taken after January 1, 2013
        http://ocd.datamade.us/bills/?actions__date__gt=2013

        # Returns all bills with no actions taken after January 1, 2013
        http://ocd.datamade.us/bills/?actions__date__lt=2013

        # Returns bills with at least one action taken on or after January 1, 2013
        http://ocd.datamade.us/bills/?actions__date__gte=2013

        # Returns bills with at least one action taken on or before January 1, 2013
        http://ocd.datamade.us/bills/?actions__date__lte=2013 

exact
#####

The “exact” filter returns entities containing an exact value for a specified field. The “iexact” filter performs the same function, but for case insensitive searches.

    :: 

        # Return all bills proposed under the jurisdiction of Chicago City Government
        http://ocd.datamade.us/bills/?from_organization__jurisdiction__name__iexact=chicago%20City%20government

startswith and endswith
#######################

The “startswith” filter returns entities containing a value for a field that begins with a specified string. The “endswith” call does the same function for entity values that end with a specified string. The “istartswith” and “iendswith” calls perform the same function as their parent parameters, for for case insensitive searches.

    ::

        # Returns bills with titles that begin with the exact phrase “Rahm Emanuel”
        http://ocd.datamade.us/bills/?title__startswith=Rahm%20Emanuel

        # Returns bills with titles that end with the phrase “Rahm Emanuel” (insensitive of case)
        http://ocd.datamade.us/bills/?title__iendswith=rahm%20Emanuel 
