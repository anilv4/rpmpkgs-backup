**rpmpkgs-backup** is a shell script to backup /var/log/rpmpkgs daily with the help of cron.

The purpose of the rpmpkgs backup is to rebuild the rpmdb using the the following article from Red Hat, when all other rpmdb recovery method fails. An up to date package list is a must for the recovery to be successful.

How to recover rpm database using /var/log/rpmpkgs

https://access.redhat.com/solutions/23743

## Usage

### Enable the required repos in Red Hat Enterprise Linux

**RHEL8**

`# subscription-manager repos --enable=rhel-8-for-x86_64-baseos-rpms`

**RHEL7**

`# subscription-manager repos --enable=rhel-7-server-optional-rpms`

**RHEL6**

`# subscription-manager repos --enable=rhel-6-server-optional-rpms`

1. Install rpm-cron, to generate rpmpkgs file.
  - `# yum install rpm-cron`
2. Download rpmpkgs-backup and copy it to /etc/cron.daily/
  - `# cp rpmpkgs-backup /etc/cron.daily/`
3. Make /etc/cron.daily/rpmpkgs-backup executable
  - `# chmod 755 /etc/cron.daily/rpmpkgs-backup`
