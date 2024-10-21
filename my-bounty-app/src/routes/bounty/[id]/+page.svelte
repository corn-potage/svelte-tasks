<script lang="ts">
    import { page } from '$app/stores';
    import BountyItem from '$lib/components/BountyItem.svelte';
    import Sidebar from '$lib/components/Sidebar.svelte';
    import Header from '$lib/components/Header.svelte';
    import CommentSection from '$lib/components/CommentSection.svelte';
  
    $: bountyId = $page.params.id;
  </script>
  <Header/>
  <div class="max-w-7xl mx-auto px-4 py-8">
    <div class="flex gap-8">
      <div class="flex-1">
        <BountyItem {bountyId} />
        <CommentSection {bountyId} />
      </div>
      <div class="w-80">
        <div class="sticky top-4">
          <Sidebar {bountyId} />
        </div>
      </div>
    </div>
  </div>