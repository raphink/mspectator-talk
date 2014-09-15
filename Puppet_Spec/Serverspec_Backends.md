# Serverspec backends

Allows to use various means of launching tests:

* SSH (default)
* Exec
* Puppet (RAL, removed from core)

        @@@ Shell
        $ serverspec-init
        Select OS type:
        
          1) UN*X
          2) Windows
        
        Select number: 1
        
        Select a backend type:
        
          1) SSH
          2) Exec (local)
        
        Select number: 1


