University Workshop Management System

A Spring Boot application for managing university workshops, sessions, and participants.

The University Workshop Management System (WMS) is designed to facilitate the organization and management of academic workshops. It allows tracking of:

Workshops and their details
Workshop sessions
Presenters
Undergraduate participants
Postgraduate participants

Technical Stack
Framework: Spring Boot
Database: MySQL
ORM: Hibernate/JPA
Language: Java

Data Model

Core Entities

1.Person (MappedSuperclass)
Base class for all person entities
Fields: email, gender, name, phone

2.Workshop

Represents a workshop event
Fields: id, name, description, start_date, end_date

3.Session

Represents individual sessions within workshops
Fields: id, name, description, date, time, workshop_id
Relationships: Many-to-Many with presenters, undergraduates, and postgraduates

4.Presenter

Extends Person
Fields: id, affiliation, country, job_title
Relationships: Many-to-Many with sessions

5.Undergraduate

Extends Person
Fields: id, degree, university
Relationships: Many-to-Many with sessions

6.Postgraduate

Extends Person
Fields: id, institute, research_interest, second_degree
Relationships: Many-to-Many with sessions
