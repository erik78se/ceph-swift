# ceph-swift
Some example use of swift

# Read here
https://docs.openstack.org/python-swiftclient/latest/cli/index.html

# Set environment variables to connect to storage backend

export ST_AUTH_VERSION=3
export OS_USERNAME=testuser
export OS_USER_DOMAIN_NAME=admin_domain
export OS_PASSWORD=1234
export OS_PROJECT_NAME=admin
export OS_PROJECT_DOMAIN_NAME=admin_domain
export OS_AUTH_URL=http://192.168.1.173:5000/v3

# Test connectivity
swift list

# upload file to object storage
swift upload testcontainer stripedata/105_VIS_V_RB_2005_31.envi

# add metadata to the uploaded file
swift post testcontainer stripedata/105_VIS_V_RB_2005_31.envi --meta Color:Blue --meta Tenderness:5

# show the object
swift stat --lh testcontainer stripedata/105_VIS_V_RB_2005_31.envi

# show only files that is under some prefix
swift list testcontainer -p stripedata
