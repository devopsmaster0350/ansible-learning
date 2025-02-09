### host_vars and group_vars

* tiil now we are storing all the varaible into inventory file but from now we need to follow the best practices.
* so we need to create the host_vars folder whatever the variable we are storing in `inventroy file` we can store it in `host_vars/web_db_server1.yaml` file. likewise we can create file names on host names and keep it there .

* so whatever the vars common for all the hosts we can create group_vars folder , and we can create filename on group name defined in inventory file
ex: `group_vars/web_db.yaml`

* best part is ansible automatically finds out all these files
