# Mspectator output

    @@@ Shell
    $ rake spec SPEC=apache_spec.rb
    /home/rpinson/.rvm/rubies/ruby-1.8.7-p371/bin/ruby -S rspec apache_spec.rb
    
    apache
      should find nodes 100
      should pass puppet spec (FAILED - 1)
      should have certificate
      when on Debian
        should find nodes 5 (FAILED - 2)
        ...
      when using SSL
        should find nodes 50 (FAILED - 3)
    
    No request sent, we did not discover any nodes.    should have package "ca-certificates"
    
    Failures:
    
      1) apache 
         Failure/Error: it { should pass_puppet_spec }
           expected that all hosts would pass tests, the following didn't:
           soekris01.wrk.cby.camptocamp.com:
            soekris02.wrk.cby.camptocamp.com:
            
         # ./apache_spec.rb:5

    ...

