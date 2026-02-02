# Advanced Learning Paths (Post-90 Days)

> **Career Progression Guide**
> 
> After completing the [90-Day Backend Engineering Roadmap](README.md), use this guide to specialize based on your career goals. These are **6-12 month learning paths** for experienced developers.

---

## 🎯 Who Is This For?

**Prerequisites:**
- ✅ Completed the [90-Day Core Roadmap](README.md)
- ✅ Built 2-3 portfolio projects
- ✅ 3-6 months of professional backend experience (or equivalent self-study)
- ✅ Comfortable with FastAPI, PostgreSQL, Docker, and deployment

**Not Ready Yet?**
Focus on **shipping projects** and gaining experience with the core stack first. Premature specialization slows learning.

---

## 🗺️ Career Specialization Paths

```
                    ┌──────────────────────────┐
                    │   90-Day Core Roadmap    │
                    │  (FastAPI + PostgreSQL)  │
                    └────────────┬─────────────┘
                                 │
                ┌────────────────┼────────────────┐
                │                │                │
                ▼                ▼                ▼
    ┌─────────────────┐  ┌──────────────┐  ┌──────────────┐
    │  Senior Backend │  │  Platform/   │  │  Technical   │
    │   Engineer      │  │  DevOps Eng  │  │  Lead        │
    └─────────────────┘  └──────────────┘  └──────────────┘
         │                     │                    │
         │                     │                    │
    [Scalability]        [Infrastructure]      [Architecture]
    [Microservices]      [Kubernetes]          [Team Leadership]
    [System Design]      [Cloud Platforms]     [Code Reviews]
```

---

## 🚀 Path 1: Senior Backend Engineer

**Focus:** Building scalable, performant systems that handle millions of users.

**Timeline:** 6-9 months  
**Outcome:** Senior-level engineering roles, system design interviews

### Phase 1: Advanced Database & Performance (2 months)

#### NoSQL Databases (2 weeks)

**Why Learn This:**
PostgreSQL is great for relational data, but modern apps need document stores, caches, and flexible schemas.

