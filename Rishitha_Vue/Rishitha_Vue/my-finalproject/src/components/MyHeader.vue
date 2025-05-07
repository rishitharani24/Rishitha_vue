<template>
  <div class="header-container">
    <h2>
      <span class="title-bold">{{ appTitle }}</span>
      <span class="title-normal caption-span">{{ caption }}!!!</span>
    </h2>
  </div>
</template>

<script>
export default {
  name: 'MyHeader',
  props: {
    appTitle: String,
    caption: String,
    author: String
  }
};
</script>

<style scoped>
.header-container {
  background-color: #bac33d;
  padding: 0.5em;
  margin: 0px auto;
  border-radius: 10px;
  text-align: center;
  max-width: 1200px;
  width: 80%;
  margin-top:1.5em;
}

h2{
  padding-bottom: 5px;

}

.title-bold {
  font-weight: bold;
  font-size: 32px;
}

.title-normal {
  font-weight: normal;
}

.caption-span::before {
  content: ' - ';
}
@media screen and (min-width: 500px) and (max-width: 1190px) {
  .header-container {
    width: 86%;
    padding: 0.75em;
  }
  h2{
    font-size: 19px;
  }
}

@media screen and (max-width: 500px) {
  .header-container {
  padding: 0.5em;
  margin: 1em auto;
  text-align: center;
  margin-bottom: 0px;
  width: 79%; 
  }

  .caption-span {
    display: block;
    margin-top: 5px;
  }

  .caption-span::before {
    content: '';
  }
  .title-normal{
    font-size: 16px;
  }
}
</style>