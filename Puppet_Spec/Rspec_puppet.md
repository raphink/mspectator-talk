# Rspec-puppet

* http://rspec-puppet.com
* Now the standard to unit test Puppet manifests
* Generates catalogs in clean environments
* Asserts catalogs for resources/classes

        @@@ Ruby
        require 'spec_helper'
        
        describe 'logrotate::rule' do
          let(:title) { 'nginx' }
        
          it { should compile.with_all_deps }    
          it { should contain_class('logrotate::setup') }
        end
