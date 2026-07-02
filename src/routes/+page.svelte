<script>
  import { data } from "$lib/data/data";
  import ScrollySection from "$lib/components/ScrollySection.svelte";
  import Header from "$lib/components/Header.svelte";
  import Footer from "$lib/components/Footer.svelte";

  const chartSections = [
    data.slice(0, 4),
    data.slice(4, 7),
    data.slice(7, 11),
    data.slice(11, 15),
    data.slice(15, 17),
  ];

  const chapters = [
    {
      id: "chapter-1",
      label: "Chapter 1",
      title: "Convergence and the Transformation of Work",
      intro:
        "The first pillar of the Global Justice Report is full income convergence across countries by 2100. Today, average monthly incomes differ by a factor of 16 between the poorest and richest world regions – a gap that shapes every other dimension of well-being. The figures in this chapter show how that gap closes, and how productivity gains are redirected: annual work hours fall from about 2,100 to 1,000, men and women converge to equal shares of economic and domestic labour, and the economy shifts from material sectors like food and manufacturing toward education, health, leisure and culture.",
    },
    {
      id: "chapter-2",
      label: "Chapter 2",
      title: "Sufficiency, Energy and Climate",
      intro:
        "Neither sufficiency nor the energy transition can keep warming below 2°C on its own – together they can. This chapter compares the cumulative emissions and temperature outcomes of the report's core scenarios, decomposes what actually drives emissions down between 2026 and 2100, and shows why targeted sufficiency with structural change outperforms large uniform degrowth: converging to €60,000 per capita with sectoral transformation yields less warming than pushing everyone down to €15,000 without it.",
    },
    {
      id: "chapter-3",
      label: "Chapter 3",
      title: "Financing Global Justice",
      intro:
        "The institutional heart of the plan is the Global Justice Fund: it collects revenues from a global wealth tax and a global income tax, invests them through a World Sovereign Fund – an active portfolio of sustainable assets stabilizing at about 60% of world GDP – and distributes country dividends on an equal per-capita basis to finance climate investment, health and education. The figures in this chapter show the scale of that architecture: expenditures of around 10% of world GDP per year, roughly thirty times today's total development aid, and the convergence of education spending it makes possible.",
    },
    {
      id: "chapter-4",
      label: "Chapter 4",
      title: "Compressing Income and Wealth Inequality",
      intro:
        "Global inequality compression is both a social justice objective and the condition for financing the transition. This chapter traces the projected redistribution: the top 10% income share falls from 52% to 18% while the bottom 50% rises from 8% to 38%; the bottom half of wealth holders go from owning 2% of global wealth to 30%; the billionaire class shrinks from 6.4% of global wealth to 0.05%; and in every region of the world, large majorities end up with higher incomes than today.",
    },
    {
      id: "chapter-5",
      label: "Chapter 5",
      title: "Power, Representation and Reparations",
      intro:
        "Who holds the power, and who owes whom? This final chapter looks at global governance and historical responsibility: the transition from today's IMF voting rights – where Europe and North America hold four times their population share – to one person-one vote by 2050, and the finding that the North-South transfers induced by the Global Justice Fund remain well below what reparations for colonial and climate damages accumulated since 1800 would actually require.",
    },
  ];
</script>

<Header />

