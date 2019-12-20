# pyramid_oereb_mfp (ÖREB-Server Print)

``pyramid_oereb_mfp`` is an implementation of a static extract (PDF) for
the [pyramid_oereb server](https://github.com/openoereb/pyramid_oereb)
using [MapFish-Print](https://github.com/mapfish/mapfish-print>).

## Prerequisites
Starting version [1.5.0](https://github.com/openoereb/pyramid_oereb_mfp/releases/tag/v1.5.0),
you require MapFish-Print in version 3.20.0 or later, which introduces the ``allowTransparency``
feature (required for PDF/A compliance).
We recommend you run the dockerized MapFish-Print. If this is not possible for you, you need to
ensure the following:

1. verify that Java is installed in version 8 or later on your system (required by this MapFish-Print version)
2. add the Cadastra font package to your print app, by creating a folder ``WEB-INF/lib`` in the app
  and copying the Cadastra.jar file to it.
You can find a copy of this package
[in the MapFish-Print repository](https://github.com/mapfish/mapfish-print/tree/master/core/docker/usr/local/tomcat/webapps/ROOT/WEB-INF/lib).

## Running local tests:
To run a local instance of mapfish-print (in docker) with the oereb templates, do:

``make serve``

### Prerequisites for running local tests:
make sure docker is installed. In addition, if you have not done
this before, you need to declare the ``print-network`` for docker,
so that your local ``pyramid_oereb`` docker container can access
your local ``print`` container, as follows:
``sudo docker network create print-network``

## Project history
This subproject was created consequently of
[Issue 459](https://github.com/openoereb/pyramid_oereb/issues/459).
Access the history of the templates by using this
[openoereb/pyramid_oereb commit](https://github.com/openoereb/pyramid_oereb/commit/352970f3504385a462797dab7de30fd00896b922),
which deleted the templates there as a starting point.
