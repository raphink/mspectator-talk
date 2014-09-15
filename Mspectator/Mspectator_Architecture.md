# Mspectator architecture

* Client runs RSpec
* RSpec calls MCollective
* MCollective calls distant `spec` agent
* `spec` agent calls `specinfra` backend

        +-------------------------------------+           +-------------------------------------+
        |      Client                         |           |        Server                       |
        |-------------------------------------|           |-------------------------------------|
        |                                     |           |                                     |
        |     rspec                           |           |                                     |
        |       +                             |           |                                     |
        |       | (check_action, *args)       |           |                                     |
        |       v                             |           |                                     |
        |  MCollective::RPC#rpcclient         |           |         Specinfra::Backend::Exec    |
        |       |                             |           |           ^                         |
        |       +                             |           |           | (check_action, *args)   |
        |       |                             |           |           +                         |
        |       +------------------------------------------->  MCollective::RPC::Agent          |
        |                action, *args        |           |                                     |
        |                                     |           |                                     |
        +-------------------------------------+           +-------------------------------------+
