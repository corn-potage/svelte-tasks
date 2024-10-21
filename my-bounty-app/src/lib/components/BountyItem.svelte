<script lang="ts">
    export let bountyId: string;
  
    // Mock data - replace with actual API call using bountyId
    const bounty = {
      title: "Create AI powered funding tool Allo-matic",
      status: "Open",
      sponsor: "Dingcoin",
      publishedDate: "Published 7 days ago",
      overview: `Dingcoin is continuously looking to improve the allocation of grant capital and leverage data to 
      deliver higher impact results. Build a toolkit that leverages LLMs for capital allocation inspired by 
      Dingcoin's Allo protocol, we believe we can iterate on allocation mechanisms, rather than serving as 
      a router, the tool should be able to:`,
      requirements: [
        "break down mechanisms into primitives that can more composably fit together",
        "streamline, improve, and automate these mechanisms through agentic workflows and human evaluation",
        "aggregate non-allo use cases in and out the Ethereum space"
      ],
      technicalRequirements: [
        {
          title: "PROGRAM-RECC-AGENT",
          description: "recommending allocations strategy based on program manager needs"
        },
        {
          title: "DEPLOYMENT AGENT",
          description: "links to relevant applications, contracts and parameters for you to run your round"
        },
        {
          title: "CASE STUDY AGENT",
          description: "recommends similar case studies and ongoing grant programs based on projects need"
        },
        {
          title: "MECHANISM SYNETHSIS",
          description: "designs new mechanisms with code and explanation"
        }
      ]
    };
  </script>
  
  <article class="bg-white rounded-lg p-6 space-y-6">
    <header class="space-y-4">
      <div class="flex items-center justify-between">
        <h1 class="text-3xl font-bold">{bounty.title}</h1>
        <div class="flex items-center space-x-4">
          <button class="text-gray-600 hover:text-gray-800">
            <span class="mr-2">Share</span>
          </button>
          <button class="text-gray-600 hover:text-gray-800">
            <span class="mr-2">Save</span>
          </button>
        </div>
      </div>
      <div class="flex items-center space-x-4 text-sm text-gray-600">
        <span>{bounty.status}</span>
        <span>•</span>
        <span>{bounty.publishedDate}</span>
      </div>
    </header>
  
    <section class="space-y-4">
      <h2 class="text-xl font-semibold">Overview</h2>
      <p class="text-gray-700">{bounty.overview}</p>
      <ul class="list-disc pl-6 space-y-2">
        {#each bounty.requirements as requirement}
          <li class="text-gray-700">{requirement}</li>
        {/each}
      </ul>
    </section>
  
    <section class="space-y-4">
      <h2 class="text-xl font-semibold">Technical requirements</h2>
      <div class="space-y-4">
        {#each bounty.technicalRequirements as requirement}
          <div class="border-b pb-4">
            <h3 class="font-semibold">{requirement.title}</h3>
            <p class="text-gray-700">{requirement.description}</p>
          </div>
        {/each}
      </div>
    </section>
  </article>