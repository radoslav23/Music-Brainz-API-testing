This project contains a lightweight automated test suite for the MusicBrainz public API, built using Postman, Newman, and GitHub Actions.
It demonstrates how to structure API tests, organize a Postman collection, and run the suite automatically in CI.

The goal is to provide a clean, professional example of API automation using a real public API with no authentication requirements.

Features

- Organized Postman collection with folders (Lookups, Search, Browse, Public)

- Automated tests for status codes, JSON structure, and key fields

- Negative tests for invalid MBIDs

- GitHub Actions workflow that runs the collection on every push

- Optional scheduled nightly run

- Local execution using Postman CLI or Newman

- Fully open‑source and easy to extend


How to Run Tests Locally

Option 1 — Using Postman CLI
Install Postman CLI

Log in:

Code
postman login
Run the collection:

Code
postman collection run "MusicBrainz Basic API Tests.postman_collection.json"
Option 2 — Using Newman
Install Newman globally:

Code
npm install -g newman
Run the collection:

Code
newman run "MusicBrainz Basic API Tests.postman_collection.json"

Continuous Integration (GitHub Actions)

This repository includes a workflow that automatically runs the Postman collection:

on every push

on every pull request

optionally on a daily schedule

The workflow file is located at:

Code

.github/workflows/postman-tests.yml

It uses Newman to execute the collection and prints results directly in the GitHub Actions logs.

What the Tests Cover

Lookups:

Artist lookup

Lookup for invalid artist

Event lookup

Series lookup

Release lookup

Recording lookup

Search

Artist search

Recording search

Release search

Browse
Browse releases by artist

Browse recordings by release

Negative Tests
Invalid MBID returns 404

Missing parameters return error

Each request includes Postman test scripts verifying:

status code

JSON format

required fields

array structure

presence of MBIDs

Why MusicBrainz?

MusicBrainz is a stable, public, free API with:

predictable responses

no authentication required

real‑world data

fast response times

Perfect for demonstrating API automation skills.
