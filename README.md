# Hold My FLASK

Instantly turn your Python-Flask application into a production-ready docker container.

No more writing and maintaining `Dockerfile` or `docker-compose`

Automatically adds and configures the following in your container so you don't have to:

- **gunicorn** for scalability
- **nginx** for routing
- **supervisord** for monitoring

Place your files inside `/app`. \
Get up and running with a single command:

```bash
docker-compose up
```

Now, if anyone asks you to quickly create and deploy a scalable Flask app, all you have to say is **"Hold My FLASK"**!

## Prerequisites

[Docker](https://docs.docker.com/get-docker/)
[docker-compose](https://docs.docker.com/compose/install/)

## Full Instructions

1. Place your Flask app files into the `app` directory. Use the name `app.py` for your app's entry point or change the filename in `configs/supervisord.conf`. (skip to step #5 to use defaults)
2. Set the version tag on the first line of `Dockerfile` to your desired Python version. (**3.9** by default)
3. (Optional) Make changes to **gunicorn**, **nginx** and **supervisord** config files in `/configs` as needed.
4. (Optional) Use a file "`app/utils/prep.py`" to run python setup scripts such as downloading sklearn models and uncomment the respective line in `Dockerfile` to run the scripts before starting the server.
5. Finally, run the following set of command to build and run the docker container:

```bash
docker-compose up
```
