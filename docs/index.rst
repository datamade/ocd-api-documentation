.. ocd-api-documentation documentation master file, created by
   sphinx-quickstart on Tue May 30 15:43:07 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

=================================
Open Civic Data API Documentation
=================================

Overview
========

The Open Civic Data (OCD) API makes governments more transparent and accountable by providing a comprehensive, filterable library of government data. With this tool, everyday citizens can better understand local governments, track the legislative process, and hold officials accountable. 

Users can conveniently explore information on legislation, politicians, governing bodies, and divisions. The API responds to standard URL query strings, and it returns data in an easily interpretable and scrapable JSON format. 

`DataMade <https://datamade.us/>`_ uses the API to power many of its open government tools, including `Chicago <https://chicago.councilmatic.org/>`_, `NYC <https://nyc.councilmatic.org/>`_, and `Los Angeles Metro <https://boardagendas.metro.net/>`_ Councilmatics, but the database contains information on thousands of districts nationwide. 

Requirements
============

Anyone with an internet browser can readily access the Open Civic Data API. It requires no special programs or installations. The API, however, presents results in JSON. Thus, a JSON reader of some kind can help organize the page into a user-friendly, human-readable format. (JSONview, for instance, has an exceptional extension for `Chrome <https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc?hl=en>`_ or `Firefox <https://addons.mozilla.org/en-Us/firefox/addon/jsonview/>`_ users.)


Learn more
==========

The following sections give a high-level overview of the OCD endpoints (i.e., the categories of civic data on the API) and walk through the process of querying the OCD library for specific results.

.. toctree::
   :maxdepth: 2
   
   endpoints
   querying_endpoints

