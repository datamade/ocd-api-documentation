.. ocd-api-documentation documentation master file, created by
   sphinx-quickstart on Tue May 30 15:43:07 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

=============================
Open Civic Data Documentation
=============================

Overview
========

The primary goal of the Open Civic Data API (OCD) is to provide users with comprehensive, filterable database for exploring government data. The API allows users to search through information on legislation, politicians, governing bodies and divisions in an effort to make governments more transparent and accountable. The API is filtered using standard url query strings and returns data in an easily scrapable JSON format. DataMade uses the API to power many of its open government tools, including Chicago Councilmatic and LA Metro, but the database contains information on thousands of districts nationwide. The tool was created to help everyday citizens better understand their local governments and empower them to hold officials accountable to their constituents. 

Requirements
============

The Open Civic Data API is readily accessible to anyone with an internet browser. It requires no special programs or installations to run. However, because results are presented in JSON format, it’s helpful to have some kind of JSON reader to organize the page in a more user-friendly way. (JSONview is a great extension for people using Chrome [https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc?hl=en] or Firefox [https://addons.mozilla.org/en-Us/firefox/addon/jsonview/])


.. toctree::
   :maxdepth: 2
   
   endpoints
   querying_endpoints


Indices and tables
------------------

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
