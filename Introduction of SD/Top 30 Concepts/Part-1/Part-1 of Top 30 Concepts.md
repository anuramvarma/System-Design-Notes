## **1. Client-Server Architecture**

Almost every web application that you use is built on this simple yet powerful concept called **client-server architecture**.
[
![](https://substackcdn.com/image/fetch/$s_!GgVl!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F05ba06b8-7730-4d3e-a6d9-1f8c81770b55_1364x446.png)
](https://substackcdn.com/image/fetch/$s_!GgVl!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F05ba06b8-7730-4d3e-a6d9-1f8c81770b55_1364x446.png)

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
](https://substackcdn.com/image/fetch/$s_!7vrc!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fbefd954a-3bf4-4000-9749-8bbe491b7881_1304x848.png)

Every publicly deployed server has a **unique IP address**. When a client wants to interact with a service, it must send requests to the correct IP address.
But there’s a problem:

- When we visit a website, we don’t type its IP address—we just enter the website name.
- We can’t expect users (or even systems) to memorize a string of random numbers for every service they connect to.
- And if we migrate our service to another server, its IP address may change—breaking all direct connections
---
## 3. DNS

Instead of relying on hard-to-remember IP addresses, we use something much more human-friendly: **domain names**.
But, we need a way to map a domain name to it’s corresponding IP address.
This is where **DNS (or Domain Name System)** comes in. It maps easy to remember domain names  to their corresponding IP addresses.
[
![](https://substackcdn.com/image/fetch/$s_!s6fZ!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F7a22b7b4-f51c-47c7-a9db-abb5ce56def7_1284x916.png)
](https://substackcdn.com/image/fetch/$s_!s6fZ!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F7a22b7b4-f51c-47c7-a9db-abb5ce56def7_1284x916.png)

Here’s what happens behind the scenes:
1. When you type `algomaster.io` into your browser, your computer asks a DNS server for the corresponding IP address.
2. Once the DNS server responds with the IP, your browser uses it to establish a connection with the server and make a request.
You can find the IP address of any domain using the **ping** command. Just open your terminal and type ping followed by the domain name. 
And it’ll return the IP address currently assigned to that domain.

---
## 4. **Proxy / Reverse Proxy**

https://blog.algomaster.io/p/proxy-vs-reverse-proxy-explained

When you visit a website, your request doesn’t always go directly to the server—sometimes, it passes through a **proxy** or **reverse proxy** first.

A **proxy server** acts as a **middleman** between your device and the internet.
[
![](https://substackcdn.com/image/fetch/$s_!i5Av!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff11ff886-4db5-4550-aa0f-5f232b094b03_887x477.png)
](https://substackcdn.com/image/fetch/$s_!i5Av!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff11ff886-4db5-4550-aa0f-5f232b094b03_887x477.png)

When you request a webpage, the proxy forwards your request to the target server, retrieves the response, and sends it back to you.
Proxy hides your IP address, keeping your location and identity private.
A **reverse proxy** works the other way around. It intercepts client requests and forwards them to backend servers based on predefined rules.
[
![](https://substackcdn.com/image/fetch/$s_!L8Gg!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F3be42662-47d2-4165-b278-95d583e2d2be_904x517.png)



](https://substackcdn.com/image/fetch/$s_!L8Gg!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F3be42662-47d2-4165-b278-95d583e2d2be_904x517.png)

Allowing direct access to servers can pose **security risks**, exposing them to threats like **hackers** and **DDoS attacks**.

A reverse proxy mitigates these risks by acting as a controlled entry point that regulates incoming traffic and hides server IPs.

It can also act as a load balancer, distributing traffic across multiple servers.

If you want to learn about Proxy vs Reverse Proxy in more detail, checkout this article:

---

## 5. Latency

Whenever a client communicates with a server, there’s always some delay. One of the biggest causes of this delay is **physical distance**.
[
![](https://substackcdn.com/image/fetch/$s_!CL6W!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F664e76b6-37fa-4e36-b8a5-d41a5b0ad93a_1866x988.png)
](https://substackcdn.com/image/fetch/$s_!CL6W!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F664e76b6-37fa-4e36-b8a5-d41a5b0ad93a_1866x988.png)

For example, if our server is in **New York**, but a user in **India** sends a request, the data has to travel halfway across the world—and then the response has to make the same long trip back.

This round-trip delay is called **latency**—the total time it takes for data to travel between the client and the server. High latency can make applications feel slow and unresponsive.

One way to **reduce latency** is by deploying our service across **multiple data centers worldwide**.

This way, users can connect to the **nearest** server instead of waiting for data to travel across the globe.