<div id="top">
  <section
    class="mx-auto w-[88vw] pt-36 pb-24 font-sans text-base-content lg:ml-[calc(43%-400px)] lg:w-200"
  >
    <h1 class="text-3xl font-semibold sm:text-4xl">
      The Global Justice Report
    </h1>
    <p class="mt-2 text-xl font-medium text-base-content/80 sm:text-2xl">
      A Plan for Equality &amp; Prosperity Within Planetary Boundaries
    </p>

    <a href="#charts" class="btn btn-primary mt-6">
      Jump to visualization
      <svg
        class="h-4 w-4"
        viewBox="0 0 24 24"
        fill="none"
        stroke="currentColor"
        stroke-width="2"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          d="M12 5v14m0 0-6-6m6 6 6-6"
        />
      </svg>
    </a>

    <p class="mt-8 text-lg leading-relaxed text-base-content/80">
      The Global Justice Report attempts to set out a new vision for global
      progress in the 21<sup>st</sup> century: grounding human development and equality
      in planetary habitability. It explores the conditions under which the world
      could move toward this horizon and traces an economically and ecologically
      consistent transition path from 2026 to 2100.
    </p>

    <p class="mt-4 text-lg leading-relaxed text-base-content/80">
      Its main conclusion is simple: it is possible to reconcile planetary
      habitability and high well-being for all, but only if the transformation
      rests on three pillars simultaneously.
      <strong>Fast decarbonization</strong> of energy systems is necessary. But
      we also need a major shift toward <strong>sufficiency</strong> –
      understood as a sharp reduction in labour hours and material footprint and
      large changes in consumption patterns, food habits, land use, and forest
      cover. In addition, neither decarbonization nor sufficiency can be
      financed and politically sustained without a
      <strong
        >drastic reduction in inequality of income, wealth and power</strong
      >, both between countries and within them. The compression of global
      inequality is not only compatible with deep decarbonization; it is a
      necessary condition for shared prosperity on a finite planet.
    </p>

    <p class="mt-4 text-lg leading-relaxed text-base-content/80">
      The Global Justice Report is the first attempt to propose a fully
      quantified plan going in this direction, combining four dimensions that
      today's debates often treat separately: redistribution at the world scale,
      a deep reform of the international financial and economic order, a radical
      transformation of energy systems, and substantial shifts in consumption
      patterns.
      <strong
        >Compared to most climate scenarios, including by the Intergovernmental
        Panel on Climate Change (IPCC), the main novelty</strong
      >
      is that we model all four dimensions together and
      <strong
        >place inequality and sufficiency at the center of the analysis</strong
      >.
    </p>

    <p class="mt-4 text-lg leading-relaxed text-base-content/80">
      Concretely: Per capita monthly national income converges to €5,000 in
      every country, closing a 16-fold gap. The share of the <strong
        >bottom half of global wealth increases from 2% to 30%</strong
      >, while the share of the billionaire class decreases from 6% to 0.05%.
      Nearly 90% of the world's population double their income while working
      roughly half as many hours as they do today. Warming reaches 1.8°C by
      2100, rather than over 4°C under baseline macroeconomic and policy trends.
    </p>

    <p class="mt-4 text-lg leading-relaxed text-base-content/80">
      The Global Justice Report is part of a <strong
        >broader international agenda for planetary habitability, social
        justice, and reform of the global financial architecture</strong
      > – including the Bridgetown Initiative launched by Barbados in 2022, combining
      international monetary reform, global wealth taxation, and climate finance;
      the recent Sevilla Commitment on development finance; the UN Tax Convention
      process; and G20 initiatives led by Brazil and South Africa on global inequality
      and the re-balancing of wealth and power within planetary limits. The main
      contribution of this report is to place these proposals within a quantified
      institutional framework, modeling socioeconomic convergence, temperature change,
      and distributional trajectories through 2100. Our broad conclusion is that
      it is possible to conceive of a quantitatively consistent plan for sustainable
      development on a global scale based on proposals such as the Bridgetown Initiative
      and other recent platforms.
    </p>

    <div class="mt-10 h-[160vh]">
      <div class="sticky top-0 grid h-screen items-center gap-6 overflow-y-auto py-10 sm:grid-cols-2">
      <div class="card card-dash card-md bg-base-100">
        <div class="card-body gap-4 text-base-content/80">
          <div class="flex items-center gap-3">
            <span class="badge badge-neutral">Box 1</span>
            <h3 class="card-title">Combining Global Equality and Planetary Habitability</h3>
          </div>
          <p>
            The Global Justice Report describes desirable future scenarios combining two key goals:
            <strong>socioeconomic equality</strong> (including full equality between countries, full
            gender equality in labour hours and pay, sharp compression of within-country income and
            wealth scales, combined with fair access to education, health and political voice), and
            <strong>planetary habitability</strong> (aligning global resource use within ecological
            boundaries, including a limitation of global temperature rise below 2°C).
          </p>
          <p>
            To avoid climate catastrophes, we show that <strong>sufficiency</strong> is required: a
            structural transformation of the economy involving shorter working hours, a lower material
            footprint, a shift from material-intensive sectors toward relatively immaterial sectors
            such as education and health, and major changes in food systems and land use. Rapid
            <strong>decarbonization of energy systems is also necessary</strong>, as is the sharp
            <strong>compression of income and wealth inequality</strong>. This compression is both a
            social justice objective and a condition for financing necessary climate investment and
            human capital expenditure and for sustaining political support from bottom- and
            middle-income classes in both the North and the South.
          </p>
        </div>
      </div>

      <div class="card card-dash card-md bg-base-100">
        <div class="card-body gap-4 text-base-content/80">
          <div class="flex items-center gap-3">
            <span class="badge badge-neutral">Box 2</span>
            <h3 class="card-title">Material and Monetary Accounting for Democratic Debate</h3>
          </div>
          <p>
            Economy and ecology cannot be debated apart: every economic activity has a material
            footprint, every ecological policy shapes incomes and wealth. To make these links visible,
            the Global Justice Report uses <strong>multidimensional social progress indicators</strong>.
            We set quantitative targets for global socioeconomic justice by combining two
            complementary languages: <strong>material accounting</strong> (work hours, sectoral
            shares, education and health, energy systems, GHG emissions, land use, forest cover,
            temperature levels) and <strong>monetary accounting</strong> (income and wealth scales
            between and within countries, progressive tax rates). The report draws on two centuries of
            historical data on global inequality and resource use, and on the recent literature on
            social progress, climate and colonial reparations.
          </p>
          <p class="font-semibold text-base-content">
            The Global Justice Report proposes a quantitatively and institutionally grounded step
            toward global justice. It does not seek to close the debate: it offers a transparent
            basis on which citizens, unions, parliaments, and international bodies can debate,
            contest, and decide the course of the coming decades.
          </p>
        </div>
      </div>
      </div>
    </div>
  </section>

  <div class="divider mx-auto w-[88vw] lg:ml-[calc(43%-400px)] lg:w-200"></div>

  <div id="charts"></div>
  {#each chapters as chapter, i (chapter.id)}
    <section
      id={chapter.id}
      class="mx-auto w-[88vw] scroll-mt-20 py-24 font-sans text-base-content lg:ml-[calc(43%-400px)] lg:w-200"
    >
      <p class="text-sm font-semibold uppercase tracking-widest text-base-content/50">
        {chapter.label}
      </p>
      <h2 class="mt-2 text-2xl font-semibold sm:text-3xl">{chapter.title}</h2>
      <p class="mt-4 text-lg leading-relaxed text-base-content/80">
        {chapter.intro}
      </p>
    </section>
    <ScrollySection pairs={chartSections[i]} />
  {/each}
</div>

<Footer />
