University: [ITMO University](https://itmo.ru/ru/)  
Faculty: [FICT](https://fict.itmo.ru)  
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)  
Year: 2022/2023  
Group: K4113c    
Author: Zhelygin Daniil Yurievich 
Lab: Laba2 

# Развертывание веб сервиса в Minikube, доступ к веб интерфейсу сервиса. Мониторинг
## Цель работы
Ознакомиться с типами "контроллеров" развертывания контейнеров, ознакомится с сетевыми сервисами и развернуть свое веб приложение.
## Ход работы 
1. Cоздать deployment с 2 репликами контейнера ifilyaninitmo/itdt-contained-frontend:master и передаем переменные в эти реплики: REACT_APP_USERNAME, REACT_APP_COMPANY_NAME.

```
kubectl apply -f kbv1.yaml
``` 
2. Создаем сервис в котором доступны поды
```
kubectl apply -f servicer.yaml
```
<div align = "center"><img src="https://github.com/Zepeler/Lb2-/blob/main/img/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202022-11-17%20%D0%B2%2018.00.03.png" ></div>
3. Просматриваем созданные сервисы

```
kubectl get service
```   

<div align = "center"><img src="https://github.com/Zepeler/Lb2-/blob/main/img/Lens.jpg" ></div>
4. Подключаемся к контейнерам через браузер

```
kubectl port-forward svc/kbv-service 80:80
```
Скриншот сервиса 
<div align = "center"><img src="https://github.com/Zepeler/Lb2-/blob/main/img/sc.jpg" ></div>
Название контейнера состоит из деплоймента, хэш реплики сет, случайно сгенерированные сиволы, чтобы различать поды между друг другом.
# Схема 
<div align = "center"><img src="https://github.com/Zepeler/Lb2-/blob/main/img/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202022-11-16%20%D0%B2%2020.34.53.png" ></div>
