# Knesset data pipelines

Data processing pipelines for loading, processing and visualizing data about the Knesset

Uses the [datapackage pipelines](https://github.com/frictionlessdata/datapackage-pipelines) and [DataFlows](https://github.com/datahq/dataflows) frameworks.

## Quickstart for data science

Follow this method to get started quickly with exploration, processing and testing of the knesset data.

### Running using Docker

Install Docker for [Windows](https://store.docker.com/editions/community/docker-ce-desktop-windows),
[Mac](https://store.docker.com/editions/community/docker-ce-desktop-mac) or [Linux](https://docs.docker.com/install/)

Pull the latest Docker image

```
docker pull orihoch/knesset-data-pipelines
```

Create a directory which will be shared between the host PC and the container:

```
sudo mkdir -p /opt/knesset-data-pipelines
```

Start the Jupyter lab server:

```
docker run -it -p 8888:8888 --entrypoint jupyter \
           -v /opt/knesset-data-pipelines:/pipelines \
           orihoch/knesset-data-pipelines lab --allow-root --ip 0.0.0.0 --no-browser \
                --NotebookApp.token= --NotebookApp.custom_display_url=http://localhost:8888/
```

Access the server at http://localhost:8888/

Open a terminal inside the Jupyter Lab web-ui, and clone the knesset-data-pipelines project:

```
git clone https://github.com/hasadna/knesset-data-pipelines.git .
```

You should now see the project files on the left sidebar.

Access the `jupyter-notebooks` directory and open one of the available notebooks.

You can now add or make modifications to the notebooks, then open a pull request with your changes.

You can also modify the pipelines code from the host machine and it will be reflected in the notebook environment.

## Contributing

Looking to contribute? check out the [Help Wanted Issues](https://github.com/hasadna/knesset-data-pipelines/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22) or the [Noob Friendly Issues](https://github.com/hasadna/knesset-data-pipelines/issues?q=is%3Aissue+is%3Aopen+label%3A%22noob+friendly%22) for some ideas.

Useful resources for getting acquainted:
* [DPP](https://github.com/frictionlessdata/datapackage-pipelines) documentation
* [Code](https://github.com/OriHoch/knesset-data-k8s) for the periodic execution component
* [Info](http://main.knesset.gov.il/Activity/Info/Pages/Databases.aspx) on available data from the Knesset site
* Living [document](https://docs.google.com/document/d/1eeQRrpGYuEJKAAtShPbjFn6i2f_UmQgg1caMTEs93ic/edit) with short list of ongoing project activities
