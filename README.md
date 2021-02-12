# piano-duo

1. Please create a folder in `@/components/global/hero` and inside create a file called `hero-default.vue` and `hero-home.vue`. This should be a replacement for all hero sections on the pages. They share the exact same html code on every page, so please put it there. From the pages, import the correct component (`hero-home.vue` for homepage and `hero-default.vue` for all other pages) and just send the `h1 title` and the `span subtitle` from the page, when you import the component.

2. I didn't mean to split hero section and the rest of the page into 2 sections for each page. I meant to split actual sections into sections. When you write a new html `row`, it makes sense to create a new section component for each row. This improves maintainability and makes code easier to read and faster to understand.

A maintainable and healthy `.vue` file should't have much more than 100 lines of code.
The clean homepage would look like this (referring to you css class naming convention for your rows):

```vue
<template>

<div class="wrapper">

  <Header/>
  <HeroHome/>
  <SectionMainRow>
  <SectionMainRow2>
  <SectionMainRow>
  <SectionMainRow2>
  <SectionTextBoxNews>
  <SectionNewsRow>
  <SectionTextBoxNews2>
  <SectionHauptabox>
  <Footer/>
  
</div>

</template>

<script>


import HeroHome from '@/components/global/hero/hero-home.vue'
import SectionMainRow from '@/components/pages/homePage/section-main-row.vue'
import SectionMainRow2 from '@/components/pages/homePage/section-main-row-2.vue'
//etc...the same for all sections

export default {
  components:{
    HeroHome, //must have its own scoped scss
    SectionMainRow, //must have its own scoped scss
    SectionMainRow2 //must have its own scoped scss,
    //etc...the same for all sections
  }
}
</script>
<style lang="scss" scoped>

//don't write css here

</style>

```

**also, all css must be split into components**

3. Please also use `import` statements for all components like I did in the example above. It makes the code a lot easier to read for other developers that could be working on the project in the future.

4. Please move **all** `background-image` css properties into a html `style` tag in the template, so we can fill that content dynamically.

5. completely remove the `@/assets/main.scss/pages.scss/_global.scss` file and write the css into the `hero-default.vue` and `hero-home.vue` files. If they share the same `scss` code, you can use a mixin.

6. responsive css in each component is still written in css syntax, please convert to scss syntax.


