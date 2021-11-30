# Beyond-2022.github.io
Project dedicated to the Beyond 2022 Project

## Setup

### Fuseki Server
To run the application, the user can use Apache Jena Fuseki application as SPARQL endpoint to load datasets. The application connects to `http://localhost:3030/Beyond_2022/query`

The user can upload dataset files for Beyond 2022 and can name it 'Beyond_2022' for the application to work without any change. Otherwise, the user can change the variable `b2022_URL` in search.html and slider.html to any other SPARQL endpoint. 

## Running the application
Once the user has setup the Knowledge Graphs and SPARQL endpoint, the user can start using the application by going to index.html. The user can click on Find By Years page to get timeline visualisation for pre-generated SPARQL requests. Otherwise, the user can go to Find By Century to select the time interval for which the timeline visualisation can be selected. 

## How the Application Works?

### Slider.html
This page allows the user to enter the time interval that they want and the page generates timeline visualisation for that period. For getting data from the user, we use input boxes which takes in two parameters from users - `from` and `to`.
These variables are used in the SPARQL request which is called `B2022_explore_query`. This request is sent to the SPARQL endpoint and we receive the following things from the endpoint :
1. Person's Name
2. Person's Birth Date
3. Person's Death Date
4. Person's Areas of Interest

The `B2022_explore_query` can be easily changed to get different data from the SPARQL endpoint. 

Once we have the data, we proceed to creating the timeline chart which is done using a JavaScript library which can be found here `https://github.com/vasturiano/timelines-chart`. We used the version v2.11.1 of this library and a local instance of it is stored locally with the name `timelines-chart.min.js`.
To plot the chart, we use names as the y-ordinate of the chart, area of interest to sort the data on the basis of colour and time as the x-ordinate.



