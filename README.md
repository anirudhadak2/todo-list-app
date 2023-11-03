# todo-list-app

This  TODO-APP is 2-tier architecture using mysql as backend database for  todo app 


apiVersion: apps/v1
kind: Deployment
metadata:
  name: todo-application
  labels:
    app: todo-app
  spec:
    replicas: 3
    selector:
      matchLabels:
        app: todo-app
    template:
    metadata:
      labels:
        app: todo-app
    spec:
      containers:
      - name: todo-app
        image: anirudhadak2/new-app:todo-app
        ports:
        - containerPort: 3000
      - name: backend-database
        image: mysql:latest

-----------------------------------------------------------------------------------------




