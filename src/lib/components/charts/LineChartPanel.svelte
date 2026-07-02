<script>
  import { LineChart } from "layerchart";
  import { scaleLog } from "d3-scale";
  import { timeFormat } from "d3-time-format";
  import { tickLabelProps, legendProps } from "$lib/chart-theme";

  let { pair } = $props();

  const formatYear = timeFormat("%Y");
  const formatValue = (d) => `${d}${pair.valueSuffix ?? ""}`;
</script>

<LineChart
  data={pair.data}
  x={pair.xKey}
  series={pair.series}
  yScale={pair.yScaleType === "log" ? scaleLog() : undefined}
  yDomain={pair.yDomain}
  legend={{ placement: "bottom" }}
  props={{
    spline: { strokeWidth: 2.5 },
    xAxis: { tickLength: 0, format: formatYear, tickLabelProps },
    yAxis: { tickLabelProps, ticks: pair.yTicks, format: formatValue },
    legend: legendProps,
  }}
/>
