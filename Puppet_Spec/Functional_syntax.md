# Puppet-spec: Functional testing

* Uses `serverspec`/`specinfra` matchers
* Tests the machine state (not the catalog)


        @@@ Ruby
        require 'spec_helper'
        
        describe service('httpd') do
          it { should be_enabled   }
          it { should be_running   }
        end
        
        describe port(80) do
          it { should be_listening }
        end
        
        describe file('/etc/httpd/conf/httpd.conf') do
          it { should be_file }
          its(:content) { should match /ServerName www.example.jp/ }
        end
