<script lang="ts">
    export let bountyId: string;
  
    // Mock data - replace with actual API calls
    let comments = [
      {
        id: 1,
        author: "Zen",
        timeAgo: "2h ago",
        content: "Notebooks have become a dominant interface for AI researchers. Their use will be very beneficial for the multidisciplinary work of Ethereum research.",
        avatar: "Z"
      },
      {
        id: 2,
        author: "Ian",
        timeAgo: "1d ago",
        content: "EQL can be an important tool and resource for helping to inform R&D discussions on Ethereum. By creating tooling around EQL you can extend the ecosystem functionality of decentralized and open source onchain data tools.",
        avatar: "I"
      }
    ];
  
    let newComment = "";
  
    function handleSubmitComment() {
      if (!newComment.trim()) return;
      
      // Add comment logic here
      comments = [...comments, {
        id: comments.length + 1,
        author: "You",
        timeAgo: "Just now",
        content: newComment,
        avatar: "Y"
      }];
  
      newComment = "";
    }
  </script>
  
  <section class="mt-8 space-y-6">
    <h2 class="text-xl font-semibold">Comments</h2>
  
    <div class="space-y-6">
      <!-- Comment input -->
      <div class="bg-white rounded-lg p-4">
        <textarea
          bind:value={newComment}
          placeholder="Post a comment..."
          class="w-full min-h-[100px] p-2 border rounded-lg resize-none focus:outline-none focus:ring-2 focus:ring-gray-200"
        ></textarea>
        <div class="mt-2 flex justify-end">
          <button 
            on:click={handleSubmitComment}
            class="bg-black text-white px-4 py-2 rounded-lg hover:bg-gray-800 transition-colors"
            disabled={!newComment.trim()}
          >
            Post
          </button>
        </div>
      </div>
  
      <!-- Comments list -->
      <div class="space-y-4">
        {#each comments as comment}
          <div class="bg-white rounded-lg p-4">
            <div class="flex items-start space-x-3">
              <div class="w-8 h-8 rounded-full bg-gray-200 flex items-center justify-center text-gray-600">
                {comment.avatar}
              </div>
              <div class="flex-1">
                <div class="flex items-center space-x-2">
                  <span class="font-medium">{comment.author}</span>
                  <span class="text-sm text-gray-500">{comment.timeAgo}</span>
                </div>
                <p class="mt-1 text-gray-700">{comment.content}</p>
              </div>
            </div>
          </div>
        {/each}
      </div>
    </div>
  </section>