<template>
  <div font-sans flex flex-col h-screen justify-between>
    <Header />
    <div container mx-a py-8>
      <slot/>
    </div>
    <Footer />
  </div>
</template>

<style>
body {
  margin: 0px;
}
</style>