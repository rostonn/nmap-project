# NMAP Results Application

## About

Project to load nmap scan results into sqlite database. Json api to return nmap results based on ip address. UI allows search by ip address to show nmap results.

## Pre-requisites

Program is built to run on a Mac.
Sqlite3 must be installed: [https://www.sqlite.org/download.html](https://www.sqlite.org/download.html)

### Pre-requisites to run and test backend application

Backend application is included in the project root, in the folder nmap-be. Also publicly available: [https://github.com/rostonn/nmap-be](https://github.com/rostonn/nmap-be)

Golang must be installed to build the application and run the tests

### Pre-requisites to run and test client application

Frontend React application is included in the project root in the folder nmap-fe. Also publicly available: [https://github.com/rostonn/nmap-fe](https://github.com/rostonn/nmap-fe)

Node and Npm are required to build the client application 

## Program Execution Instructions
 
1. Open Terminal
2. Change directory into unzipped project folder
3. cd into dist
4. run ./nmap-be
5. Program will run at http://localhost:8080

## Usage
### Upload XML File of NMAP Results

There is a simple webpage to upload an xml file of nmap results. An example xml file is included in the nmap.results folder called nmap.results.xml

The file uploader application is available at:

[http://localhost:8080/upload-xml.html](http://localhost:8080/upload-xml.html)

This application posts the xml file to the server 

### View NMAP Results

A react application is served at

[http://localhost:8080](http://localhost:8080)

Enter an IP address to search for NMAP results. An example IP address is shown on the site. Table can be cleared with the clear button.

## Database

Database schema is included in the dist folder in the file nmap.schema
Sqlite3 Database file is in dist folder nmap.db

There is a shell script in the root of the project folder called **reset-db.sh**
This bash script will drop all database tables and create them again

Each nmap result is saved in the database with a Scan id. This way the same nmap result set will only be uploaded once

## Testing

To run the go test cases, make sure golang is installed. Run ```go test``` from the nmap-be folder, dal folder, dto folder

To run the front end tests: ```nom test`` from the root project directory

## Build Projects

To Build the react app ```npm build``` it will build to the build folder

To build backend use ```go build``` or go install

## Configuration

Backend:

Config json file is in **dist/config/config.json**

Port and dbPath are configurable by editing this file.

Frontend:

.env file contains the api url ```REACT_APP_API_URL=http://localhost:8080/nmap-by-ip```

## Other Notes

This was a very fun challenging project. Dealing with the entire application stack. 

I chose uploading an XML file because I hadn't used golang to parse XML before.

## Improvements

Add validation on loading the xml file. Add frontend validation on the IP address input box.

Add a bit more testing.

Add configurable option to serve app over HTTPS




