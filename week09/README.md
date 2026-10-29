\# 쿠버네티스 정리







\## 명령어 실행 결과







\### $ kubectl get nodes 결과



```text



NAME       STATUS   ROLES           AGE   VERSION



minikube   Ready    control-plane   55m   v1.37.0



```







\### $ kubectl get pods -w 결과



```text



NAME                         READY   STATUS    RESTARTS   AGE



guestbook-6684ddfcb8-5smvm   1/1     Running   0          12m



```







\---







\## 선언형이란?



개발자가 목표를 하나하나 절차까지 정해주는것이 아닌 목표 상태를 정하고 실무는 쿠버네티스가 작업하는 방식. 







\### 선언형 예시:



고객이 특정 인테리어를 원할 때 페인트, 작업 순서등등을 전부 지정하는 것이 아닌 인테리어 업자가 알아서 작업함.







\---







\## 막혔던 점



도커를 실행하지 않고 `minikube start --driver=docker`를 실행해서 에러가 발생함.

