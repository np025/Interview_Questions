# Load Balancing: Interview Q&A 

## 1. When would you choose an Application Load Balancer (ALB) over a Network Load Balancer (NLB), and vice versa?

**Interviewer:** When would you choose an Application Load Balancer (ALB) over a Network Load Balancer (NLB), and vice versa?

**Candidate:** 
- I would choose an **ALB** when I need advanced routing features, like host-based or path-based routing, or if I am dealing with HTTP/HTTPS traffic.
- On the other hand, I would go for an **NLB** when I need ultra-low latency and need to handle TCP, UDP, or gRPC traffic directly.
- For example, ALB is ideal for web applications, while NLB suits backend systems or services requiring high performance.

---

## 2. What is a target group in the context of ALB, and how is it used for routing traffic to instances?

**Interviewer:** What is a target group in the context of ALB?

**Candidate:** A target group defines the destination for incoming traffic from the ALB. It can include EC2 instances, IP addresses, or Lambda functions. 
- Based on the listener rules, the ALB routes traffic to the appropriate target group. 
- This helps in organizing traffic distribution and enables scaling and flexibility.

---

## 3. Explain the concept of listeners and rules in load balancer configuration.

**Interviewer:** Can you explain listeners and rules in load balancers?

**Candidate:**
- A **listener** is a process that checks for connection requests using a protocol and port (e.g., HTTP on port 80).
- **Rules** determine how requests are routed based on conditions like URL path or hostname.
- For instance, an ALB with multiple rules can route `/api` traffic to one target group and `/app` traffic to another.

---

## 4. What are the health checks performed by AWS load balancers, and how do they impact instance health?

**Interviewer:** What are health checks in AWS load balancers?

**Candidate:** Health checks are periodic tests performed by the load balancer to verify the availability of targets.
- They send requests to a specified endpoint, like `/health`.
- If targets fail health checks, the load balancer stops routing traffic to them, ensuring that only healthy instances serve requests.

---

## 5. How can you ensure session persistence or stickiness for clients using a load balancer in AWS?

**Interviewer:** How do you ensure session persistence for clients?

**Candidate:** By enabling **sticky sessions**, also known as session affinity. 
- This ensures that requests from the same client are always sent to the same target instance.
- For ALB, this is achieved using a cookie (Application-Controlled or Load-Balancer-Generated).

---

## 6. How does AWS ensure high availability for load balancers, and what are the best practices for achieving redundancy?

**Interviewer:** How is high availability achieved for load balancers?

**Candidate:** AWS ensures high availability by deploying load balancers across multiple **Availability Zones (AZs)**.
- To enhance redundancy, we should:
  - Enable cross-zone load balancing.
  - Distribute targets evenly across AZs.
  - Use health checks to detect and route traffic away from unhealthy instances.

---

## 7. Explain the use of cross-zone load balancing in AWS, and when would you enable or disable it?

**Interviewer:** What is cross-zone load balancing?

**Candidate:** Cross-zone load balancing allows traffic to be distributed evenly across all targets in all enabled AZs, regardless of the source.
- I would enable it for consistent traffic distribution.
- I might disable it if AZ-specific traffic routing or cost optimization is required.

---

## 8. What is the importance of distributing instances across multiple Availability Zones (AZs) when using load balancers in AWS?

**Interviewer:** Why distribute instances across multiple AZs?

**Candidate:** Distributing instances across AZs ensures high availability and fault tolerance.
- If one AZ goes down, the load balancer can route traffic to healthy instances in other AZs.

---

## 9. Explain the process of configuring SSL/TLS certificates for securing traffic between clients and the load balancer.

**Interviewer:** How do you configure SSL/TLS certificates for a load balancer?

**Candidate:** 
- I would obtain a certificate from AWS Certificate Manager (ACM) or upload a custom certificate.
- Then, I attach the certificate to the HTTPS listener of the load balancer.
- This enables encrypted communication between clients and the load balancer.

---

## 10. What is AWS Web Application Firewall (WAF), and how can it be integrated with a load balancer for application security?

**Interviewer:** What is WAF, and how does it integrate with load balancers?

**Candidate:** AWS WAF is a firewall service for web applications to protect against common exploits like SQL injection or XSS.
- It can be associated with an ALB by linking WAF rules to the load balancer.
- This adds a layer of security to web applications.

---

## 11. What are blue-green deployments, and how can AWS load balancers be used to facilitate this deployment strategy?

**Interviewer:** How do load balancers support blue-green deployments?

**Candidate:** In blue-green deployments, traffic is shifted from the old (blue) environment to the new (green) environment gradually or instantly.
- Load balancers can be configured to direct traffic to the green environment once it's verified to be stable, ensuring a seamless deployment.

---

This conversational Q&A format aims to simplify Load Balancer concepts for students and interview preparation.
