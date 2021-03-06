# Intro to pg_featureserv

This scenario gives you an introduction to pg_featureserv.

To use pg_featureserv, you need to have a PostGIS database with spatial data loaded in it. The database has already been started and the spatial data has already been loaded. This scenario will use data from New York City (NYC). This exercise shows how to connect pg_featureserv to your database and shows the resulting features. We also show an example of using user defined function through pg_featureserv. If you would like to learn more about creating funcitons, please review some of our other exercies. Data from this scenario is used in our other exercises as well, but the environements don't persist between scenarios.

We have already logged you into the PostgreSQL command line but, if you get disconnected here are the details on the database we are connecting to:

1. Username: groot
2. Password: password (same password for the postgres user as well)
3. A database named: nyc

# pg_featureserv

Pg_featureserv is a lightweight RESTful geospatial feature server for [PostGIS](https://postgis.net/), written in [Go](https://golang.org/).
It supports the [OGC API - Features](http://docs.opengeospatial.org/is/17-069r3/17-069r3.html) REST API standard.

Pg_featureserv implements the [OGC API - Features](http://docs.opengeospatial.org/is/17-069r3/17-069r3.html) standard. It uses PostGIS to provide geospatial functionality:
  * Transforming geometry data into the output coordinate system
  * Marshalling feature data into GeoJSON

Pg_featureserv requires PostGIS 2.4 or greater to operate.

That's great, but I'm sure you're asking "What does it do? How does it work?" pg_featureserv works by 1) taking an http request and converting it to the neccessary SQL to have PostGIS return the spatial data as a feature. 2) it connects to the target PostGIS database via a Database URL connection string. It runs in a completely stateless manner, any configuration of the data layers is driven by the underlying database. This means that data scientists, analysts and stewards can focus on maintaining their data and data structures. 

Now, let's get to showing you how easily it can be added to your PostGIS implementation and expose features. 

