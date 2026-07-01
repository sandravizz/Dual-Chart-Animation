<script>
  import { ArcChart } from "layerchart";

  let { pair } = $props();
</script>

<ArcChart
  data={pair.data}
  key={pair.key}
  value={pair.value}
  innerRadius={0.65}
  cornerRadius={3}
  padAngle={0.01}
  legend={{ placement: "bottom" }}
  props={{
    legend: { class: "text-xs font-light" },
  }}
/>
