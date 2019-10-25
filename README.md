# NMAP Results Application

Pre-requisites

Program is built to run on a Mac. There is also a Windows exe program although it hasn't been tested
Sqlite3 must be installed: [(https://www.sqlite.org/download.html]https://www.sqlite.org/download.html)

### Pre-requisites to run and test backend application

Backend application is included in the project root in the folder nmap-be. Also publicly available:

Golang must be installed to build the application and run the tests

Frontend React application is included in the project root in the folder nmap-fe. Also publicly available:

Node and Npm are required to build the client application 



Start Program

1. Open Terminal
2. Change directory into unzipped project folder
3. cd into dist
4. ./nmap-be
5. Program will run at http://localhost:8080

## Usage

### Upload XML File of NMAP Results


There is a simple webpage to upload an xml file of nmap results. An example xml file is included in the root project folder.

The file uploader application is available at:

[(http://localhost:8080/upload-xml.html](http://localhost:8080/upload-xml.html)

This application posts the xml file to the server 

### View NMAP Results

A react application is served at

[(http://localhost:8080](http://localhost:8080)

Enter an IP address to search for NMAP results. An example IP address is shown on the site. Table can be cleared with the clear button.

## Database

Database schema is included in the dist folder in the file nmap.schema
Sqlite3 Database file is in dist folder nmap.db

There is a shell script in the root of the project folder called reset-schema.sh
This bash script will drop all database tables and create them again

Each nmap result is saved in the database with a Scan id. This way the same nmap result set will only be uploaded once

## Testing

To run the go test cases, make sure golang is installed. Run ```go test``` from the nmap-be folder, dal folder, dto folder

To run the front end test: ```nom test`` from the root project directory

## Build Projects

To Build the react app ```npm build``` it will build to the build folder

To build backend use ```go build``` or go install


## Other Notes

This was a fun challenging project. Dealing with the entire full stack. I chose uploading an XML file because I hadn't used golang to parse XML before.

### Improvements

I didn't add any validation on loading the xml file. Or any frontend validation on the IP address input box.

Add a bit more testing. I realize the entire application isn't tested, but all of the testing is set up




