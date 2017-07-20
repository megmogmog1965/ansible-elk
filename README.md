# ansible-elk

[Ansible] project for ELK ([Elasticsearch] + [Logstash] + [Kibana]) on AWS.


# How to use

Run an EC2 instance from Amazon Linux AMI.

* [Amazon Linux AMI 2017.03.1 (HVM), SSD Volume Type](https://aws.amazon.com/jp/amazon-linux-ami/)

Edit inventory file to change target host and JVM memory size for Elasticsearch (half of physical memory, recommended).

```
[ec2]
12.34.56.78  ansible_user=ec2-user

[all:vars]
elasticsearch_memory_size=512
```

Then, run ansible playbook.

```
$ ansible-playbook -i hosts --private-key=/path/to/your-private-key site.yml
```


[Ansible]:https://www.ansible.com/
[Elasticsearch]:https://www.elastic.co/products/elasticsearch
[Kibana]:https://www.elastic.co/jp/products/kibana
[Logstash]:https://www.elastic.co/products/logstash
