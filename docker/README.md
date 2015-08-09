# Dockerfile for Academic-Webpage-Docpad-Boilerpate

This `README` is derived from the
[DocPad Dockerfile](https://github.com/docpad/dockerfile) by Rob Loach.

[Docker](http://docker.com) container to use [DocPad](http://docpad.org).

## Usage

### Install

Build `<yourname>/docpad` from source:

```bash
cd docker
docker build -t <yourname>/docpad .
```

### Run

From the project root directory, run the image, binding associated ports, and
mounting the present working directory to the `/app` directory in the container:

```bash
docker run -it -p 9778:9778 -v $(pwd):/app:rw docpad/docpad help
```

Append the DocPad command to the end of your `docker run` command. The above
example uses `help`.

Probably you are interested in running:
```bash
docker run -it -p 9778:9778 -v $(pwd):/app:rw docpad/docpad run
```


## Services

Service     | Port | Usage
------------|------|------
DocPad      | 9778 | When using `docpad run`,
                     visit `http://localhost:9778` in your browser


## Volumes

Volume          | Description
----------------|-------------
`/app`          | The location of the DocPad application root.
