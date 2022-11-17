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
1. Cоздать deployment с 2 репликами

```
kubectl apply -f kbv1.yaml
```  
```
kubectl apply -f servicer.yaml
```  
2. Просматриваем созданные сервисы
 ```
kubectl get service
```   
3. подключаемся к контейнерам через браузер
 ```
mkubectl port-forward svc/kbv-service 80:80
```
Название контейнера состоит из деплоймента, хэш реплики сет, случайно сгенерированные сиволы, чтобы различать поды между друг другом.
# Схема 
<div align = "center"><img src="https://github.com/Zepeler/Lb2-/blob/main/img/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202022-11-16%20%D0%B2%2020.34.53.png" ></div>
