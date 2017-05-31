Querying Endpoints
==================

Each of the endpoints can be individually filtered and searched to provide more specific results. While users can search the API using basic URL query strings, OCD also supports a handful of more advanced queries, including certain `Django URL Filters <https://github.com/miki725/django-url-filter>`_.

Query basics
~~~~~~~~~~~~

    i. URL query strings always begin with a question mark (?)

      ::

          http://ocd.datamade.us/bills/?{query string}
        
    ii. If queries contain multiple parameters, separated them with an ampersand (&)

      ::

          i.e. http://ocd.datamade.us/bills/?{param1}&{param2}&{param3}

