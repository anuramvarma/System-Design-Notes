## **1. Client-Server Architecture**
Almost every web application that you use is built on this simple yet powerful concept called **client-server architecture**.
[
![](https://substackcdn.com/image/fetch/$s_!GgVl!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F05ba06b8-7730-4d3e-a6d9-1f8c81770b55_1364x446.png)
]
- On one side, you have a **client**—this could be a web browser, a mobile app, or any other frontend application.
- On the other side, you have a **server**—a machine that runs continuously, waiting to handle incoming requests.
- The client sends a request to **store, retrieve, or modify data**.
- The server receives the request, processes it, performs the necessary operations, and sends back a response.
---
## **2. IP Address**

A client doesn’t magically know where a server is, it needs an **address** to locate and communicate with it.
On the internet, computers identify each other using **IP addresses**, which work like phone numbers for servers.
[
![](https://substackcdn.com/image/fetch/$s_!7vrc!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fbefd954a-3bf4-4000-9749-8bbe491b7881_1304x848.png)
]

Every publicly deployed server has a **unique IP address**. When a client wants to interact with a service, it must send requests to the correct IP address.
But there’s a problem:

- When we visit a website, we don’t type its IP address—we just enter the website name.
- We can’t expect users (or even systems) to memorize a string of random numbers for every service they connect to.
- And if we migrate our service to another server, its IP address may change—breaking all direct connections
---
## 3.DNS

Instead of relying on hard-to-remember IP addresses, we use something much more human-friendly: **domain names**.
But, we need a way to map a domain name to it’s corresponding IP address.
This is where **DNS (or Domain Name System)** comes in. It maps easy to remember domain names  to their corresponding IP addresses.
[
![](https://substackcdn.com/image/fetch/$s_!s6fZ!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F7a22b7b4-f51c-47c7-a9db-abb5ce56def7_1284x916.png)
]
Here’s what happens behind the scenes:
1. When you type `algomaster.io` into your browser, your computer asks a DNS server for the corresponding IP address.
2. Once the DNS server responds with the IP, your browser uses it to establish a connection with the server and make a request.
- You can find the IP address of any domain using the **ping** command. Just open your terminal and type ping followed by the domain name. 
- And it’ll return the IP address currently assigned to that domain.

---
## 4. **Proxy / Reverse Proxy**

When you visit a website, your request doesn’t always go directly to the server—sometimes, it passes through a **proxy** or **reverse proxy** first.
A **proxy server** acts as a **middleman** between your device and the internet.
[
![](https://substackcdn.com/image/fetch/$s_!i5Av!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff11ff886-4db5-4550-aa0f-5f232b094b03_887x477.png)
]

When you request a webpage, the proxy forwards your request to the target server, retrieves the response, and sends it back to you.
Proxy hides your IP address, keeping your location and identity private.
A **reverse proxy** works the other way around. It intercepts client requests and forwards them to backend servers based on predefined rules.
[
![](https://substackcdn.com/image/fetch/$s_!L8Gg!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F3be42662-47d2-4165-b278-95d583e2d2be_904x517.png)
]
- Allowing direct access to servers can pose **security risks**, exposing them to threats like **hackers** and **DDoS attacks**.
- A reverse proxy mitigates these risks by acting as a controlled entry point that regulates incoming traffic and hides server IPs.
- It can also act as a load balancer, distributing traffic across multiple servers.
- If you want to learn about Proxy vs Reverse Proxy in more detail, checkout this article:
  https://blog.algomaster.io/p/proxy-vs-reverse-proxy-explained

---
## 5. Latency

Whenever a client communicates with a server, there’s always some delay. One of the biggest causes of this delay is **physical distance**.
[
![](https://substackcdn.com/image/fetch/$s_!CL6W!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F664e76b6-37fa-4e36-b8a5-d41a5b0ad93a_1866x988.png)
]
- For example, if our server is in **New York**, but a user in **India** sends a request, the data has to travel halfway across the world—and then the response has to make the same long trip back.
- This round-trip delay is called **latency**—the total time it takes for data to travel between the client and the server. High latency can make applications feel slow and unresponsive.
- One way to **reduce latency** is by deploying our service across **multiple data centers worldwide**.
- This way, users can connect to the **nearest** server instead of waiting for data to travel across the globe.
---
## 6. **HTTP/HTTPS**

Every time you visit a website, your browser and the server communicate using a set of rules called **HTTP (Hypertext Transfer Protocol)**.

That’s why most URLs start with `http://` or its secure version, `https://`.

[
![](https://substackcdn.com/image/fetch/$s_!8BgK!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F46796792-f8b5-4e13-b4c2-6920b3d6e0e7_1942x1170.png)
]

Here’s how it works:
- The **client** sends a request to the server. This request includes a **header** (containing details like the request type, browser type, and cookies) and sometimes a **request body** (which carries additional data, like form inputs).
- The **server** processes the request and responds with an **HTTP response**—either returning the requested data or an error message if something goes wrong.
HTTP has a major security flaw, it **sends data in plain text**. This is a serious problem, especially for sensitive information like passwords, credit card details, and personal data.

That’s why modern websites use **HTTPS (Hypertext Transfer Protocol Secure)** instead. HTTPS encrypts all data using **SSL/TLS,** ensuring that even if someone intercepts the request, they can’t read or alter it.

But clients and servers don’t directly exchange raw HTTP requests and response.

HTTP is just a **protocol** for transferring data but it doesn’t define:
- How requests should be structured
- What format responses should be in
- or how different clients should interact with the server.
This is where **APIs (or Application Programming Interfaces)** come in.

---

## 7. **APIs**

Think of an API as a **middleman** that allows clients (like web and mobile apps) to communicate with servers without worrying about low-level details.

[

![](https://substackcdn.com/image/fetch/$s_!EH_B!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F0c3a0e69-9134-4bd9-9d42-a898bc838e32_1574x504.png)
]
Almost every digital service you use—social media, e-commerce, online banking, ride-hailing apps—is built on APIs working together behind the scenes.
Here’s how it typically works:
1. A **client** sends a request to an API.
2. The **API**, hosted on a server, processes the request, interacts with databases or other services, and prepares a response.
3. The **API sends back the response** in a structured format, usually **JSON** or **XML**, which the client understands and can display.
APIs provide a **layer of abstraction**—the client doesn’t need to know **how** the server processes the request, only that it **returns the expected data**.
---
## 8. **Rest API**
Among the different API styles, **REST (Representational State Transfer)** is the most widely used.
A **REST API** follows a set of rules that define how clients and servers communicate over HTTP in a structured way.
[
![](https://substackcdn.com/image/fetch/$s_!HBtO!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F5c704568-18c9-48e5-ba45-f8e6e1e25a6b_1554x896.png)
]
Rest is:
- **Stateless:** Every request is independent; the server doesn’t store client state.
- **Resource-Based:** Everything is treated as a resource (e.g., /users, /orders, /products).
- **Uses Standard HTTP Methods:** Clients interact with resources using **HTTP methods** like:
    - **GET** → Retrieves data (e.g., fetching a user profile).
    - **POST** → Creates new data (e.g., adding a new user).
    - **PUT/PATCH** → Updates existing data (e.g., changing user settings).
    - **DELETE** → Removes data (e.g., deleting an account).
REST APIs are great because they’re **simple, scalable, and easy to cache**, but they have **limitations**, especially when dealing with complex data retrieval.

REST endpoints often return **more data than needed**, leading to inefficient network usage. If an API doesn’t return related data, the client may need to **make multiple requests** to retrieve all required information.

To address these challenges, GraphQL was introduced in 2015 by Facebook.

---
## 9. GraphQL

Unlike REST, which forces clients to retrieve **fixed sets of data**, **GraphQL** lets clients **ask for exactly what they need—nothing more, nothing less**.
With a REST API, if you need a user details, user profile details along with their recent posts, you might have to **make multiple requests** to different endpoints:
1. `GET /api/users/123` → fetch user details
2. `GET /api/users/123/profile` → fetch user profile
3. `GET /api/users/123/posts` → fetch user’s posts
With GraphQL, you can **combine those requests into one** and fetch exactly the data you need in a single query:
[
![](https://substackcdn.com/image/fetch/$s_!s0a7!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F5b40446b-9156-4e7f-9107-654235bb1e53_2138x1806.png)
]
The **server responds with only the requested fields**, reducing unnecessary data transfer and improving efficiency.

However, GraphQL also comes with trade-offs—it **requires more processing on the server side** and isn’t as easy to cache as REST.

---

## 10. Databases
- If our application deals with **small amounts of data**, we could store it **in memory**.
- But modern applications handle **massive volumes of data**—far more than what memory can efficiently handle.
- That’s why we need a **dedicated server for storing and managing data**—a **database**.
- A database is the backbone of any application. It ensures that data is stored, retrieved, and managed efficiently while keeping it secure, consistent, and durable.
- When a client requests to **store** or **retrieve** data, the **server communicates with the database**, fetches the required information, and returns it to the client.
[
![](https://substackcdn.com/image/fetch/$s_!Xis-!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F57b338e3-3cc2-4bcf-86e4-0aa42cc2c2de_1060x884.png)
]
But not all databases are the same. 
Different applications have different **scalability, performance, and consistency** requirements, which is choosing the right type of database is important.