**Learning Resources:**
1. [MongoDB University (Free)](https://university.mongodb.com/)
2. [MongoDB with FastAPI Tutorial](https://www.mongodb.com/languages/python/pymongo-tutorial)
3. [Redis University (Free)](https://university.redis.com/)

**Projects:**
1. **User Activity Tracker:**
   - Store user events in MongoDB (flexible schema)
   - Use Redis for real-time leaderboards
   - Compare with PostgreSQL solution

2. **Session Store:**
   - Implement JWT alternative with Redis sessions
   - Handle distributed sessions across servers
   - Add expiration and refresh logic

**Technologies:**
- Motor (async MongoDB driver for Python)
- Redis advanced features (sorted sets, streams, pub/sub)
- Elasticsearch for full-text search

**When to Use NoSQL:**
- ✅ Flexible/evolving schemas (user-generated content)
- ✅ High write throughput (logs, analytics)
- ✅ Document storage (CMS, catalogs)
- ❌ Complex transactions (use PostgreSQL)
- ❌ Strong relational integrity requirements

---

### Phase 2: Microservices & Distributed Systems (3 months)

#### Microservices Architecture (4 weeks)

**Why Learn This:**
Large companies split monoliths into microservices for independent scaling and deployment.

**Learning Resources:**
1. [Building Microservices (Book)](https://www.oreilly.com/library/view/building-microservices-2nd/9781492034018/)
2. [Microservices.io Patterns](https://microservices.io/patterns/index.html)
3. [FastAPI Microservices Tutorial](https://testdriven.io/blog/fastapi-microservices/)

**Core Concepts:**
- Service boundaries and domain-driven design
- API Gateway pattern
- Service discovery (Consul, etcd)
- Inter-service communication (REST, gRPC)
- Distributed transactions (Saga pattern)
- Circuit breakers and retries

**Project:**
**E-commerce Microservices:**
Split monolithic e-commerce into services:
1. **User Service:** Authentication, profiles
2. **Product Service:** Catalog, inventory
3. **Order Service:** Cart, checkout, orders
4. **Notification Service:** Emails, push notifications
5. **API Gateway:** Route requests, handle auth

---

## 🏗️ Path 2: Platform/DevOps Engineer

**Focus:** Infrastructure, deployment, observability, and reliability.

**Timeline:** 6-12 months  
**Outcome:** Platform Engineer, SRE, DevOps roles

### Phase 1: Container Orchestration (2 months)

#### Kubernetes Fundamentals (4 weeks)

**Why Learn This:**
Kubernetes is industry standard for running containerized applications at scale.

**Learning Resources:**
1. [Kubernetes Official Tutorial](https://kubernetes.io/docs/tutorials/)
2. [Kubernetes for Developers (Course)](https://www.udemy.com/course/kubernetes-for-developers/)
3. [Kubernetes The Hard Way](https://github.com/kelseyhightower/kubernetes-the-hard-way)

**Core Concepts:**
- Pods, Services, Deployments
- ConfigMaps and Secrets
- Ingress controllers
- StatefulSets for databases
- Helm charts
- Resource limits and autoscaling

---

## 👨‍💼 Path 3: Technical Lead

**Focus:** Architecture decisions, team collaboration, code quality.

**Timeline:** 6-12 months (alongside work experience)  
**Outcome:** Tech Lead, Engineering Manager tracks

### Phase 1: Code Review & Mentorship (2 months)

**Learning Resources:**
1. [Google Engineering Practices](https://google.github.io/eng-practices/)
2. [The Manager's Path (Book)](https://www.oreilly.com/library/view/the-managers-path/9781491973882/)

**Skills to Develop:**
- Giving constructive code review feedback
- Reviewing for architecture, not just syntax
- Mentoring junior developers
- Writing technical documentation
- Leading design discussions

**Practice:**
- Review 10+ PRs per week on open source projects
- Write architecture decision records (ADRs)
- Create coding standards document
- Mentor 1-2 junior developers

---

## 🎯 Choosing Your Path

**Still Unsure? Try This:**

### Month 1-3 After Roadmap:
Sample all three paths:
- Week 1-2: NoSQL databases (Backend path)
- Week 3-4: Docker Compose & Kubernetes basics (DevOps path)
- Week 5-6: Architecture patterns (Lead path)

Then commit to the path that excites you most.

### By Company Size:

**Startups (< 50 people):**
→ **Backend Engineer Path** (you'll wear all hats anyway)

**Mid-Size (50-500 people):**
→ **Any path works** (companies have specialized roles)

**Large Tech (500+ people):**
→ **Specialize** (Backend, Platform, or Lead tracks are distinct)

---

## 📚 Recommended Reading List

### Technical Books:
1. Designing Data-Intensive Applications (Martin Kleppmann)
2. Domain-Driven Design (Eric Evans)
3. Release It! (Michael Nygard)
4. The Pragmatic Programmer (Hunt & Thomas)

### Soft Skills:
1. The Manager's Path (Camille Fournier)
2. Staff Engineer (Will Larson)
3. An Elegant Puzzle (Will Larson)

---

## ⏱️ Timeline Reality Check

**Realistic Expectations:**

```
90-Day Core Roadmap
    ↓
3-6 months professional experience
    ↓
Choose specialization path
    ↓
6-12 months deep dive
    ↓
Senior-level skills (2+ years total from start)
```

**Key Insight:**
You don't need to complete these paths before getting hired. Most learning happens **on the job**. Use this guide to:
- Fill knowledge gaps
- Prepare for promotions
- Guide self-study
- Understand career options

---

## 🏆 Success Metrics by Path

### Senior Backend Engineer:
- [ ] Design and implement microservices architecture
- [ ] Handle 100k+ requests/day with proper caching
- [ ] Pass system design interviews at FAANG companies
- [ ] Contribute to open source databases/frameworks
- [ ] Optimize queries for 10x performance improvements

### Platform/DevOps Engineer:
- [ ] Deploy production apps to Kubernetes
- [ ] Manage cloud infrastructure with Terraform
- [ ] Set up monitoring dashboards (Prometheus/Grafana)
- [ ] Handle on-call rotations and incidents
- [ ] Achieve AWS/GCP certifications

### Technical Lead:
- [ ] Lead team of 3-5 engineers
- [ ] Make architecture decisions for products
- [ ] Mentor junior developers effectively
- [ ] Write technical specs and ADRs
- [ ] Represent engineering in stakeholder meetings

---

## 💼 Job Market Reality (2025-2026)

**What Companies Actually Need:**

**Entry-Level (0-2 years):**
- ✅ FastAPI/Django + PostgreSQL (from main roadmap)
- ✅ Docker basics
- ✅ Git workflows
- ❌ Usually DON'T require Kubernetes/AWS expertise

**Mid-Level (2-5 years):**
- ✅ Everything from main roadmap
- ✅ Some specialization (NoSQL OR K8s OR Architecture)
- ✅ Production debugging experience
- ❌ Don't need to know EVERYTHING in this guide

**Senior (5+ years):**
- ✅ Deep expertise in ONE path
- ✅ Broad awareness of other paths
- ✅ Leadership/mentoring experience
- ✅ System design skills

**Key Takeaway:**
Don't let this advanced guide intimidate you. Most jobs need the core skills from the [90-Day Roadmap](README.md). These advanced paths are for **career growth**, not entry requirements.

---

## ✅ Final Advice

**From Developers Who've Been There:**

1. **"Ship side projects, not tutorial clones"**
   Build something you'll use. It's more impressive.

2. **"Production experience beats courses"**
   Get a job ASAP. Nothing replaces real work.

3. **"Specialize after generalizing"**
   Master fundamentals before diving deep.

4. **"Tech changes, fundamentals don't"**
   Focus on concepts, not specific tools.

5. **"Consistency beats intensity"**
   2 hours daily for a year >> 40 hours one week.

---

## 🎯 Your Next Steps

1. ✅ **Complete the [90-Day Core Roadmap](README.md)** (if not already done)
2. 📝 **Add critical [Enhancements](ENHANCEMENTS.md)** (testing, API design)
3. 💼 **Build 2-3 portfolio projects** and deploy them
4. 🎤 **Start applying for jobs** (you don't need everything here)
5. 🚀 **Choose ONE advanced path** based on interests/job requirements
6. 📚 **Learn continuously** on the job

**Remember:**
> "The best time to start was yesterday. The second best time is now. You don't need to know everything to start your backend career. Ship code, learn fast, grow continuously."

---

**Questions? Feedback?**  
Open an issue or discussion in this repository.

**[← Back to Main Roadmap](README.md)** | **[← Enhancements Guide](ENHANCEMENTS.md)**

---

**Last Updated:** February 2026  
**Maintained by:** [@ehtisham-sadiq](https://github.com/ehtisham-sadiq)