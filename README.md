# JSTestChartProject



## Contents

- [Demo](https://github.com/BoukariFatma/JSTestChartProject)
- [ home.html]
- [ data.json]
- [js](#js)
  - [bootstrap.min.js](#bootstrap.min.js)
  - [eco.js](#eco.js)
  
- [css](#css)
  - [bootstrap.min.css](#bootstrap.min.css)
  - [style.css](#style.css)
  
-[img]
  
## html
<!DOCTYPE HTML>
<html>

<head>
    <link rel="stylesheet" href="css/bootstrap.min.css">
    <link rel="stylesheet" href="css/style.css">
    <script>
        window.onload = function() {

            var chart = new CanvasJS.Chart("chartContainer", {
                animationEnabled: true,
                title: {
                    text: "Technical Assessment"
                },
                axisX: {
                    valueFormatString: "11 04 2022 hh mm ss",
                    crosshair: {
                        enabled: true,
                        snapToDataPoint: true
                    }
                },
                axisY: {
                    title: "Value",
                    valueFormatString: "0000",
                    crosshair: {
                        enabled: true,
                        snapToDataPoint: true,
                        labelFormatter: function(e) {
                            return "" + CanvasJS.formatNumber(e.value, "000");
                        }
                    }
                },
                data: [{
                    type: "area",
                    xValueFormatString: "11 avr 2022 hh mm ss",
                    yValueFormatString: "000",
                    dataPoints: [{
                
                          }]
            });
            chart.render();

        }
    </script>
</head>
  
<body>
      

    <header>
        <div class="row">
            <div class="col-3">
                <a class="header-logo" href="#"><img src="img/elcologo.PNG"></a>
               
            </div>
    <div id="chartContainer" style="height: 300px; width: 100%;"></div>
    <script src="https://canvasjs.com/assets/script/canvasjs.min.js"></script>
</body>

## js
      
       let chart = new CanvasJS.Chart("chartContainer",{
    exportEnabled: true,
    title:{
        text:"assissment Live Chart with Data-Points from External JSON"
    },
    data: [{
        type: "spline",
        dataPoints : dataPoints,
    }]
});

$.getJSON("data.json", function(data) {  
    $.each(data, function(key, value){
        dataPoints.push({x: value[0], y: parseInt(value[1])});
    });
    dpsLength = dataPoints.length;
    chart.render();
    updateChart();
});
