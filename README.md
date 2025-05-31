# University Workshop Management System

A Spring Boot application for managing university workshops, sessions, and participants.

## 📌 Overview

The **University Workshop Management System (WMS)** is designed to streamline the organization and management of academic workshops at universities. It enables tracking and management of:

- Workshops and their details  
- Workshop sessions  
- Presenters  
- Undergraduate participants  
- Postgraduate participants  

## 🛠️ Technical Stack

- **Framework:** Spring Boot  
- **Database:** MySQL  
- **ORM:** Hibernate / JPA  
- **Language:** Java  

## 🧩 Data Model

### 🔹 Core Entities

#### 1. `Person` (MappedSuperclass)
> Base class for all person entities.

- Fields:
  - `email`
  - `gender`
  - `name`
  - `phone`

---

#### 2. `Workshop`
> Represents a workshop event.

- Fields:
  - `id`
  - `name`
  - `description`
  - `start_date`
  - `end_date`

---

#### 3. `Session`
> Represents individual sessions within workshops.

- Fields:
  - `id`
  - `name`
  - `description`
  - `date`
  - `time`
  - `workshop_id`

- Relationships:
  - Many-to-Many with `Presenter`
  - Many-to-Many with `Undergraduate`
  - Many-to-Many with `Postgraduate`

---

#### 4. `Presenter` (extends `Person`)
> Represents workshop presenters.

- Fields:
  - `id`
  - `affiliation`
  - `country`
  - `job_title`

- Relationships:
  - Many-to-Many with `Session`

---

#### 5. `Undergraduate` (extends `Person`)
> Represents undergraduate participants.

- Fields:
  - `id`
  - `degree`
  - `university`

- Relationships:
  - Many-to-Many with `Session`

---

#### 6. `Postgraduate` (extends `Person`)
> Represents postgraduate participants.

- Fields:
  - `id`
  - `institute`
  - `research_interest`
  - `second_degree`

- Relationships:
  - Many-to-Many with `Session`

---

## ✅ Features

- Create and manage workshop events
- Schedule and organize sessions under workshops
- Manage presenter, undergraduate, and postgraduate information
- Assign participants and presenters to specific sessions

## 🚀 Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/university-wms.git

