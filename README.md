`ansible-playbook -i inventory main.yml`

Shows how to conditionally execute a role based on a dynamically added host fact.

```
PLAY [all] ********************************************************************

GATHERING FACTS ***************************************************************
ok: [localhost]

TASK: [set_fact ] *************************************************************
ok: [localhost]

TASK: [foo.rh | debug msg="I am foo"] *****************************************
skipping: [localhost]

TASK: [foo.debian | debug msg="I am debian"] **********************************
ok: [localhost] => {
        "msg": "I am debian"
}

TASK: [foo.ubuntu | debug msg="I am ubuntu"] **********************************
skipping: [localhost]

PLAY RECAP ********************************************************************
localhost                  : ok=3    changed=0    unreachable=0    failed=0
```
