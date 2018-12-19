# Juma API

## Description

This software provides a RESTful API for the Juma Editor (LOSD Version) which allows data to be quickly turned into RDF through a mapping created in Juma.

## Required Software

- Apache Webserver
- php 7
- [Juma Editor (LOSD Version)](https://github.com/Al-Meehan/juma-losd)

## Configuration of the juma-api

1. Extract "juma-api" to webserver root directory.

2. For the juma-api to communicate with the Juma Editor, you need to specify the path to the Juma Editor base directory.
   Open the "../juma-api/index.php" file and specify the path of the Juma Editor base directory for the "$path_to_juma_base" variable.
	 For example, if Juma Editor is located at "/home/user1/" then then the following should be specified: "$path_to_juma_base = '/home/user1/Juma/juma-uplift-master/';".
	 
## Usage of the juma-api
	 
- To use the juma, POST your request to the address of the api with three parameters - which are specified via tokens. These three parameters are:
	- Juma Editor user name (?user)
	- Juma Editor mapping id number (?map)
	- URL of the CSV source data that is to be converted into RDF (?source)

- The result from the api will be RDF data (RDF version of the CSV data in the source file, specified according the the mapping from in the Juma Editor.

- An example call to the api, where the Juma Editor user name is "user1", the mapping ID number is "10" and the URL of the source CSV data is "http://example.com/data/csvfile1", would be as follows:
	- 'POST /juma-api?user=user1&map=10&source=http://example.com/data/csvfile1'
	
## License

This software is released under the [MIT license](http://opensource.org/licenses/MIT).