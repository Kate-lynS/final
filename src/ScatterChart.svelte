<script>
  import { onMount } from 'svelte';
  import Highcharts from 'highcharts';

  let chart;

  onMount(() => {
    chart = Highcharts.chart('scatterContainer', {  // ID as a string
      chart: {
        type: 'scatter',
        zoomType: 'xy'
      },
      title: {
        text: 'Education vs. Uninsured Rate by Race'
      },
      xAxis: {
        title: { text: '% with University Degree' }
      },
      yAxis: {
        title: { text: '% Uninsured' }
      },
      tooltip: {
        pointFormat: '{point.name}<br>Education: {point.x}%, Uninsured: {point.y}%'
      },
      series: [{
        name: 'Race Groups',
        colorByPoint: true,
        data: [
          { name: 'White', x: 35, y: 9.6 },
          { name: 'Hispanic', x: 20, y: 24.6 },
          { name: 'Black', x: 25, y: 12.9 },
          { name: 'Asian', x: 50, y: 9.2 },
          { name: 'AIAN', x: 15, y: 17.1 }
        ]
      }]
    });
  });
</script>

<!-- ID must match exactly what you referenced in the chart function -->
<div id="scatterContainer" style="width: 100%; height: 400px;"></div>
