<script>
  import { LineChart } from "layerchart";
  import { timeFormat } from "d3-time-format";

  let { pair } = $props();

  const formatYear = timeFormat("%Y");
</script>

<LineChart
  data={pair.data}
  x={pair.xKey}
  series={pair.series}
  legend={{ placement: "bottom" }}
  props={{
    spline: { strokeWidth: 2.5 },
    xAxis: { tickLength: 0, format: formatYear, tickLabelProps: { fill: "rgba(42,38,89)", class: "text-xs font-light" } },
    yAxis: { tickLabelProps: { fill: "rgba(42,38,89)", class: "text-xs font-light" } },
    legend: { class: "text-xs font-light" },
  }}
/>
