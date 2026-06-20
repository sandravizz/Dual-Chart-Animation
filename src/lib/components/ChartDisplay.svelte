<script>
  import { LineChart, AreaChart, BarChart } from "layerchart";
  import { scaleBand, scaleLinear } from "d3-scale";

  let { pairs, activeIndex } = $props();

  const chartColor = "#6E63A8";

  function tickLabelProps() {
    return { fill: "rgba(42,38,89)", class:"text-xs font-light"};
  }
  function categoryIndex(pair) {
    const indexByItem = new Map(pair.data.map((d, i) => [d, i]));
    return (d) => indexByItem.get(d);
  }
  function categoryFormat(pair) {
    return (i) => String(pair.data[i]?.[pair.xKey] ?? "");
  }
  const xScales = {
    category: scaleBand,
    linear: scaleLinear,
  };
  function xScale(pair) {
    return xScales[pair.xType]();
  }
  function xAccessor(pair) {
    return pair.xType === "category" ? categoryIndex(pair) : pair.xKey;
  }
  function xFormat(pair) {
    return pair.xType === "category" ? categoryFormat(pair) : (v) => String(v);
  }
</script>

<div class="w-200 absolute top-40 left-1/2 -translate-x-1/2">
  {#each pairs as pair, i (pair.product)}
    <div class="absolute inset-0 transition-opacity duration-500 ease-[ease]" style:opacity={i === activeIndex ? 1 : 0}>
      <div class="mb-2 font-sans text-sm text-[#2A2659]">
        {pair.product}
      </div>

      <div class="h-140">
        {#if pair.kind === "line"}
          <LineChart
            data={pair.data}
            x={xAccessor(pair)}
            y={pair.yKey}
            series={[{ key: pair.product, value: pair.yKey }]}
            xScale={xScale(pair)}
            axis="x"
            props={{
              spline: { stroke: "#6E63A8", fill: "none" },
              xAxis: { tickLength: 0, format: xFormat(pair), tickLabelProps: tickLabelProps() },
            }}
          />

        {:else if pair.kind === "area"}
          <AreaChart
            data={pair.data}
            x={xAccessor(pair)}
            y={pair.yKey}
            series={[{ key: pair.product, value: pair.yKey }]}
            xScale={xScale(pair)}
            axis="x"
            props={{
              area: { fill: "#6E63A8", fillOpacity: 0.3, line: { stroke: "#6E63A8", fill: "none" } },
              xAxis: { tickLength: 0, format: xFormat(pair), tickLabelProps: tickLabelProps() },
            }}
          />

        {:else if pair.kind === "bar"}
          <BarChart
            data={pair.data}
            x={xAccessor(pair)}
            y={pair.yKey}
            series={[{ key: pair.product, value: pair.yKey }]}
            xScale={xScale(pair)}
            axis="x"
            props={{
              bars: { fill: "#6E63A8", stroke: "#6E63A8", strokeWidth: 0 },
              xAxis: { tickLength: 0, format: xFormat(pair), tickLabelProps: tickLabelProps() },
            }}
          />
        {/if}
      </div>
    </div>
  {/each}
</div>
