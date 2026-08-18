# TMDB-API-Testing-Assignment

This repository contains my API Testing Assignment for **The Movie Database (TMDB) API**, implemented using **Postman** and executed using **Newman**.

## Tools & Technologies

- Postman
- Newman
- JavaScript
- REST API
- JSON

## Project Structure

```text
TMDB-API-Testing/
│
├── TheMovieDatabaseAPI.postman_collection.json
├── TestingEnv.postman_environment.json
├── newman/
│   └── TheMovieDatabaseAPI-2026-08-17-18-36-33-136-0.html
└── README.md
````

## Collection Overview

The collection covers the following API testing scenarios:

1. Search Movies by Keyword
2. Search TV Shows by Name
3. Get Movie Details by Movie ID
4. Get Movie Credits
5. Get Popular Movies
6. Get TV Show Details by ID
7. Get Movie Genres List
8. Discover Movies by Genre
9. Get Now Playing Movies
10. Get Person Details (Actor/Director)
11. Get Account Details
12. Add Movie to Watchlist (Bonus)

The collection includes assertions for:

* HTTP status codes
* Response structure validation
* Required fields validation
* Array and object validation
* Data type validation
* Date range validation
* Sorting validation
* Genre filtering validation
* Pagination validation
* Response content validation
* Idempotency-related behavior

## Prerequisites

Before running the collection, make sure you have:

* A valid **TMDB API Key**
* A valid **TMDB Bearer Token**
* Postman
* Newman

For more information about TMDB authentication, visit:

[https://developer.themoviedb.org/docs/authentication-application](https://developer.themoviedb.org/docs/authentication-application)

## Environment Configuration

The collection uses the following environment variables:

| Variable       | Description                                   |
| -------------- | --------------------------------------------- |
| `base_url`     | TMDB API base URL                             |
| `api_key`      | Your TMDB API Key                             |
| `bearer_token` | Your TMDB Bearer Token                        |
| `account_id`   | TMDB account ID used for watchlist operations |
| `person_id`    | Person ID used in Scenario 10                 |

### Important

For security reasons, the actual API Key and Bearer Token are **not included in this repository**.

Before running the collection, add your own credentials to the `TestingEnv` environment:

```text
api_key = YOUR_TMDB_API_KEY
bearer_token = YOUR_TMDB_BEARER_TOKEN
```

Do not commit or share your API Key or Bearer Token publicly.

## Running the Collection in Postman

1. Import `TheMovieDatabaseAPI.postman_collection.json`.
2. Import `TestingEnv.postman_environment.json`.
3. Select the `TestingEnv` environment.
4. Add your own TMDB API Key and Bearer Token.
5. Make sure the required variables have valid values.
6. Run the collection from Postman.

## Running the Collection with Newman

Check that Newman is installed:

```bash
newman --version
```

Run the collection using:

```bash
newman run TheMovieDatabaseAPI.postman_collection.json -e TestingEnv.postman_environment.json
```

Alternatively, you can provide the API Key and Bearer Token at runtime:

```bash
newman run TheMovieDatabaseAPI.postman_collection.json \
-e TestingEnv.postman_environment.json \
--env-var "api_key=YOUR_TMDB_API_KEY" \
--env-var "bearer_token=YOUR_TMDB_BEARER_TOKEN"
```

## Newman HTML Report

The collection was executed using Newman from the command line.

The generated HTML report is available in:

`newman/TheMovieDatabaseAPI-2026-08-17-18-36-33-136-0.html`

## API Testing Techniques Used

The collection demonstrates several API testing and JavaScript assertion techniques, including:

* `pm.test()`
* `pm.expect()`
* `forEach()`
* `map()`
* Property validation
* Array validation
* Numeric comparisons
* Sorting validation
* Date conversion using the JavaScript `Date` constructor
* Date range validation
* Request and response data validation

## Testing Notes

During testing, some differences were observed between the assignment's expected behavior and the actual behavior returned by the TMDB API.

For example, in the **Add Movie to Watchlist** scenario, sending the same request again returned HTTP `201 Created` with an update-related response instead of the `200 OK` specified in the assignment.

This behavior was documented as a testing finding rather than modifying the assertion simply to make the test pass.

## Repository Contents

* **Postman Collection:** `TheMovieDatabaseAPI.postman_collection.json`
* **Postman Environment:** `TestingEnv.postman_environment.json`
* **Newman Report:** `newman/TheMovieDatabaseAPI-2026-08-17-18-36-33-136-0.html`

## Author

SEIF AHMED

API Testing Assignment
Postman | Newman | JavaScript

**مهم:** لو أنت رافع الـNewman report فعلًا داخل فولدر `newman`، فالـREADME ده مناسب. ولو اسم ملف الـreport مختلف، بدّل الاسم في الأماكن المذكورة عشان الـREADME يطابق الـrepository بالظبط.
```
