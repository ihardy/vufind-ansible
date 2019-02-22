# vufind-ansible
Anisble role for deploying a basic vufind instance and loading some sample data.

## example playbook
```
- hosts: all
  roles:
    - vufind
```

## defaults
```
vufind_version: 5.1
vufind_db: vufind
vufind_db_user: vufind
vufind_db_pass: vufindadmin
vufind_db_host: localhost
vufind_local_sample_data: true
```

## Notes
This role contains information from the [Bibliographic Dataset](https://library.harvard.edu/services-tools/harvard-library-apis-datasets#biblio), which is provided by the [Harvard Library](http://library.harvard.edu/) under its [Bibliographic Dataset Use Terms](https://library.harvard.edu/services-tools/harvard-library-apis-datasets#biblio-terms) and includes data made available by, among others, [OCLC Online Computer Library Center](http://www.oclc.org/), Inc. and the [Library of Congress](http://www.loc.gov/cds/).
