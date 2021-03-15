# Kafka Homework

This repository contains a project template and infrastructure for the Kafka homework. 

## Task Description

There is a Kafka cluster with 2 topics: `users` and `notifications`. `users` topic is being
constantly filled with the test data. The data format is JSON, sample message is: 

```json
{"registertime":1502427342644,"userid":"User_5","regionid":"Region_4","gender":"FEMALE"}
```

### What Should Be Done

Complete a .NET service in `./WelcomeService` directory, so the it reads data from `users` 
topic and produces messages in `notifications` topic. 

The content of `notification` topic should be build as `users.userId + " has been registered"`.
So for the previous sample the message should be `User_5 has been registered`.

## How To Get It Up and Running

This repo uses a docker compose to start everything needed. No extra dependeny except of Docker 
is required to complete this task.

### Start the Stack

```bash
docker-compose up -d
```

### View messages in the Kafka

```bash
docker-compose logs users-reader # for users
docker-compose logs notifications-reader # for users
```

You can use `docker-compose logs --follow <svc_name>` to follow (don't exit on the end) logs. 

