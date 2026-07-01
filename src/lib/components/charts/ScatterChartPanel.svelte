<script>
  import { ScatterChart } from "layerchart";
  import { palette } from "$lib/colors";

  let { pair } = $props();
</script>

<ScatterChart
  data={pair.data}
  x={pair.xKey}
  y={pair.yKey}
  c={pair.cKey}
  cRange={palette}
  legend={{ placement: "bottom" }}
  props={{
    points: { r: 6, fillOpacity: 0.85, strokeWidth: 0 },
    xAxis: { tickLabelProps: { fill: "rgba(42,38,89)", class: "text-xs font-light" } },
    yAxis: { tickLabelProps: { fill: "rgba(42,38,89)", class: "text-xs font-light" } },
    legend: { class: "text-xs font-light" },
  }}
/>
