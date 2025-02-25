OpenTelemetry Flask Tracing
===========================

|pypi|

.. |pypi| image:: https://badge.fury.io/py/opentelemetry-instrumentation-flask.svg
   :target: https://pypi.org/project/opentelemetry-instrumentation-flask/

This library builds on the OpenTelemetry WSGI middleware to track web requests
in Flask applications.

Installation
------------

::

    pip install opentelemetry-instrumentation-flask

Configuration
-------------

Exclude lists
*************
To exclude certain URLs from being tracked, set the environment variable ``OTEL_PYTHON_FLASK_EXCLUDED_URLS`` with comma delimited regexes representing which URLs to exclude.

For example,

::

    export OTEL_PYTHON_FLASK_EXCLUDED_URLS="client/.*/info,healthcheck"

will exclude requests such as ``https://site/client/123/info`` and ``https://site/xyz/healthcheck``.

You can also pass the comma delimited regexes to the ``instrument_app`` method directly:

.. code-block:: python

    FlaskInstrumentor().instrument_app(app, excluded_urls="client/.*/info,healthcheck")

References
----------

* `OpenTelemetry Flask Instrumentation <https://opentelemetry-python-contrib.readthedocs.io/en/stable/instrumentation/flask/flask.html>`_
* `OpenTelemetry Project <https://opentelemetry.io/>`_
* `OpenTelemetry Python Examples <https://github.com/open-telemetry/opentelemetry-python/tree/main/docs/examples>`_
