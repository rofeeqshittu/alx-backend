# 0x03. Queuing System in JS

## Overview

This project involves building a queuing system using JavaScript, Redis, Node.js, ExpressJS, and Kue. You'll implement and explore Redis functionalities, including basic and advanced operations, asynchronous handling, and queue management. The final objective is to develop a Redis-based queuing system that interacts with background workers for tasks like notifications.

---

## Concepts

- Running and interacting with a Redis server.
- Using Redis client operations in Node.js.
- Managing asynchronous tasks with Redis.
- Building Express applications with Redis interaction.
- Utilizing Kue as a queue system for task management.

---
---

## Tasks

| Task # | Filename                                | Description                                                                                                                                                 |
|--------|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0      | [dump.rdb](./dump.rdb)                  | Install and configure Redis. Verify Redis operations (e.g., setting and getting key-value pairs).                                                           |
| 1      | [0-redis_client.js](./0-redis_client.js) | Create a Redis client in Node.js that connects to the Redis server and logs connection success or errors.                                                   |
| 2      | [1-redis_op.js](./1-redis_op.js)        | Implement Redis operations (set and get) using callbacks.                                                                                                   |
| 3      | [2-redis_op_async.js](./2-redis_op_async.js) | Use `promisify` to handle Redis operations asynchronously with ES6 `async/await`.                                                                            |
| 4      | [4-redis_advanced_op.js](./4-redis_advanced_op.js) | Store and retrieve hash values in Redis.                                                                                                                    |
| 5      | [5-subscriber.js](./5-subscriber.js), [5-publisher.js](./5-publisher.js) | Create a Redis-based queuing system with publisher-subscriber functionality.                                                                               |
| 6      | [6-job_creator.js](./6-job_creator.js)  | Use Kue to create a queue for notification jobs and log their status (created, completed, failed).                                                          |
| 7      | [6-job_processor.js](./6-job_processor.js)        | Use Kue to process jobs in the `push_notification_code` queue, log notifications, and implement a `sendNotification` function.                          |
| 8      | [7-job_creator.js](./7-job_creator.js)            | Create and manage jobs in the `push_notification_code_2` queue, handle job progress tracking, and log job statuses (created, completed, failed).        |
| 9      | [7-job_processor.js](./7-job_processor.js)        | Process `push_notification_code_2` queue jobs, filter blacklisted phone numbers, and log job progress using Kue.                                        |
| 10     | [8-job.js](./8-job.js)                            | Define a `createPushNotificationsJobs` function to create and manage jobs in the `push_notification_code_3` queue, and handle job lifecycle events.     |
| 11     | [8-job.test.js](./8-job.test.js)                  | Write test cases for `createPushNotificationsJobs` using Kue's test mode to validate functionality, error handling, and job creation accuracy.          |
| 12     | [9-stock.js](./9-stock.js)                        | Create a stock management system using Express and Redis to manage product data, track reserved stock, and provide JSON responses for client requests.  |

---

## Environment Setup

1. **Install Redis**:
   ```bash
   wget http://download.redis.io/releases/redis-6.0.10.tar.gz
   tar xzf redis-6.0.10.tar.gz
   cd redis-6.0.10
   make
   src/redis-server &

