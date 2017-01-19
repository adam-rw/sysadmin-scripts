#Puppet#

Puppet is an orchestration tool for setting up one or more servers in a version controlled, auditable and consistent way.

It allows deployment of full stacks including custom configs and bare shell commands.

Puppet is agent based and polls the Puppet Master at set intervals config changes.

More info at https://puppet.com/.
Docs at https://docs.puppet.com/puppet/

##Puppet Manifest Example##

```
# example.pp

case $operatingsystem {
  centos, redhat: { $service_name = 'ntpd' }
  debian, ubuntu: { $service_name = 'ntp' }
}

package { 'ntp':
  ensure => installed,
}

service { 'ntp':
  name      => $service_name,
  ensure    => running,
  enable    => true,
  subscribe => File['ntp.conf'],
}

file { 'ntp.conf':
  path    => '/etc/ntp.conf',
  ensure  => file,
  require => Package['ntp'],
  source  => "puppet:///modules/ntp/ntp.conf",
  # This source file would be located on the Puppet master at
  # /etc/puppetlabs/code/modules/ntp/files/ntp.conf
}

```
