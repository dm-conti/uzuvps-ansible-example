#Per verificare la conessione con il nostro server remoto, possiamo usare il modulo ping di Ansible in questo modo:

ansible all -i hosts -m ping



#Questa e' la risposta:

192.168.1.100 | success >> {
    "changed": false,
    "ping": "pong"
}






#Per eseguire lo script, dalla root directory lanciamo il seguente comando:

ansible-playbook ./hello-world.yml -v -vvvv -u uzumaki -i hosts




#Dovremmo ottenere una risposta simile alla seguente:

PLAY [Hello Ansible - quick start] ******************************************** 

GATHERING FACTS *************************************************************** 
<192.168.1.100> ESTABLISH CONNECTION FOR USER: uzumaki
<192.168.1.100> REMOTE_MODULE setup
<192.168.1.100> EXEC ssh -C -tt -vvv -o ControlMaster=auto -o ControlPersist=60s -o ControlPath="/Users/uzumaki/.ansible/cp/ansible-ssh-%h-%p-%r" -o IdentityFile="/Users/uzumaki/.ssh/id_rsa.pub" -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 192.168.1.100 /bin/sh -c 'mkdir -p $HOME/.ansible/tmp/ansible-tmp-1439010224.78-89585568252965 && echo $HOME/.ansible/tmp/ansible-tmp-1439010224.78-89585568252965'
<192.168.1.100> PUT /var/folders/qp/stxpcmxx76ndm_mjzn8yl38m0000gn/T/tmpSEVvew TO /home/uzumaki/.ansible/tmp/ansible-tmp-1439010224.78-89585568252965/setup
<192.168.1.100> EXEC ssh -C -tt -vvv -o ControlMaster=auto -o ControlPersist=60s -o ControlPath="/Users/uzumaki/.ansible/cp/ansible-ssh-%h-%p-%r" -o IdentityFile="/Users/uzumaki/.ssh/id_rsa.pub" -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 192.168.1.100 /bin/sh -c 'LANG=en_US.UTF-8 LC_CTYPE=en_US.UTF-8 /usr/bin/python /home/uzumaki/.ansible/tmp/ansible-tmp-1439010224.78-89585568252965/setup; rm -rf /home/uzumaki/.ansible/tmp/ansible-tmp-1439010224.78-89585568252965/ >/dev/null 2>&1'
ok: [192.168.1.100]

TASK: [uzumaki | debug msg="this is a task from role A"] ********************** 
<192.168.1.100> ESTABLISH CONNECTION FOR USER: uzumaki
ok: [192.168.1.100] => {
    "msg": "this is a task from role A"
}

PLAY RECAP ******************************************************************** 
192.168.1.100              : ok=2    changed=0    unreachable=0    failed=0   