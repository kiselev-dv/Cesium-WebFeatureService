# Cesium-WebFeatureService
A module which when integrated into cesium loads vector features from a Web Feature Service provider


After integration into Cesium the provider is initialised as

    //initialise cesium
    var viewer = new Cesium.Viewer("cesiumContatiner");
    
    //initialise WFS provider
     var wfs = new Cesium.WebFeatureServiceImageryProvider({
     
      url : "http://localhost:8080/geoserver/web",
      layers : "vectorLayerName",
      viewer : viewer
      
    });
    

The module loads features by sending a GET request to the server instance and parsing the GML data received t
get the coordinates.
The features requested dependes on the current viewing volume. Only the features visible in the current viewing
volume are requested to minimise network traffic.


