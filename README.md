# Домашнее задание 11. Ansible 
Подготовить стенд на Vagrant как минимум с одним сервером. На этом сервере используя Ansible необходимо развернуть nginx со следующими условиями:

- необходимо использовать модуль yum/apt;
конфигурационные файлы должны быть взяты из шаблона jinja2 с перемененными;
- после установки nginx должен быть в режиме enabled в systemd;
- должен быть использован notify для старта nginx после установки;
- сайт должен слушать на нестандартном порту - 8080, для этого использовать переменные в Ansible.
## Проверка
- Склонировать репозиторий
  ```
  git clone https://github.com/linuxprolab/hw11.git
  cd hw11
  ```
- Запустить Vagrant хосты:
  ```
  vagrant up
  ```
- Запустить Ansible playbook
  ```
  ansible-playbook -i inventories/development/all.yml playbooks/go.yml --private-key ~/.vagrant.d/insecure_private_key 
  ```
- Проверить доступность web-серверов
  ```
  curl localhost:8001
  curl localhost:8002
  ```