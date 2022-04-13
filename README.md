# JSTestChartProject



## Contents

- [Demo](https://github.com/BoukariFatma/JSTestChartProject)
- [ home.html](#html)
- [ data.json]
- [js](#js)
  - [bootstrap.min.js](#bootstrap.min.js)
  - [eco.js](#js)
  
- [css](#css)
  - [bootstrap.min.css](#bootstrap.min.css)
  - [style.css](#css)
  
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
      
#css
      body {
    margin: 0;
    padding: 0;
}

a {
    color: currentColor;
    text-decoration: none;
}
.header-logo{
display: inline-flex;
justify-content: center;
align-items: center;
border-radius: 50%;

}


.container {
    display: flex;
    justify-content: center;
    align-items: center;
}

.col-xs-3 {
    float: left;
    width: 270px;
    height: 270px;
    margin: 5px 8px;
}


.imageright {
    text-align: right;
}





.footer-dark {
    padding:50px 0;
    color:#f0f9ff;
    background-color:#282d32;
  }
  
 
  
  .footer-dark ul {
    padding:0;
    list-style:none;
    line-height:1.6;
    font-size:14px;
    margin-bottom:0;
  }
  
  .footer-dark ul a {
    color:inherit;
    text-decoration:none;
    opacity:0.6;
  }
  
  .footer-dark ul a:hover {
    opacity:0.8;
  }
  
  @media (max-width:767px) {
    .footer-dark .item:not(.social) {
      text-align:center;
      padding-bottom:20px;
    }
  }
  
  .footer-dark .item.text {
    margin-bottom:36px;
  }
  
  @media (max-width:767px) {
    .footer-dark .item.text {
      margin-bottom:0;
    }
  }
  
  .footer-dark .item.text p {
    opacity:0.6;
    margin-bottom:0;
  }
  

  
  @media (max-width:991px) {
    .footer-dark .item.social {
      text-align:center;
      margin-top:20px;
    }
  }
  
 
  
  .footer-dark .item.social > a:hover {
    opacity:0.9;
  }
  
  .footer-dark .copyright {
    text-align:center;
    padding-top:24px;
    opacity:0.3;
    font-size:13px;
    
    color: white;
    background-color: black;
  }



