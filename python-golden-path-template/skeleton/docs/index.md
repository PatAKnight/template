# ${{values.component_id}}

${{values.description}}


## Getting started

### Run with Docker

To run the application with Docker, you need to build and run with the following commands:

```shell
docker build . -t ${{values.component_id}}
docker run -d -p 8081:8081 -t ${{values.component_id}}
```

The default port is `8081` but you can use another value.

You can access the HelloWorld API at [localhost:8080/](http://localhost:8080/).