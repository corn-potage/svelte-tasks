<script>
    import Header from '$lib/components/Header.svelte';
    import BountyList from '$lib/components/BountyList.svelte';
    import Sidebar from '$lib/components/Sidebar.svelte';
  
    let searchQuery = '';
    let selectedSkills = [];
    let selectedAmount = null;
    let selectedEndDate = null;
    let sortBy = 'newest';
  
    function handleSearch() {
      // Implement search logic
    }
  
    function handleFilterChange() {
      // Implement filter logic
    }
  
    function handleSortChange() {
      // Implement sort logic
    }
  </script>
  
  
  <Header />
  <div class="max-w-7xl mx-auto px-4 py-8">
    <div class="flex gap-8">
        <div class="flex-1">
          <BountyList />
        </div>
        <div class="w-80">
          <div class="sticky top-4">
            <Sidebar/>
          </div>
        </div>
      </div>
    
  </div>