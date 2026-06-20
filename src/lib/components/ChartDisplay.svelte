<script>
  import AreaChartPanel from "./AreaChartPanel.svelte";
  import BarChartPanelHorizontal from "./BarChartPanelHorizontal.svelte";
  import LineChartPanel from "./LineChartPanel.svelte";
  import ScatterChartPanel from "./ScatterChartPanel.svelte";
  import PieChartPanel from "./PieChartPanel.svelte";
  import DonutChartPanel from "./DonutChartPanel.svelte";
  import GroupedBarChartPanel from "./GroupedBarChartPanel.svelte";

  let { pairs, activeIndex } = $props();
</script>

<div class="w-200 absolute top-20 left-1/2 -translate-x-1/2">
  {#each pairs as pair, i (pair.product)}
    <div
      class="absolute inset-0 transition-opacity duration-500 ease-[ease]"
      style:opacity={i === activeIndex ? 1 : 0}
    >
      <div class="mb-2 font-sans text-sm text-[#2A2659]">
        {pair.product}
      </div>

      <div class="h-140 flex gap-6">
        {#if pair.kind === "area"}
          <AreaChartPanel {pair} />
        {:else if pair.kind === "bar"}
          <BarChartPanelHorizontal {pair} />
        {:else if pair.kind === "line"}
          <LineChartPanel {pair} />
        {:else if pair.kind === "scatter"}
          <ScatterChartPanel {pair} />
        {:else if pair.kind === "pie"}
          <PieChartPanel {pair} />
        {:else if pair.kind === "donut"}
          <DonutChartPanel {pair} />
        {:else if pair.kind === "grouped-bar"}
          <GroupedBarChartPanel {pair} />
        {/if}
      </div>
    </div>
  {/each}
</div>
