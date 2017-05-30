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

a. To access the listing pages for a given endpoint, enter the following URL:

::

    ocd.datamade.us/{end_point_name}/

The endpoint name should be one of the following categories listed above. Example:

:: 

    ocd.datamade.us/events


