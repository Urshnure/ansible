- name: netology-ml
  hosts: hosts

  tasks:
  - name: ping my hosts
    ansible.builtin.ping:

  - name: install
    ansible.builtin.shell:
      cmd: "sudo apt install -y net-tools git tree htop mc vim"
      cmd: "sudo apt update"

  - name: copy file
    ansible.builtin.copy:
      src: /etc/ansible/test.txt
      dest: /home/ansible/test.txt
      mode: u+rw,g-wx,o-rwx



  - name: groups
    become: true
    become_method: su
    become_user: root
    become_exe: sudo su
    ansible.builtin.group:
      name:  "{{ item }}"
    loop:
      - test_1
      - devops_1

  - name: users
    become: true
    become_method: su
    become_user: root
    become_exe: sudo su
    ansible.builtin.user:
      name: "{{ item }}"
      group: "{{ item }}"
      createhome: yes
    loop:
      - test_1
      - devops_1
