- name: create ec2 and r53 recoids
  hosts: local
  connection: local
  vars:
    subnet_id : subnet-0d6c1b251bbb2609c
    sg_id: sg-0c9e4890faf6134a7
    ami_id: ami-09c813fb71547fc4f
  instance:
  - mysql
  - backend
  - frontend
  tasks:
  - name: Create ec2 instance
    amazon.aws.ec2_instance:
      name: "{{ item }}"
      vpc_subnet_id: "{{ subnet_id }}"
      instance_type: t2.micro
      security_group: "{{ sg_id }}"
      image_id: "{{ ami_id }}"
    loop: "{{ instance }}"
    register: ec2_instances