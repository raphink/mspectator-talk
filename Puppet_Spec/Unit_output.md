# Puppet-spec: Unit tests output

    @@@ Shell
    # puppet agent -t
    info: Retrieving plugin
    err: Could not retrieve catalog from remote server: Unit tests failed:
    F..
    
    Failures:
    
      1) package 
         Failure/Error: it { should contain_package('augeas') }
           expected that the catalogue would contain Package[augeas]
         # /var/lib/puppet/lib/spec/class/augeas/package_spec.rb:3
         # /var/lib/puppet/lib/puppet/indirector/catalog/rest_spec.rb:31:in `find'
    
    Finished in 0.00092 seconds
    3 examples, 1 failure
    
    Failed examples:
    
    rspec /var/lib/puppet/lib/spec/class/augeas/package_spec.rb:3 # package 
    
    info: Not using expired catalog for foo.example.com from cache; expired at Tue Apr 02 17:40:21 +0200 2013
    notice: Using cached catalog


~~~SECTION:notes~~~
This example is on the master side
~~~ENDSECTION~~~
