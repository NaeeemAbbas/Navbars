<template>
  <div :class="cn('relative', className)">
    <div
      class="group relative cursor-pointer"
      @click="isVideoOpen = true"
    >
      <img
        :src="thumbnailSrc"
        :alt="thumbnailAlt"
        width="1920"
        height="1080"
        class="w-full rounded-md  shadow-lg transition-all duration-200 ease-out group-hover:brightness-[0.8]"
      />
      <div class="absolute inset-0 flex scale-[0.9] items-center justify-center rounded-2xl transition-all duration-200 ease-out group-hover:scale-100">
        <div class="flex size-28 items-center justify-center rounded-full bg-primary/10 backdrop-blur-md">
          <div
            class="relative flex size-20 scale-100 items-center justify-center rounded-full bg-gradient-to-b from-primary/30 to-primary shadow-md transition-all duration-200 ease-out group-hover:scale-[1.2]"
          >
            <Play
              class="size-8 scale-100 fill-white text-white transition-transform duration-200 ease-out group-hover:scale-105"
              style="filter: drop-shadow(0 4px 3px rgb(0 0 0 / 0.07)) drop-shadow(0 2px 2px rgb(0 0 0 / 0.06))"
            />
          </div>
        </div>
      </div>
    </div>
    
    <!-- Video Modal -->
    <Teleport to="body">
      <Transition
        enter-active-class="transition-opacity duration-300"
        leave-active-class="transition-opacity duration-300"
        enter-from-class="opacity-0"
        enter-to-class="opacity-1"
        leave-from-class="opacity-1"
        leave-to-class="opacity-0"
      >
        <div
          v-if="isVideoOpen"
          class="fixed inset-0 z-50 flex items-center justify-center bg-black/50 backdrop-blur-md"
          @click="isVideoOpen = false"
        >
          <Transition
            :enter-active-class="getTransitionClasses().enter"
            :leave-active-class="getTransitionClasses().leave"
            :enter-from-class="getTransitionClasses().enterFrom"
            :enter-to-class="getTransitionClasses().enterTo"
            :leave-from-class="getTransitionClasses().leaveFrom"
            :leave-to-class="getTransitionClasses().leaveTo"
          >
            <div
              v-if="isVideoOpen"
              class="relative mx-4 aspect-video w-full max-w-4xl md:mx-0"
              @click.stop
            >
              <button
                @click="isVideoOpen = false"
                class="absolute -top-16 right-0 rounded-full bg-neutral-900/50 p-2 text-xl text-white ring-1 backdrop-blur-md dark:bg-neutral-100/50 dark:text-black"
              >
                <X class="size-5" />
              </button>
              <div class="relative isolate z-[1] size-full overflow-hidden rounded-2xl ">
                <iframe
                  :src="videoSrc"
                  class="size-full rounded-2xl"
                  allowfullscreen
                  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                ></iframe>
              </div>
            </div>
          </Transition>
        </div>
      </Transition>
    </Teleport>
  </div>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'
import { Play, X } from 'lucide-vue-next'

type AnimationStyle =
  | "from-bottom"
  | "from-center"
  | "from-top"
  | "from-left"
  | "from-right"
  | "fade"
  | "top-in-bottom-out"
  | "left-in-right-out"

interface Props {
  animationStyle?: AnimationStyle
  videoSrc: string
  thumbnailSrc: string
  thumbnailAlt?: string
  className?: string
}

const props = withDefaults(defineProps<Props>(), {
  animationStyle: 'from-center',
  thumbnailAlt: 'Video thumbnail',
  className: ''
})

const isVideoOpen = ref(false)

// Utility function to merge classes (similar to cn from utils)
const cn = (...classes: (string | undefined)[]) => {
  return classes.filter(Boolean).join(' ')
}

const getTransitionClasses = () => {
  const animations = {
    "from-bottom": {
      enter: "transition-all duration-300 ease-out",
      leave: "transition-all duration-300 ease-out",
      enterFrom: "translate-y-full opacity-0",
      enterTo: "translate-y-0 opacity-100",
      leaveFrom: "translate-y-0 opacity-100",
      leaveTo: "translate-y-full opacity-0"
    },
    "from-center": {
      enter: "transition-all duration-300 ease-out",
      leave: "transition-all duration-300 ease-out",
      enterFrom: "scale-50 opacity-0",
      enterTo: "scale-100 opacity-100",
      leaveFrom: "scale-100 opacity-100",
      leaveTo: "scale-50 opacity-0"
    },
    "from-top": {
      enter: "transition-all duration-300 ease-out",
      leave: "transition-all duration-300 ease-out",
      enterFrom: "-translate-y-full opacity-0",
      enterTo: "translate-y-0 opacity-100",
      leaveFrom: "translate-y-0 opacity-100",
      leaveTo: "-translate-y-full opacity-0"
    },
    "from-left": {
      enter: "transition-all duration-300 ease-out",
      leave: "transition-all duration-300 ease-out",
      enterFrom: "-translate-x-full opacity-0",
      enterTo: "translate-x-0 opacity-100",
      leaveFrom: "translate-x-0 opacity-100",
      leaveTo: "-translate-x-full opacity-0"
    },
    "from-right": {
      enter: "transition-all duration-300 ease-out",
      leave: "transition-all duration-300 ease-out",
      enterFrom: "translate-x-full opacity-0",
      enterTo: "translate-x-0 opacity-100",
      leaveFrom: "translate-x-0 opacity-100",
      leaveTo: "translate-x-full opacity-0"
    },
    "fade": {
      enter: "transition-opacity duration-300",
      leave: "transition-opacity duration-300",
      enterFrom: "opacity-0",
      enterTo: "opacity-100",
      leaveFrom: "opacity-100",
      leaveTo: "opacity-0"
    },
    "top-in-bottom-out": {
      enter: "transition-all duration-300 ease-out",
      leave: "transition-all duration-300 ease-out",
      enterFrom: "-translate-y-full opacity-0",
      enterTo: "translate-y-0 opacity-100",
      leaveFrom: "translate-y-0 opacity-100",
      leaveTo: "translate-y-full opacity-0"
    },
    "left-in-right-out": {
      enter: "transition-all duration-300 ease-out",
      leave: "transition-all duration-300 ease-out",
      enterFrom: "-translate-x-full opacity-0",
      enterTo: "translate-x-0 opacity-100",
      leaveFrom: "translate-x-0 opacity-100",
      leaveTo: "translate-x-full opacity-0"
    }
  }
  
  return animations[props.animationStyle]
}
</script>

<style scoped>
/* Custom styles for primary color if needed */
.bg-primary\/10 {
  background-color: rgb(59 130 246 / 0.1);
}

.from-primary\/30 {
  --tw-gradient-from: rgb(59 130 246 / 0.3) var(--tw-gradient-from-position);
  --tw-gradient-to: rgb(59 130 246 / 0) var(--tw-gradient-to-position);
  --tw-gradient-stops: var(--tw-gradient-from), var(--tw-gradient-to);
}

.to-primary {
  --tw-gradient-to: rgb(59 130 246) var(--tw-gradient-to-position);
}
</style>