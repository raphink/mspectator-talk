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
        should have package "apache2.2-common"
        should not have package "httpd"
        should have service "apache2"
        should have file "/etc/apache2/apache2.conf"
        should have directory "/etc/apache2/conf.d"
        should have user "www-data"
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
    
      2) apache when on Debian 
         Failure/Error: it { should find_nodes(5).with_agent('spec') }
           expected to find 5 nodes using agent 'spec', but found 2 instead.
         # ./apache_spec.rb:11
    
      3) apache when using SSL 
         Failure/Error: it { should find_nodes(50).or_more }
           expected to find 50 nodes or more using agent 'rpcutil', but found 0 instead.
         # ./apache_spec.rb:23
    
    Finished in 29.1 seconds
    12 examples, 3 failures
    
    Failed examples:
    
    rspec ./apache_spec.rb:5 # apache 
    rspec ./apache_spec.rb:11 # apache when on Debian 
    rspec ./apache_spec.rb:23 # apache when using SSL 

