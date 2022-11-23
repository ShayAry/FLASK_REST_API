# FLASK_REST_API

A REST API to exposed to interactions with stores, items, tags, and users. 

The API will allow clients to:
  - Create and retrieve information about stores.
  - Create, retrieve, search for, update, and delete items in those stores.
  - Create tags and link them to items, and search for items with specific tags.
  - Add user authentication to the client apps using the API.
  - Handle secure login, logout, authorization and authentication.


The API will have the endpoints shown below:

#Users
| Method | Endpoint        | description |
|--------|-----------------|-------------|
| POST   | /register       |             |
| POST   | /login          |             |
| 🔒POST  | /logout         |             |
| 🔒POST  | /refresh        |             |
| GET    | /user/{user_id} |             |
| DELETE | /user/{user_id} |             |

#Stores
| Method | Endpoint    | Description                              |
|--------|-------------|------------------------------------------|
| GET    | /store      | Get a list of all stores.                |
| POST   | /store      | Create a store.                          |
| GET    | /store/{id} | Get a single store, given its unique id. |
| POST   | /store/{id} | Delete a store, given its unique id.     |


#Items
| Method  | Endpoint   | Description                                                                                         |
|---------|------------|-----------------------------------------------------------------------------------------------------|
| 🔒GET    | /item      | Get a list of all items in all stores.                                                              |
| 🔒🔒POST  | /item      | Create a new item, given its name and price in the body of the request.                             |
| 🔒GET    | /item/{id} | Get information about a specific item, given its unique id.                                         |
| PUT     | /item/{id} | Update an item given its unique id. The item name or price can be given in the body of the request. |
| 🔒DELETE | /item/{id} | Delete an item given its unique id.                                                                 |

#Tags
| Method | Endpoint            | Description                                             |
|--------|---------------------|---------------------------------------------------------|
| GET    | /store/{id}/tag     | Get a list of tags in a store.                          |
| POST   | /store/{id}/tag     | Create a new tag.                                       |
| POST   | /item/{id}/tag/{id} | Link an item in a store with a tag from the same store. |
| DELETE | /item/{id}/tag/{id} | Unlink a tag from an item.                              |
| GET    | /tag/{id}           | Get information about a tag given its unique id.        |
| DELETE | /tag/{id}           | Delete a tag, which must have no associated items.      |
