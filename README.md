**rpmpkgs-backup** is a shell script to backup /var/log/rpmpkgs daily with the help of cron.

## Usage

### Enable the required repos in Red Hat Enterprise Linux

**RHEL8**

`#subscription-manager repos --enable=rhel-8-for-x86_64-baseos-rpms`

**RHEL7**

`# subscription-manager repos --enable=rhel-7-server-optional-rpms`

**RHEL6**

`# subscription-manager repos --enable=rhel-6-server-optional-rpms`

1. Install rpm-cron, to generate rpmpkgs file.
  - `# yum install rpm-cron`
2. Copy rpmpkgs-backup to /etc/cron.daily/
  - `# cp rpmpkgs-backup /etc/cron.daily/`
3. Make /etc/cron.daily/rpmpkgs-backup executable
  - `# chmod 755 /etc/cron.daily/rpmpkgs-backup`
