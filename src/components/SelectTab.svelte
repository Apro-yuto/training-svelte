<script>
  import { createEventDispatcher } from 'svelte'
  export let current

  const tabsObject = [
    {
      'title': '全て',
      'statusName': 'all',
    },
    {
      'title': '完了',
      'statusName': 'done',
    },
    {
      'title': '未完了',
      'statusName': 'notDone',
    }
  ]

  const dispatch = createEventDispatcher()

  const toggleCurrentStatus = (currentStatus) => {
    dispatch('changeCurrentStatus', currentStatus)
  }

</script>

<ul class="main_contents_tabs">
  {#each tabsObject as tab}
    <li
      on:click={() => toggleCurrentStatus(tab.statusName)}
      style={current === tab.statusName ? 'background-color: #fff;' : ''}
      class="main_contents_tabs_tab">
      {tab.title}
    </li>
  {/each}
</ul>

<style>
.main_contents_tabs {
  display: flex;
  justify-content: left;
}
.main_contents_tabs_tab {
  width: 140px;
  background-color: transparent;
  border-radius: 20px 20px 0 0;
  text-align: center;
  padding: 12px 0;
  color: #000;
  border: 1px solid #707070;
}
</style>
