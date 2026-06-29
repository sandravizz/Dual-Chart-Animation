<script>
  import { BarChart, defaultChartPadding } from "layerchart";
  import { scaleBand, scaleLinear } from "d3-scale";
  import { extent } from "d3-array";
  import { palette } from "$lib/colors";

  let { pair } = $props();

  const hasPerRowColor = $derived(pair.data.every((d) => d.color));

  const LINE_HEIGHT = 13;
  const MAX_CHARS_PER_LINE = 14;

  function wrapLabel(text, maxChars = MAX_CHARS_PER_LINE) {
    if (text.length <= maxChars) return [text];
    const words = text.split(" ");
    const lines = [];
    let current = "";
    for (const word of words) {
      const candidate = current ? `${current} ${word}` : word;
      if (candidate.length > maxChars && current) {
        lines.push(current);
        current = word;
      } else {
        current = candidate;
      }
    }
    if (current) lines.push(current);
    return lines;
  }
</script>

<BarChart
  data={pair.data}
  x={pair.yKey}
  y={pair.xKey}
  yScale={scaleBand().paddingInner(0.2).paddingOuter(0)}
  xScale={scaleLinear().domain(extent(pair.data, (d) => d[pair.yKey]))}
  xRange={({ width }) => [0, width]}
  orientation="horizontal"
  axis={false}
  labels
  padding={defaultChartPadding({ left: 2, right: 40 })}
  {...hasPerRowColor ? { c: pair.xKey, cRange: pair.data.map((d) => d.color) } : {}}
  series={[
    {
      key: pair.subtitle,
      value: pair.yKey,
      color: hasPerRowColor ? undefined : palette[9],
      props: { insets: { y: 0 }, strokeWidth: 0 },
    },
  ]}
  props={{
    labels: {
      class: "text-xs font-light",
      fill: "rgba(42,38,89)",
      format: (d) => `${d}${pair.valueSuffix ?? ""}`,
    },
    tooltip: { item: { label: "" } },
  }}
>
  {#snippet aboveMarks({ context })}
    {#each pair.data as d (d[pair.xKey])}
      {@const lines = wrapLabel(String(d[pair.xKey]))}
      {@const bandCenter = context.yScale(d[pair.xKey]) + context.yScale.bandwidth() / 2}
      {@const startY = bandCenter - ((lines.length - 1) * LINE_HEIGHT) / 2}
      <text x={8} class="text-xs font-light fill-[#FEFCFD] stroke-none">
        {#each lines as line, i (i)}
          <tspan x={8} y={startY + i * LINE_HEIGHT}>{line}</tspan>
        {/each}
      </text>
    {/each}
  {/snippet}
</BarChart>
