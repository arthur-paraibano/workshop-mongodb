<h1 align="center" style="font-weight: bold;">Workshop-mongodb 💻</h1>

<p align="center">
 <a href="#tech">Technologies</a> • 
 <a href="#started">Getting Started</a> • 
 <a href="#routes">API Endpoints</a> •
 <a href="#colab">Collaborators</a> •
 <a href="#contribute">Contribute</a> •
 <a href="#network">Redes Sociais</a> •
</p>

<p align="center">
    <b>Simple project that performs the basic operations of an API, with Java in the backend and MongoDB as a non-relational database.</b>
</p>

<h2 id="technologies">💻 Technologies</h2>

<img width="12" />
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-plain-wordmark.svg" height="40" alt="java logo"  />
<img width="12" />
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-plain-wordmark.svg" height="40" alt="java logo"  />

- Java
- MongoDB  

<h2 id="started">🚀 Getting started</h2>

To run this project on your machine you must have downloaded the tools mentioned below, you must run MongoDB through cmd with the ```mongod``` command. Within MongoDBCompass create a database with the name ```workshop_mongo``` the folders will be created as soon as you run the API.

<h3>Prerequisites</h3>

Necessary prerequisites to execute this project:

- [MongoDBCompass](https://drive.google.com/file/d/1HLWHnJHEPM4fpXtXb2acNeaOdoEVxGir/view?usp=drive_link)
- [MongoDB](https://drive.google.com/file/d/1Qzu6rzjh5puVqHa_tzwkP3PkKrCaSwHf/view?usp=drive_link)
- [Postman](https://drive.google.com/file/d/1p7aanlVv7Pvmg4oM8VOXSKfbS4g9U_6b/view?usp=drive_link)

<h3>Cloning</h3>

How to clone your project

```bash
git clone https://github.com/arthur-paraibano/workshop-mongodb.git
```

<h3>Config .env variables</h2>

Inside the `application.properties` file, make sure it is the same path as "MongoDBCompass".

```bash
spring.data.mongodb.uri=mongodb://localhost:27017/workshop_mongo
```

<h3>Starting</h3>

How to start the project:

```bash
run class: WorkshopmongodbApplication
```

<h2 id="routes">📍 API Endpoints</h2>

Here you can list the main routes of your API, and what are their expected request bodies.
​
| route               | description                                          
|----------------------|-----------------------------------------------------
| <kbd>GET User /authenticate</kbd>     | retrieves user info, see [response details](#getUser-auth-detail)
| <kbd>GET Post /authenticate</kbd>     | retrieve post information, see [response details](#getPost-auth-detail)
| <kbd>GET Pers /authenticate</kbd>     | retrieve personalized information, see [response details](#getPer-auth-detail)
| <kbd>POST /authenticate</kbd>     | authenticate user into the api, see [request details](#post-auth-detail)
| <kbd>DELETE /authenticate</kbd>     | delete the user in the API, see [request details](#delete-auth-detail)
| <kbd>PUT /authenticate</kbd>     | put from a specific user in the API, see [request details](#put-auth-detail)

<h3 id="getUser-auth-detail">GET User /authenticate</h3>

- ```http://localhost:8080/users```

**RESPONSE**
```json
{
    "id": "65dcb6aa86c0690a6686a751",
    "name": "Maria Brown",
    "email": "maria@gmail.com"
}
```

<h3 id="getPost-auth-detail">GET Post /authenticate</h3>

- ```http://localhost:8080/posts/fullsearch```

**RESPONSE**
```json
[
    {
        "id": "65dcb6aa86c0690a6686a754",
        "date": "2018-03-21T00:00:00.000+00:00",
        "title": "Partiu viagem",
        "body": "Vou viajar para São Paulo. Abraços!",
        "author": {
            "id": "65dcb6aa86c0690a6686a751",
            "name": "Maria Brown"
        },
        "comments": [
            {
                "text": "Boa viagem mano!",
                "date": "2018-03-21T00:00:00.000+00:00",
                "author": {
                    "id": "65dcb6aa86c0690a6686a752",
                    "name": "Alex Green"
                }
            },
            {
                "text": "Aproveite",
                "date": "2018-03-22T00:00:00.000+00:00",
                "author": {
                    "id": "65dcb6aa86c0690a6686a753",
                    "name": "Bob Grey"
                }
            }
        ]
    },
    {
        "id": "65dcb6aa86c0690a6686a755",
        "date": "2018-03-23T00:00:00.000+00:00",
        "title": "Bom dia",
        "body": "Acordei feliz hoje!",
        "author": {
            "id": "65dcb6aa86c0690a6686a751",
            "name": "Maria Brown"
        },
        "comments": [
            {
                "text": "Tenha um ótimo dia!",
                "date": "2018-03-23T00:00:00.000+00:00",
                "author": {
                    "id": "65dcb6aa86c0690a6686a752",
                    "name": "Alex Green"
                }
            }
        ]
    }
]
```

<h3 id="getPer-auth-detail">GET Pers /authenticate</h3>

- ```http://localhost:8080/posts/fullsearch?text=bom&maxDate=2018-03-30```

**RESPONSE**
```json
{
    "id": "65dcb6aa86c0690a6686a755",
    "date": "2018-03-23T00:00:00.000+00:00",
    "title": "Bom dia",
    "body": "Acordei feliz hoje!",
    "author": {
        "id": "65dcb6aa86c0690a6686a751",
        "name": "Maria Brown"
    },
    "comments": [
        {
            "text": "Tenha um ótimo dia!",
            "date": "2018-03-23T00:00:00.000+00:00",
            "author": {
                "id": "65dcb6aa86c0690a6686a752",
                "name": "Alex Green"
            }
        }
    ]
}
```

<h3 id="post-auth-detail">POST /authenticate</h3>

- ```http://localhost:8080/users```

**REQUEST**
```json
{
    "name": "Jose",
    "email": "Jose@gmail.com"
}
```

**RESPONSE**
```json
- 201 Created
- The request has been fulfilled and resulted in a new resource being created.
```

<h3 id="delete-auth-detail">DELETE /authenticate</h3>

- ```http://localhost:8080/users/ 65dcc0fb9411df62befe61bf ```

**REQUEST**
```json
{
    "id": "65dcc0fb9411df62befe61bf",
    "name": "Jose",
    "email": "Jose@gmail.com"
}
```

**RESPONSE**
```json
- 204 No Content
- The server successfully processed the request, but is not returning any content.
```

<h3 id="put-auth-detail">PUT /authenticate</h3>

- ```http://localhost:8080/users/ 65dcc0c39411df62befe61ba ```

**REQUEST**
```json
{
    "id": "65dcc0c39411df62befe61ba",
    "name": "Maria Brown",
    "email": "maria@gmail.com"
}
```

**RESPONSE**
```json
- 200 OK
- Standard response for successful HTTP requests. The actual response will depend on the request method used. In a GET request, the response will contain an entity corresponding to the requested resource. In a POST request the response will contain an entity describing or containing the result of the action.
```



<h2 id="colab">🤝 Collaborators</h2>

<table>
  <tr>
    <td align="center">
      <a href="#">
        <img src="https://avatars.githubusercontent.com/u/110489981?v=4" width="100px;" alt="Arthur Mikael"/><br>
        <sub>
          <b>Arthur Mikael</b>
        </sub>
      </a>
    </td>
</table>

<h2 id="contribute">📫 Contribute</h2>

Contribute to the project.

1. `git clone https://github.com/Fernanda-Kipper/text-editor.git`
2. `git checkout -b feature/NAME`
3. Follow commit patterns
4. Open a Pull Request explaining the problem solved or feature made, if exists, append screenshot of visual modifications and wait for the review!

<h3>Documentations that might help</h3>

[📝 How to create a Pull Request](https://www.atlassian.com/br/git/tutorials/making-a-pull-request)

[💾 Commit pattern](https://gist.github.com/joshbuchea/6f47e86d2510bce28f8e7f42ae84c716)


<h2 id="network">🌎 Redes Sociais</h2>

[![Instagram](https://img.shields.io/badge/Instagram-%23E4405F?style=for-the-badge&logo=instagram&logoColor=fff)](https://www.instagram.com/arthur_paraibano/) 
[![Discord](https://img.shields.io/badge/Discord-7289DA?style=for-the-badge&logo=discord&logoColor=fff)](https://discord.gg/x32ftcRd8a)
