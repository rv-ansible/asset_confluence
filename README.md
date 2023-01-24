# TPS Asset Inventory Role
TPS Asset Inventory Role
requirements.yml
- name: tps-asset-inventory
  src: https://github.domaingc.net/scm/tpsdev/tps-asset-inventory.git
  scm: git

Call from remote yml with tag:
- name: call tps-asset-inventory role
  hosts: all
  roles:
    - { role: tps-asset-inventory, publish_asset_to_confluence: true }

# Requirements when running the scripts operator manually

## Runtime <>
1. Python 2.7
1.1 Module(note by default all modu les below is available on python 2.7)
    json
    csv
    configparser
    requests

## Data<>
Required data to be prepared when using the role

	- file2upload.csv, this contains the list of data/asset in comma delimited format
		e.g. https://github.domaingc.net/projects/DEV/repos/tps_upload_confluence/browse/files/file2upload.csv
	- Required variable by the role
		e.g. https://github.domaingc.net/projects/DEV/repos/tps_upload_confluence/browse/group_vars/all

		user: confluence username
		passsecret: confluence password vault encrypted
		confluence_pageID: pageId of the existing page you want to update
		csv_header: contains list that wil become table header