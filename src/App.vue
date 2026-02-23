<script setup>
import { ref } from 'vue'

import Menubar from 'primevue/menubar';

import PageTitle from './components/PageTitle.vue';
import ImageDesc from './components/ImageDesc.vue';

import engineList from './assets/engine_list.jpg'
import modelingImage from './assets/modeling.png'
import simplicityImage from './assets/simplicity.png'

// Engine Development, 3D modeling, java-esc code

const current = ref(0);

const pageButtons = ref(
  [
    {
      label: 'Engine',
      command: engineDev,
    },
    {
      label: '3D',
      command: modeling
    },
    {
      label: 'Simplicity',
      command: simplicity
    }
  ]
);

const pageContent = ref(
    [
      {
        title: 'Engine',
        description: 'There are a few engines that can be used to make games, there are a few popular ones, and some that are up and coming.\n' +
            'Unity is known for its flexibility. It works well for both 2D and 3D games, making it a great choice for beginners and professionals alike. It supports many platforms, so your game can reach a wide audience. Plus, its large community means help is easy to find.\n' +
            'Unreal Engine stands out for its stunning graphics. It’s often used for AAA titles because it can handle complex visuals and physics. If you want your game to look next-level and have powerful tools, Unreal Engine is worth considering.\n' +
            'Godot is an open-source engine. It’s perfect if you want to avoid licensing fees and prefer an engine that is lightweight and easy to learn. It’s growing fast, especially for indie developers focused on 2D projects.\n' +
            'CryEngine offers high-end visuals and realistic environments. It’s great for shooters or games that need detailed worlds. While it might have a steeper learning curve, it rewards you with impressive graphical capabilities.\n' +
            'GameMaker is famous for its simplicity. If you want to make 2D games quickly, this is the engine to explore. It doesn’t require deep programming knowledge and is very user-friendly, which makes it popular for rapid prototyping and indie hits.',
        image: engineList,
        alignRight: true
      },
      {
        title: '3D',
        description: '3D modeling has become one of my favorite creative outlets. I especially enjoy modeling hard objects, where the geometry can be clean and well-maintained. ' +
            'There’s something incredibly satisfying about crafting sharp edges and details with exact control without relying on brushes. ' +
            'Unlike organic or rigging work, this sort modeling lets me focus purely on the structure and design. ' +
            'It’s a challenge that pushes me to keep improving my skills.\n' +
            'Looking at characters like the one in this image, I’m always impressed by the talent behind them. ' +
            'The way someone can create such detailed fur, expressive eyes, and lively poses blows me away. ' +
            'It reminds me how much dedication and knowledge go into mastering 3D art.' +
            'I deeply respect artists who bring characters to life through rigging and animation. ' +
            'Their work shows how limitless 3D modeling can be when combined with creativity. ' +
            'It motivates me to push my own boundaries and appreciate the full art of modeling, from clean, sharp surfaces to soft, organic forms.',
        image: modelingImage,
        alignRight: false
      },
      {
        title: 'Simplicity',
        description: 'I really enjoy creating abstractions for complicated C++ code. ' +
            'It’s like building a bridge between something complex and something much easier to understand and work with. ' +
            'C++ can get really dense with all its pointers, memory management, and templates. ' +
            'But when I design clean abstractions, I can hide all that complexity and make the code feel almost like Java. ' +
            'It’s satisfying to take a tangled mess of low-level details and turn it into something elegant and simple to use.\n' +
            'What really excites me is how these abstractions improve productivity. When the hard parts are hidden behind clear interfaces, ' +
            'it becomes easier to focus on solving actual problems instead of wrestling with syntax and technicalities. ' +
            'It pushes me to think carefully about design and clarity. ' +
            'Ultimately, it’s not just about writing code but about creating tools that make life easier for everyone who uses them. ' +
            'That’s why I find this kind of abstraction work so rewarding and fun.',
        image: simplicityImage,
        alignRight: true
      }
    ]
);

function engineDev() {
  current.value = 0;
}

function modeling() {
  current.value = 1;
}

function simplicity() {
  current.value = 2;
}

</script>

<template>
  <div class="alignToTop">
    <Menubar :model="pageButtons" class="menubarStyle"/>

    <PageTitle :title="pageContent[current].title" />
    <ImageDesc :text="pageContent[current].description" :image="pageContent[current].image" :right="pageContent[current].alignRight" />
  </div>
</template>

<style scoped>
  .alignToTop {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
  }
  .menubarStyle {
    justify-content: center;
    font-size: 24px;
    font-weight: 600;
  }
</style>
