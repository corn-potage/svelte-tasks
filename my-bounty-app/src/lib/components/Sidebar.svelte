<script lang="ts">
    export let bountyId: string | undefined = undefined;
    
    // Different content based on whether we're on the list page or item page
    const isItemPage = !!bountyId;
  
    // Mock data for item page
    const itemPageData = {
      sponsor: {
        name: "Collective",
        image: "/api/placeholder/40/40"
      },
      reward: {
        total: "5000 USDC",
        breakdown: [
          { place: "1st place", amount: "3500 USDC" },
          { place: "2nd place", amount: "1000 USDC" },
          { place: "3rd place", amount: "500 USDC" }
        ]
      },
      tags: ["UI/UX", "Full Stack", "SQL"],
      deadline: {
        date: "Oct 1, 2024 at 09:00",
        timeLeft: "Due in 4 weeks"
      }
    };
  </script>
  
  {#if isItemPage}
    <div class="bg-white rounded-lg p-6 space-y-6 ring-1 ring-gray-300">
      <div class="flex items-center space-x-3">
        <img 
          src={itemPageData.sponsor.image} 
          alt={itemPageData.sponsor.name}
          class="w-10 h-10 rounded-full"
        />
        <div>
          <h3 class="font-semibold">{itemPageData.sponsor.name}</h3>
          <span class="text-sm text-gray-600">Sponsor</span>
        </div>
      </div>
      <hr class="border-gray-300 my-4" />
      <div class="space-y-2">
        <div class="space-y-1">
        <div class="flex justify-between text-sm">
            <span class="font-medium">5000 USDC</span>
            <span class="text-gray-500">Total prize pool</span>
        </div>
        </div>
      </div>
      <hr class="border-gray-300 my-4" />
      <div class="space-y-2">
        <div class="space-y-1">
          {#each itemPageData.reward.breakdown as prize}
            <div class="flex justify-between text-sm">
                <span class="font-medium">{prize.amount}</span>
              <span class="text-gray-500">{prize.place}</span>
            </div>
          {/each}
        </div>
      </div>
      <hr class="border-gray-300 my-4" />
      <div class="space-y-2">
        <div class="flex items-start text-sm">
        <!-- Example icon from Heroicons or Font Awesome -->
        <svg class="w-4 h-4 mr-1" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
        </svg>
        </div>
        <div class="flex flex-wrap gap-2">
          {#each itemPageData.tags as tag}
            <span class="px-3 py-1 border border-gray-300 rounded-full text-sm">
              {tag}
            </span>
          {/each}
        </div>
      </div>
      <hr class="border-gray-300 my-4" />
      <div class="space-y-2">
        <div class="flex items-start text-sm">
          <!-- Clock icon -->
          <svg class="w-5 h-5 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6 1a9 9 0 1 1-18 0 9 9 0 0 1 18 0z"></path>
          </svg>
          <div>
            <p class="font-semibold">{itemPageData.deadline.timeLeft}</p>
            <p class="text-gray-500">{itemPageData.deadline.date}</p>
          </div>
        </div>
      </div>
  
      <button class="w-full bg-black text-white py-3 px-4 rounded-lg hover:bg-gray-800 transition-colors">
        Submit entry
      </button>
    </div>
  {:else}
    <div class="bg-blue-200 text-blue-600 rounded-lg p-6 ">
      <h2 class="text-xl font-semibold mb-2">Anyone can create bounties</h2>
      <p class="text-gray-600 mb-4">Create your first bounty within minutes.</p>
      <a 
        href="/create" 
        class="block text-center bg-white text-black py-3 px-4 rounded-lg hover:bg-gray-800 transition-colors"
      >
        Learn more
      </a>
    </div>
  {/if}