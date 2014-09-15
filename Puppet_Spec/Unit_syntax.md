# Puppet-spec: Unit testing

* Catalog exposed by `PuppetSpec::Catalog.instance.catalog`
* Uses `rspec-puppet` matchers
* Asserts real catalogs
* Runs on the master or agent side (as catalog indirection terminii)

        @@@ Ruby
        describe 'puppet' do
          subject { PuppetSpec::Catalog.instance.catalog }
          it { should contain_package('puppet') }
          it { should contain_package('ppet') }
          it { should include_class('puppet') }
          it { should include_class('puppet::client::base') }
        end
