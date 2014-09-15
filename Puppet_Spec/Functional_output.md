# Puppet-spec: Function tests output

    @@@ Shell
    # puppet agent  -t
    info: Retrieving plugin
    info: Caching catalog for foo.example.com
    info: Applying configuration version 'raphink/a2c8e0f [+]'
    ... Applying changes ...
    notice: Finished catalog run in 59.19 seconds
    err: Could not send report: Unit tests failed:
    FF
    
    Failures:
    
      1) augeas 
         Failure/Error: it { should be_installed }
           expected "augeas" to be installed
         # /var/lib/puppet/lib/spec/server/class/foo.example.com/package_spec.rb:2
         # /var/lib/puppet/lib/puppet/indirector/report/rest_spec.rb:45:in `save'
    
      2) /usr/share/augeas/lenses/dist 
         Failure/Error: it { should be_file }
           expected "/usr/share/augeas/lenses/dist" to be file
         # /var/lib/puppet/lib/spec/server/class/foo.example.com/package_spec.rb:6
         # /var/lib/puppet/lib/puppet/indirector/report/rest_spec.rb:45:in `save'
    
    Finished in 0.06033 seconds
    2 examples, 2 failures
    
    Failed examples:
    
    rspec /var/lib/puppet/lib/spec/server/class/foo.example.com/package_spec.rb:2 # augeas 
    rspec /var/lib/puppet/lib/spec/server/class/foo.example.com/package_spec.rb:6 # /usr/share/augeas/lenses/dist 
