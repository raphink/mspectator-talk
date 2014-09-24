# Mspectator architecture

* Client runs RSpec
* RSpec calls MCollective
* MCollective calls distant `spec` agent
* `spec` agent calls `specinfra` backend

![Mspectator Architecture](../images-base/Mspectator_Architecture.png)
