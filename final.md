# Задание 1:
1) Создать сервис, состоящий из 2 различных контейнеров: 1 - веб, 2 - БД
2) Далее необходимо создать 3 сервиса в каждом окружении (dev, prod, lab)
3) По итогу на каждой ноде должно быть по 2 работающих контейнера
4) Выводы зафиксировать

1-2. Создаем *docker-compose* файл, состоящий из двух контейнеров:
   1 - веб, nginx
   2 - БД, mariadb

Docker-compose file для окружения dev (dev.yaml):
sudo nano dev.yaml
```
version: '3.3'
services:
 web:
  image: nginx:latest
  ports:
   - "8081:80"
  networks:
   - network_net
```
  
![image](https://github.com/user-attachments/assets/dbe13a32-623e-41b0-929e-507724f3ea50)

Docker-compose file для окружения prod (prod.yaml):
sudo nano prod.yaml
![image](https://github.com/user-attachments/assets/aad1fef1-3f1d-4d3c-944c-c34fa3cbc396)

Docker-compose file для окружения lab (lab.yaml):
sudo nano lab.yaml
![image](https://github.com/user-attachments/assets/25a50009-0b67-45c0-9a1f-36590c104225)

3. После того, как создали сервисы для каждого окружения, выполняем следующие команды для развертывания контейнеров:

Развертывание для dev окружения:
sudo docker-compose -f dev.yaml up -d
docker ps
![image](https://github.com/user-attachments/assets/83515794-9912-4ae8-a130-54ef47ec010d)

Развертывание для prod окружения:
sudo docker-compose -f prod.yaml up -d
docker ps
![image](https://github.com/user-attachments/assets/da741690-76a0-4264-b59a-e4db7f19404c)

Развертывание для lab окружения:
sudo docker-compose -f lab.yaml up -d
docker ps
![image](https://github.com/user-attachments/assets/0a15f18b-dae6-4c76-8e56-2504c43efbeb)


4. Вывод логов
Вывод логов выполнения для окурежния dev:
sudo docker-compose -f dev.yaml logs
![image](https://github.com/user-attachments/assets/d37bb4b9-4b8b-4470-9831-b93ec411e0f1)

Вывод логов выполнения для окурежния prod:
sudo docker-compose -f prod.yaml logs
![image](https://github.com/user-attachments/assets/51c42244-d8ec-4dfc-ba08-073e7e745da2)

Вывод логов выполнения для окурежния lab:
sudo docker-compose -f lab.yaml logs
![image](https://github.com/user-attachments/assets/c3637656-ddea-4e94-b442-91841cf7ded7)


# Задание 2:
1) нужно создать 2 ДК-файла, в которых будут описываться сервисы
2) повторить задание 1 для двух окружений: lab, dev
3) обязательно проверить и зафиксировать результаты, чтобы можно было выслать преподавателю для проверки

1-2. Создаем *docker-compose* файл, состоящий из двух контейнеров:
   1 - веб, nginx
   2 - БД, mariadb

Docker-compose file для окружения lab (lab.yaml):
sudo nano lab.yaml
![image](https://github.com/user-attachments/assets/25a50009-0b67-45c0-9a1f-36590c104225)

Docker-compose file для окружения dev:
sudo nano dev.yaml
![image](https://github.com/user-attachments/assets/dbe13a32-623e-41b0-929e-507724f3ea50)

3. После того, как создали сервисы для каждого окружения, выполняем следующие команды для развертывания контейнеров:
Развертывание для lab окружения:
sudo docker-compose -f lab.yaml up -d
docker ps
![image](https://github.com/user-attachments/assets/0a15f18b-dae6-4c76-8e56-2504c43efbeb)

Вывод логов выполнения для окурежния lab:
sudo docker-compose -f lab.yaml logs
![image](https://github.com/user-attachments/assets/c3637656-ddea-4e94-b442-91841cf7ded7)

sudo docker-compose -f dev.yaml up -d
docker ps
![image](https://github.com/user-attachments/assets/83515794-9912-4ae8-a130-54ef47ec010d)

Вывод логов выполнения для окурежния dev:
sudo docker-compose -f dev.yaml logs
![image](https://github.com/user-attachments/assets/d37bb4b9-4b8b-4470-9831-b93ec411e0f1)
