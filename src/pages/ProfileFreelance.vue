<template>
  <div>
    <div class="page-header clear-filter" filter-color="orange">
      <div
        class="page-header-image"
        style="background-image:url('img/test.jpg')"
      >
      </div>
      <div class="container">
        <div class="photo-container">
          <img src="img/ryan.jpg" alt="" />
        </div>
        <h3 class="title"> {{ name }} </h3>
        <p class="category">{{ category }}</p>
        <div class="content">
          <div class="rating_wrap">
            <h1 class="rating text-warning">
              <i class="far fa-star"></i>
              {{ rating }}
            </h1>
          </div>
        </div>
      </div>
    </div>
    <div class="section">
      <div class="container">
        <h3 class="title">Обо мне</h3>
        <h5 class="description">
            <div>  
                {{ about }}
                   <i class="now-ui-icons design-2_ruler-pencil" @click="visible=!visible"></i>
            </div>
            <div v-show="visible">
                <input v-model="editAbout" class="input" size="70px"/>
            </div>
        </h5>
      </div>
    </div>
  </div>
</template>
<script>
import { Tabs, TabPane } from '@/components';

export default {
  name: 'profile_freelance',
  bodyClass: 'profile-page',
  components: {
    Tabs,
    TabPane
  },
  data() {
    return {
      editable: false,
      name: 'Ryan Scheinder',
      category: 'Пожарная безопасность',
      rating: 4.3,
      about: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quia accusamus sequi hic ea laborum saepe architecto non repellat animi dignissimos.',
      editAbout: '',
      visible: false
    }
  },
  methods: {
 
  },
    updated() {
        this.about = this.editAbout; 
    } 
};
</script>
<style></style>
