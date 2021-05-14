1 Задание. Ansible
Написать Ansible-playbook который установит Apache2 и загрузит html страницу на целевом сервере. Playbook должен учитывать, что целевой сервер может быть Ubuntu server или CentOS.
Результат разместить на github.

Использую заранее подготовденную пару виртуальных машин с настроенным ssh соединением по ключу

Все настройки подключения к управляемым машинам находятся в файле hosts.txt

В нём я ввёл переменную os, которая определяет фразу в html странице, генерируемую c помощью jinja2


Выполняю команду

ansible-playbook -i hosts.txt -l test playbook.yaml --extra-vars "ansible_sudo_pass=МойПароль"

![Alt-текст](https://github.com/Suppamanisation/AnsibleTask/blob/master/screenshots/Screenshot%20from%202021-05-14%2004-43-24.png)

После чего проверяю index.html страницы web-серверов

![Alt-текст](https://github.com/Suppamanisation/AnsibleTask/blob/master/screenshots/Screenshot%20from%202021-05-14%2004-15-13.png)


![Alt-текст](https://github.com/Suppamanisation/AnsibleTask/blob/master/screenshots/Screenshot%20from%202021-05-14%2004-15-22.png)

Хотел сделать новую вм c CentOS но столкнулся с проблемой недоступности стандартных репозиториев
