<script>
  import { PieChart } from "layerchart";

  let { pair } = $props();
</script>

<PieChart
  data={pair.data}
  key={pair.key}
  value={pair.value}
  c="color"
  legend={{ placement: "bottom" }}
  props={{
    legend: { class: "text-xs font-light" },
  }}
/>
