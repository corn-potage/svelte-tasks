<script>
    import { page } from '$app/stores';
    import BountyItem from '$lib/components/BountyItem.svelte';
    import Sidebar from '$lib/components/Sidebar.svelte';
    import CommentSection from '$lib/components/CommentSection.svelte';
  
    $: bountyId = $page.params.id;
    // Fetch bounty data based on bountyId
  </script>
  
  <div class="flex">
    <div class="w-3/4 pr-4">
      <BountyItem {bountyId} />
      <CommentSection {bountyId} />
    </div>
    <div class="w-1/4">
      <div class="sticky top-4">
        <Sidebar {bountyId} />
      </div>
    </div>
  </div>