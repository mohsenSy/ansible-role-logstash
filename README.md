logstash
=========

A simple ansible role to install logstash server

Requirements
------------

No special requirements for this role to run

Role Variables
--------------

* **LOGSTASH_INPUTS**: An array of arrays which defines each input type.

  Each array has the following fields:
  * if: specifies a condition which must be met to use this input (optional)
  * name: The name of the input such as filebeat, packetbeat etc... (required)
  * options: An array of options defined for the input type, each element is a structure (optional)
    which contains two fields:
      * name: The name of the option
      * value: The value for the option.

  If no input is specified then stdin is used.
* **LOGSTASH_OUTPUTS**: An array of arrays which defines each output type.

    Each array has the following fields:
    * if: specifies a condition which must be met to use this output (optional)
    * name: The name of the output such as elasticsearch, statsd etc... (required)
    * options: An array of options defined for the output type, each element is a structure (optional)
      which contains two fields:
        * name: The name of the option
        * value: The value for the option.

    If no output is specified then stdout is used.
* **LOGSTASH_FILTERS**: An array of arrays which defines each filter used in the pipeline

  Each array has the following fields:
  * if: specifies a condition which must be met to use this filter (optional)
  * name: The name of the filter such as grok, mutate, geoip etc... (required)
  * options: An array of options defined for the filter type, each element is a structure (optional)
    which contains two fields:
      * name: The name of the option
      * value: The value for the option.

  This array is optional and does not have a default value

Dependencies
------------

{ role: mohsenSy.java, JAVA_VERSION: 8}

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: mohsenSy.logstash }

License
-------

BSD

Author Information
------------------

If you have any question please contact me on

[twitter](https://twitter.com/mouhsen_ibrahim)

[linkedin](https://linkedin.com/in/mohsen-ibrahim-670b13112/)

email mohsen47@hotmail.co.uk
