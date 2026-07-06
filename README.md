# ER Diagram Documentation

## Overview

The Entity Relationship (ER) Diagram represents the database structure of the **Personalized Networking Assistant**. It illustrates how user information, event details, networking sessions, AI-generated conversation starters, Wikipedia fact verification, and system logs are organized and related within the application. The design follows database normalization principles to minimize redundancy, improve data integrity, and support efficient querying.

## Entities

The ER model consists of six primary entities:

* **User Profile** – Stores user biography information and cached event data.
* **Event Context** – Stores event descriptions and extracted themes used for personalization.
* **Networking Session** – Records every interaction between a user and an event.
* **Generated Starter** – Stores AI-generated conversation starters created during a networking session.
* **Wikipedia Fact Check** – Stores fact verification requests and their verification results.
* **Log Entry** – Maintains detailed system logs for auditing, debugging, and analytics.

## Primary Keys

Each entity contains a unique primary key:

* User Profile – **UserID**
* Event Context – **EventID**
* Networking Session – **SessionID**
* Generated Starter – **StarterID**
* Wikipedia Fact Check – **FactCheckID**
* Log Entry – **LogID**

## Foreign Keys

The relationships between entities are maintained using foreign keys:

* **Networking Session** references **User Profile** through **UserID**.
* **Networking Session** references **Event Context** through **EventID**.
* **Generated Starter** references **Networking Session** through **SessionID**.
* **Wikipedia Fact Check** references **Networking Session** through **SessionID**.
* **Log Entry** references **Networking Session** through **SessionID**.

## Relationships

The database follows one-to-many (1:M) relationships:

* One user can participate in multiple networking sessions.
* One event context can be associated with multiple networking sessions.
* One networking session can generate multiple conversation starters.
* One networking session can perform multiple Wikipedia fact checks.
* One networking session can create multiple system log entries.

## Normalization

The ER model is normalized to reduce data redundancy and improve consistency. User information, event data, networking sessions, AI-generated outputs, fact verification records, and system logs are stored in separate entities while maintaining relationships through foreign keys.

## Use Case Coverage

The ER diagram supports the following core functionalities of the Personalized Networking Assistant:

* Managing persistent user profiles.
* Storing event information and extracted themes.
* Recording networking sessions.
* Generating personalized AI conversation starters.
* Verifying factual information using Wikipedia.
* Maintaining system logs for auditing, analytics, and debugging.

## Conclusion

The ER Diagram provides a clear and scalable database design for the Personalized Networking Assistant. It ensures efficient data management, maintains referential integrity through primary and foreign keys, and supports all major application features while remaining flexible for future enhancements.
