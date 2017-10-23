# k5-cflocal installation

Cloud Foundry CLI:
https://github.com/cloudfoundry/cli/releases

Plugin:
cf install-plugin -r CF-Community "cflocal"

Fujitsu K5 CF account:
cf api https://api.<region>.paas-cf.cloud.global.fujitsu.com
cf login -u <user>@<contract> -o <contract> -s <project> -p <password>
