<template>
  <nb-container :style="{ backgroundColor: '#fff' }">
    <nb-header>
      <nb-left>
        <nb-button
          transparent
          :onPress="() => this.props.navigation.openDrawer()"
        >
          <nb-icon name="menu" />
        </nb-button>
      </nb-left>
      <nb-body>
        <nb-title>Menu 2</nb-title>
      </nb-body>
      <nb-right />
    </nb-header>

    
        <nb-h3 class="text-color-white">Menu 2</nb-h3>
  </nb-container>
</template>

