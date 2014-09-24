# Serverspec

* http://serverspec.org
* Provides RSpec matchers for local functional tests (packages, users, services, ports, etc.)
* Independant from configuration management tools

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
