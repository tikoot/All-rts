<script lang="ts">
  import { onMount, onDestroy } from "svelte"
  import HeaderDropdown from "$lib/components/Header/HeaderDropdown/HeaderDropdown.svelte"
  import HeaderDropdownItem from "$lib/components/Header/HeaderDropdownItem/HeaderDropdownItem.svelte"
  import arrowDownIcon from "../../../../assets/icons/arrow-down-light.svg"
  import arrowUpIcon from "../../../../assets/icons/arrow-up-active.svg"

  export let text: string
  export let activeMenu: string
  export let menuId: string
  export let toggleMenu: (menuId: string) => void

  let dropdownElement: HTMLElement | null = null

  const handleClickOutside = (event: MouseEvent) => {
    if (dropdownElement && !dropdownElement.contains(event.target as Node)) {
      toggleMenu("")
    }
  }

  let isClient = false

  onMount(() => {
    isClient = typeof window !== "undefined"
    if (isClient) {
      document.addEventListener("click", handleClickOutside)
    }
  })

  onDestroy(() => {
    if (isClient) {
      document.removeEventListener("click", handleClickOutside)
    }
  })
</script>

<!-- svelte-ignore a11y-no-static-element-interactions -->
<!-- svelte-ignore a11y-click-events-have-key-events -->
<div
  class="relative"
  on:click={(e) => {
    e.stopPropagation()
    toggleMenu(menuId)
  }}
  bind:this={dropdownElement}
>
  <button
    class={`flex items-center ${activeMenu === menuId && "text-header-linkActive"}`}
  >
    <span class="mr-2 text-lg">{text}</span>
    <img
      src={activeMenu === menuId ? arrowUpIcon : arrowDownIcon}
      alt="dropdown"
      class="w-4"
    />
  </button>

  {#if activeMenu === menuId}
    <HeaderDropdown>
    <a target="_blank"  href="https://g.autumninteractive.com/rts-online/" class="block px-4 py-4 hover:text-opacity-75 hover:bg-gray-500">Play on browser</a>

      <HeaderDropdownItem text="Download"/>
   <!-- <HeaderDropdownItem text="Extra button space" />
      <HeaderDropdownItem text="Features" />
      <HeaderDropdownItem text="Mobile Requirements" /> -->
      <a href="/features" class="block px-4 py-4 hover:text-opacity-75 hover:bg-gray-500">Features</a>
     <!-- <a href="/" class="block px-4 py-4 hover:text-opacity-75 hover:bg-gray-500">Mobile Requirements</a> -->
    </HeaderDropdown>
  {/if}
</div>
