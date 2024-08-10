# YAML

yet another Markup language: presentation languge.

YAML syntax consitsts of 2:

dictionary and lists:

1. Dictonary: a key value pair is called a dictonary
2. Lists: a list of items plurals. 

dictonary -->  key:value pair
lists --> -banaa
          -apple anything with a '-' is called as lists.  


syntax of playbook:

- name: playname
  hosts: group name
  tasks: 
    - name: taskname
      module name:
        action: input to action

example:

- name: hello msgs
  hosts: all    
  taks: 
    - name: sending a message
      ansible.builtin.ping: 
        data: pong

### Variables

every programming lanugage is incomplete with variables in ansible as well we have the concept of varaibles.

how to declare a variable:

we can declare a variable in 4 ways:

1. play - level vairables
2. task - level variables
3. cli - level varaibles using -e we can provide the value to a variable when executing the playbook
4. file - level variables.

order of importance / preccedence:

Commandline level > task level variable declaration > play level declaration.

commandline level example:

ansible-playbook -i nodes -e ansible_username=ec2-user -e ansible-password=DevOps321 -e variable=value of the variable playbook_name

#### play level varaible:

- name: play name
  hosts: all
  vars: 
    - var1 = value
    - var2 = value
  tasks:  
    - name: task1
      modulename:
        module action

#### task level:

- name: play name
  hosts: all
  vars: 
    - var1 = value
    - var2 = value
  tasks:  
    - name: task1
      modulename:
        module action
      vars:
        - var1 = value
        - var2 = value 

File declaration of variables are used commonly and widely.