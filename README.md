# link_parsing_API
This code exports three functions. "parseUrl" parses a URL string and returns an object containing its components. "explainUrlComponents" takes a URL string and returns a formatted string explaining its components. "parseMultipleUrls" takes an array of URLs and returns an array of objects where each object represent a parsed URL string.

Here is the Readme, which explains the code and its exports:

URL Parsing
This module exports three functions related to URL parsing.

parseUrl(urlString)
Parses a URL string and returns an object containing its components. The parsed URL object contains:

scheme: The protocol of the URL (without the trailing ":").
domain: The domain name of the URL.
port: The port number specified in the URL (if any).
path: The path of the URL.
query: An object representation of the query string.
fragment: The fragment identifier (if any).
Example usage:

Js


const { parseUrl } = require("./urlUtils");

const parsed = parseUrl("https://subdomain.example.com:8080/path/to/page?query=string&some_part=1");
console.log(parsed);
// Output:
// {
//   scheme: "https",
//   domain: "subdomain.example.com",
//   port: "8080",
//   path: "/path/to/page",
//   query: { query: "string", some_part: "1" },
//   fragment: ""
// }
explainUrlComponents(urlString)
This function takes a URL string and returns a formatted string explaining its components. The output will contain:

Scheme: The protocol of the URL.
Domain: The domain name of the URL.
Port (if specified).
Path: The path of the URL.
Query parameters (if specified).
Fragment identifier (if specified).
Example usage:

Js


const { explainUrlComponents } = require("./urlUtils");

const explanation = explainUrlComponents("https://subdomain.example.com:8080/path/to/page?query=string&some_part=1");
console.log(explanation);
// Output:
// Scheme: https
// Domain: subdomain.example.com
// Port: 8080
// Path: /path/to/page
// Query parameters:
// - query: string
// - some_part: 1
parseMultipleUrls(urls)
This function takes an array of URLs and returns an array of objects where each object represents a parsed URL string.

Example usage:

Js


const { parseMultipleUrls } = require("./urlUtils");

const parsedUrls = parseMultipleUrls([
  "https://subdomain.example.com:8080/path/to/page?query=string&some_part=1",
  "https://subdomain.example.com:8080/path/to/page?query=string&some_part=2",
]);
console.log(parsedUrls);
// Output:
// [
//   {
//     scheme: "https",
//     domain: "subdomain.example.com",
//     port: "8080",
//     path: "/path/to/page",
//     query: { query: "string", some_part: "1" },
//     fragment: ""
//   },
//   {
//     scheme: "https",
//     domain: "subdomain.example.com",
//     port: "8080",
//     path: "/path/to/page",
//     query: { query: "string", some_part: "2" },
//     fragment: ""
//   }
// ]
