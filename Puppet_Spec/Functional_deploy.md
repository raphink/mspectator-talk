# Puppet-spec: Deploying functional tests

* Tests are run after catalog application
* Tests can be distributed via pluginsync (in the `spec/server/class`) directory of each module
* Tests can be distributed with `file` Puppet resources, optionally using the `spec::serverspec` defined resource type
