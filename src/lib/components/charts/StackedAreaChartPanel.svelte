<script>
  import { AreaChart } from "layerchart";
  import { timeFormat } from "d3-time-format";
  import { tickLabelProps, legendProps } from "$lib/chart-theme";

  let { pair } = $props();

  const formatYear = timeFormat("%Y");
  const formatValue = (d) => `${d}${pair.valueSuffix ?? ""}`;
</script>

<AreaChart
  data={pair.data}
  x={pair.xKey}
  series={pair.series}
  seriesLayout="stack"
  legend={{ placement: "bottom" }}
  props={{
    area: { fillOpacity: 0.9, line: { strokeWidth: 1 } },
    xAxis: { tickLength: 0, format: formatYear, tickLabelProps },
    yAxis: { tickLabelProps, format: formatValue },
    legend: legendProps,
  }}
/>
