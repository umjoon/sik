
<HTML><HEAD>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<style> div { position: relative; width:80vw; margin: auto } </style>
</HEAD><BODY>
<div><canvas id="myChart"></canvas></div>
<script>
  const mylabels = [];  const mydata = [];
  const datainfo = {
    labels: mylabels,
    datasets: [{
      label: 'PI(3.14) Calculation',
      backgroundColor: 'rgb(255, 99, 132)',
      borderColor: 'rgb(255, 99, 132)',
      data: mydata
    }]
  };
  const config = {
    type: 'line',
    data: datainfo,
    options: {}
  };
</script>
<script>
  const myChart = new Chart(
      document.getElementById('myChart'),
      config
  ); 
  k = 0;
  dl = datainfo.labels;
  dd = datainfo.datasets[0].data
  for ( i=1 ; i<=100000000 ; i++ ) {
     x = Math.random();
     y = Math.random()
     if ( (x*x + y*y) <= 1 ) k++
     if ( i == 10 ) { redraw(i) }
     if ( i == 100 ) { redraw(i) }
     if ( i == 1000 ) { redraw(i) }
     if ( i == 10000 ) { redraw(i) }
     if ( i == 100000 ) { redraw(i) }
     if ( i == 1000000 ) { redraw(i) }
     if ( i == 10000000 ) { redraw(i) }
     if ( i == 100000000 ) { redraw(i)}
     if ( (i % 10000000) == 0 ) console.log(i)
  }
  function redraw(t) {
    dl.push(t); dd.push(4*k/t);
    myChart.update();
  }
</script>
</BODY>
</HTML>
