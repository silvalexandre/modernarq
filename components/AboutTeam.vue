<template lang="pug">
  section
    .content
      h2 Equipe
      ul
        li(
          v-for="(item, index) in team"
          :key="index"
          :style="`background-image: url(${item.image})`"
          :title="item.name"
        )
          .title
            h3 {{ item.name }}
</template>

<script>
export default {
  props: ['team']
}
</script>

<style lang="postcss" scoped>
section {
  background: #212529;
}
.content {
  h2 {
    color: #f8f9fa;
  }
}
ul {
  list-style: none;
  padding-left: 0;
  display: flex;
  flex-wrap: wrap;
  width: 100%;
  li {
    margin-bottom: 1.5rem;
    width: 30%;
    margin-right: 3%;
    height: 200px;
    color: #f1f3f5;
    background-position: center center;
    background-repeat: no-repeat;
    background-size: cover;
    transition: all 300ms ease;
    &:hover {
      transform: translateY(-2px);
    }
    .title {
      position: relative;
      background: linear-gradient(transparent, rgba(0, 0, 0, 0.4) 90%);
      display: block;
      width: 100%;
      height: 100%;
      &:hover {
        h3 {
          color: #f8f9fa;
        }
      }
    }
    h3 {
      position: absolute;
      bottom: 1em;
      text-align: right;
      right: 1em;
      font-size: 1.15em;
      color: #dee2e6;
      transition: color 300ms ease;
    }
  }
}

@media screen and (max-width: 768px) {
  section {
    .content {
      ul {
        justify-content: space-between;
        li {
          width: 48%;
          margin-right: 0;
        }
      }
    }
  }
}
@media screen and (max-width: 425px) {
  section {
    .content ul {
      li {
        width: 100%;
      }
    }
  }
}
</style>

