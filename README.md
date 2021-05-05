# Simple C# WebAPI

## Introduction
**This project was created as a student assignment.**

You can find my other C# APIs and assignments in my [student's github - s18277](https://github.com/s18277).

## Description

Models representing database can be found in subdirectory `Cw11/Models/`.
You can also find there database context `Cw11.Models.ClinicDbContext`.

Context uses external classes configuring table structure (instead of annotations in models themselves).
These classes can be found in `Cw11/Configurations/` subdirectory.

In DB context you can also find helper method seeding database with example data
`Cw11.Models.ClinicDbContext.SeedDataToDb`.

Controller handling requests for path `api/doctors` is `Cw11.Controllers.DoctorsController`.
It provides 5 endpoints:
* Get information about all doctors - `HTTP GET` request under `api/doctors`
* Get information about single doctor - `HTTP GET` request under `api/doctors/{id}`
* Add new doctor - `HTTP POST` request under `api/doctors`
* Modify doctor - `HTTP PUT` request under `api/doctors/{id}`
* Delete doctor - `HTTP DELETE` request under `api/doctors/{id}`

Details can be found in documentation generated automatically using
[Swagger/OpenAPI](https://github.com/domaindrivendev/Swashbuckle.AspNetCore).
Documentation in graphical format can be opened under `/swagger/index.html`.
Documentation in JSON format can be found under `/swagger/v1/swagger.json`.

Communication with database is done using service - interface `Cw11.Services.IClinicDbService`
and it's implementation `Cw11.Services.EfcClinicDbService`. This implemnetation is using `Entity
Framework Core` i `LINQ`.

In this repository you can find two migrations:
* `InitialModelsAndConfigurations` - table structure
* `SeedData` - adding example data to database