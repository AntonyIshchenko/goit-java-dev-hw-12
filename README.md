# SpaceTravel Project

You work at SpaceTravel company. The company specializes in transporting passengers between planets.

## Entities and Relationships

The system consists of the following entities with their respective relationships:

### Client
A company client with the following properties:
- `id` - identifier, primary surrogate key, auto-increment number
- `name` - name, from 3 to 200 characters inclusive

### Planet
Origin or destination point. Has the following properties:
- `id` - planet identifier. String consisting exclusively of Latin uppercase letters and digits. For example: MARS, VEN
- `name` - planet name, string from 1 to 500 characters inclusive

### Ticket
Has the following properties:
- `id` - ticket identifier, primary surrogate key, auto-increment number
- `created_at` - TIMESTAMP in UTC when this ticket was created
- `client_id` - identifier of the client who owns this ticket
- `from_planet_id` - identifier of the planet from which the passenger departs
- `to_planet_id` - identifier of the planet to which the passenger travels

## Task #1 - Set up project with Hibernate

Create a new Gradle project. Connect the following libraries to it:
- H2
- Hibernate
- Flyway

Make sure your project starts and doesn't produce any errors.

## Task #2 - Write migrations to create and populate the database

Write two migrations.

### First Migration
The first migration (name it `V1__create_db.sql`) should create the database structure - all tables and relationships between them. Pay attention to correct constraints. For example, for the ticket table, the `client_id` field should be a foreign key to the client table by the `id` field.

### Second Migration
The second migration should populate the database with data (name this migration `V2__populate_db.sql`). Create at least:
- 10 clients
- 5 planets
- 10 tickets

Make sure the program starts and both migrations execute correctly.

## Task #3 - Create CRUD services for Client and Planet

### Entity Mapping
Describe the Client and Planet entities. Write Hibernate mappings for these entities (corresponding to the `client` and `planet` tables in the database).

### CRUD Services
Write CRUD services for both entities:
- `ClientCrudService`
- `PlanetCrudService`

### Testing
Write test code that will add/remove records using these services. Make sure all CRUD operations work correctly.