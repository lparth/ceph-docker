# CEPH DAEMON IMAGE
# CEPH VERSION: Jewel
# CEPH VERSION DETAIL: 10.2.x

FROM ceph/base:tag-build-master-jewel-ubuntu-14.04
MAINTAINER Sébastien Han "seb@redhat.com"

# Add bootstrap script, ceph defaults key/values for KV store
ADD *.sh ceph.defaults check_zombie_mons.py ./osd_scenarios/* /

# Add templates for confd
ADD ./confd/templates/* /etc/confd/templates/
ADD ./confd/conf.d/* /etc/confd/conf.d/

# Add volumes for Ceph config and data
VOLUME ["/etc/ceph","/var/lib/ceph", "/etc/ganesha"]

# Execute the entrypoint
WORKDIR /
ENTRYPOINT ["/entrypoint.sh"]
