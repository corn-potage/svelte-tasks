<script lang="ts">
    // Mock data - replace with actual API calls
    let bounties = [
      {
        id: 1,
        title: "Build an EQL Notebook app",
        sponsor: "Collective",
        dueDate: "Due in 4 weeks",
        description: "The brief for this app is to build a lightweight version of an interactive computing & data notebook for EQL. EVM Query Language is a powerful and expressive querying tool for...",
        reward: 5000,
        tags: ["UI/UX", "Full Stack", "SQL"],
        status: "Open"
      },
      {
        id: 2,
        title: "Add autocomplete feature to EQL web app",
        sponsor: "Collective",
        dueDate: "Due in 2 weeks",
        description: "Implement autocomplete functionality for the EQL web application to improve user experience...",
        reward: 500,
        tags: ["UI/UX", "Full Stack", "SQL"],
        status: "Open"
      }
    ];
  </script>
  
  <div class="space-y-4">
    {#each bounties as bounty}
      <a 
        href="/bounty/{bounty.id}" 
        class="block bg-white rounded-lg p-6 ring-1 ring-gray-300"
      >
        <div class="flex justify-between items-start">
          <div class="space-y-2">
            <div class="flex items-center space-x-2">
              <h2 class="text-xl font-semibold">{bounty.title}</h2>
              <span class="px-2 py-1 text-sm bg-green-100 text-green-800 rounded-full">
                {bounty.status}
              </span>
            </div>
            <div class="text-sm text-gray-600">
              {bounty.sponsor} • {bounty.dueDate}
            </div>
            <p class="text-gray-700 line-clamp-2">{bounty.description}</p>
            <div class="flex flex-wrap gap-2">
              {#each bounty.tags as tag}
                <span class="px-3 py-1 border border-gray-300 rounded-full text-sm">
                  {tag}
                </span>
              {/each}
            </div>
          </div>
          <div class="flex items-center">
            <div class="text-right">
              <span class="text-lg font-bold">{bounty.reward}</span>
              <span class="text-sm text-gray-600">USDC</span>
            </div>
          </div>
        </div>
      </a>
    {/each}
  </div>