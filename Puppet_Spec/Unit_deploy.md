# Puppet-spec: Deploying unit tests

* On the master side:
  * Tests are located in the `spec/catalog/class` directory of the environment
  * Only the directories named after classes declared in the catalog are tested
  
* On the agent side:
  * Deploy tests using pluginsync
  * Tests are located in the `lib/spec/catalog/class` directory of each module
  * Only the directories named after classes declared in the catalog are tested
