<template>
  <div class="project-card">
    <div class="project-card__img-wrapper">
      <img :src="getImagePath" class="project-card__img" />
      <div class="project-card__actions">
        <a
          :href="project.url"
          class="project-card__button"
          target="_blank"
          rel="noreferrer noopener"
        >
          <img src="../assets/iconmonstr-video-13.svg" />
        </a>
        <a
          :href="project.git"
          class="project-card__button"
          target="_blank"
          rel="noreferrer noopener"
        >
          <img src="../assets/iconmonstr-github-1.svg" />
        </a>
      </div>
    </div>
    <div class="project-card__wrapper">
      <h3 class="project-card__title">{{ project.title }}</h3>
      <ul class="project-card__description">
        <li
          v-for="technology in project.technologies"
          :key="technology"
          :style="{
            border: `2px solid ${getColor(technology)}`,
            color: getColor(technology),
          }"
        >
          {{ technology }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import colors from "../data/colors";

export default {
  name: "ProjectCard",
  data() {
    return {
      colors,
    };
  },
  props: {
    project: {
      type: Object,
      required: true,
    },
  },
  computed: {
    getImagePath() {
      return new URL(this.project.image, import.meta.url);
    },
  },
  methods: {
    getColor(item) {
      return colors[item];
    },
  },
};
</script>

<style lang="scss" scoped>
.project-card {
  position: relative;
  &:hover {
    .project-card__actions {
      opacity: 1;
      background: #ffffff11;
      backdrop-filter: blur(3px);
      height: 100%;
      width: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
    }
  }

  &__button {
    display: block;
    text-decoration: none;
    z-index: 20;
    transition: filter 0.25s;

    img {
      width: 40px;
    }
    &:hover {
      filter: invert(0.3);
    }
  }

  &__img {
    max-width: 100%;
    box-shadow: 0px 2px 3px rgb(19 52 77 / 15%);
  }

  &__actions {
    opacity: 0;
    transition: opacity 0.2s;
    position: absolute;
    z-index: 20;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    display: flex;
    gap: 20px;
  }

  &__img-wrapper {
    position: relative;
    padding-bottom: 6px;
  }
  &__title {
    padding-bottom: 8px;
    font-size: 26px;
  }
  &__description {
    font-size: 12px;
    list-style: none;
    display: flex;
    gap: 8px;
  }
  li {
    padding: 5px 16px;
    color: white;
    border-radius: 15px;
    font-weight: 600;
  }
}
@media (max-width: 700px) {
  .project-card {
    &__title {
      font-size: 20px;
    }
    &__description {
      font-size: 10px;
      gap: 6px;
    }
  }
} ;
</style>
