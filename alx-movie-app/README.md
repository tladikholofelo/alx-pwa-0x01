# API Explorer: Mastering RESTful Connections

## API Overview
The MoviesDatabase API provides access to a large collection of movie and TV show data, allowing users to search for movies, retrieve information about specific titles, and explore various movie-related metadata. Key features include searching movies by title, fetching details about a specific movie or TV show, and retrieving additional information such as reviews, cast, and images.

## Version
Version: [API Version from Documentation]

## Available Endpoints
- **/movie/popular**: Returns a list of the most popular movies based on user votes.
- **/movie/{id}**: Retrieves detailed information about a movie, identified by its ID.
- **/search/movie**: Searches for movies based on a given query.
- **/tv/popular**: Lists popular TV shows.
- **/tv/{id}**: Fetches detailed information about a specific TV show by its ID.
- **/movie/{id}/credits**: Lists the cast and crew for a movie.

## Request and Response Format
### Request Example:
- **GET** `/search/movie?query=Inception`
```json
{
  "query": "Inception"
}
```

### Response Example:
```json
{
  "page": 1,
  "results": [
    {
      "id": 27205,
      "title": "Inception",
      "overview": "A thief who steals corporate secrets through the use of dream-sharing technology is given the inverse task of planting an idea into the mind of a CEO.",
      "release_date": "2010-07-16",
      "vote_average": 8.3
    }
  ]
}
```

## Authentication
To access the API, you need an API key. The API key must be included as a query parameter in your requests, as follows:

* **Key**: `api_key`
* **Example**: `/search/movie?query=Inception&api_key=your_api_key`

## Error Handling
Common error responses:

* **400 Bad Request**: The request is malformed or missing required parameters.
* **401 Unauthorized**: API key is missing or invalid.
* **404 Not Found**: The requested resource does not exist.
* **500 Internal Server Error**: Something went wrong on the server's side.

To handle errors, check the status code of the response and ensure that the request was correctly formed.

## Usage Limits and Best Practices
* **Rate Limit**: The API may have a limit on the number of requests you can make per minute/hour/day. Check the documentation for the exact limits.
* **Caching**: Cache responses where appropriate to reduce the number of API calls.
* **Avoid Overloading**: Make requests only when necessary to avoid hitting the rate limit too quickly.
