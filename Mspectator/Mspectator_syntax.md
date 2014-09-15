# Mspectator syntax

Own matchers, mapping to `specinfra` backend methods:

    @@@ Ruby
    require 'mspectator'
    
    describe 'apache' do
      it { should find_nodes(100).or_less }   # Counts discovered nodes
      it { should pass_puppet_spec }          # Runs the `spec` agent
      it { should have_certificate.signed }   # Uses the `puppetca` agent
    
      context 'when on Debian',
        :facts => { :operatingsystem => 'Debian' } do            # Filter by facts
    
        it { should find_nodes(5).with_agent('spec') }
        it { should have_package('apache2.2-common') }
        it { should_not have_package('httpd') }
        it { should have_service('apache2').with(
          :ensure => 'running'
        ) }
        it { should have_file('/etc/apache2/apache2.conf') }
        it { should have_directory('/etc/apache2/conf.d') }
        it { should have_user('www-data') }
      end
    
      context 'when using SSL', :classes => ['apache::ssl'] do   # Filter by classes
        it { should find_nodes(50).or_more }
        it { should have_package('ca-certificates') }
      end
    end

