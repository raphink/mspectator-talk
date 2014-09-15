# Puppet-spec: MCollective agent

* Communicates with distant nodes
* Sends action and values to `specinfra` check commands
* Does not implement `serverspec` syntax
* Returns `true`/`false`
* Uses MCollective as transport (instead of SSH)

Examples:

    @@@ Shell
    $ mco rpc spec check action=user values=rpinson
    $ mco rpc spec check action=file values=/etc/passwd
    $ mco rpc spec check action=resolvable values=google.fr,A
    $ mco rpc spec check action=listening values=80
    $ mco rpc spec check action=process values=mcollectived
    $ mco rpc spec check action=file_contain values=/etc/passwd,rpinson

