# Tier 2. Module 6 - Fullstack Web Development with Python

## Topic 3. Homework - Web Basics. Building a Simple HTTP Server

### Description

This project is a simple Python web application using an HTTP server and Jinja2 templates. The application allows you to save messages as JSON.

It uses Docker for containerization.

### Routes

- **/** — home page.
- **/message** — add new message.
- **/read** — show all messages.
- **/error** — error page.

### Dependencies

- Python 3.10
- Jinja2
- Docker
- Poetry

### Installation instructions

```bash
   git clone https://github.com/Coffee-2-Go/goit-pythonweb-hw-03.git

   cd goit-pythonweb-hw-03

   docker-compose up --build
```

Open your browser and navigate to http://localhost:3000 to access the app.

### Technical task

Your goal is to implement the simplest web application. Take the **following files from this repository** as a basis https://github.com/GoIT-Python-Web/FullStack-Web-Development-hw3.

By analogy with the example considered in the abstract, create a web application with routing for two `html` pages: `index.html` and `message.html`.

Also:

- Process static resources during the program: `style.css`, `logo.png`;
- Organize work with the form on the `message.html` page;
- In case of a `404 Not Found error`, return the `error.html` page.

The program runs on port `3000`.

When working with the form, we convert the received byte string into a dictionary and save it in the json file `data.json` in the `storage` directory.

The format of the data.json file is as follows:

```Python
{
"2022-10-29 20:20:58.020261": {
"username": "krabaton",
"message": "First message"
},
"2022-10-29 20:21:11.812177": {
"username": "Krabat",
"message": "Second message"
}
}
```

Where the key of each message is the time of receipt of the message: `datetime.now()`. That is, each new message from the web application is added to the `storage/data.json` file with the time of receipt.

Add the `/read` route, when accessed, an information page will be generated. This page should be a Jinja2 template. It should display all saved notifications from the `data.json` file.

Additionaly:

1. Create a `Dockerfile` and run your application as a Docker container.
2. Using the `volumes` mechanism, store data from `storage/data.json` outside the container.
