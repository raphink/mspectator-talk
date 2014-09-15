# Puppet-spec: Setting up Unit testing

* Tests achieved from catalog indirection terminii
* Plugins (terminii) deployed with pluginsync
* Setup done in `routes.yaml`:

        agent:
          catalog:
            # Either on the agent side
            terminus: rest_spec
            cache: yaml
        master:
          catalog:
            # Or on the master side
            terminus: compiler_spec

