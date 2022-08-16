Demo of New Relic Agent Dashboard
======================

**Introduce About New Relic Agent**

A ``New relic`` agent is a piece of software that you install on a host or in an application that sends performance data to New Relic. `New Relic`_ is a Software as a Service offering that focuses on performance and availability monitoring.

.. _New Relic: http://newrelic.com

**Dashboard of Host**
-----

**Example 1:** ``CPU Usage``

.. code:: bash

    SELECT latest(host.cpuPercent) FROM Metric WHERE `entityGuid` = 'MzU2NDQ4NnxJTkZSQXxOQXw2OTI2MTI1NzY3MDQ1Njg1ODI' TIMESERIES auto

.. image:: Images/01_cpu_usage.jpg
  :width: 400
  :alt: CPU Usage

**Example 2:** ``Network Traffic``

.. code:: bash

    SELECT latest(host.net.transmitBytesPerSecond) AS 'Transmit bytes per second', latest(host.net.receiveBytesPerSecond) AS 'Receive bytes per second' FROM Metric WHERE `entityGuid` = 'MzU2NDQ4NnxJTkZSQXxOQXw2OTI2MTI1NzY3MDQ1Njg1ODI' TIMESERIES auto

.. image:: Images/02_network_traffic.jpg
  :width: 400
  :alt: Network Traffic

.. list-table:: Title
   :widths: 50 50
   :header-rows: 1
   
  * - **Example 1:** ``CPU Usage``
    - **Example 2:** ``Network Traffic``
  * - Row 1, column 1
    -
  * - Row 2, column 1
    - .. image:: Images/02_network_traffic.jpg
        :width: 400
        :alt: Network Traffic
