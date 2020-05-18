<template>
  <div>
    <!-- header -->
    <div id="head-container">
      <b-navbar toggleable="lg" type="dark" variant="danger">
        <b-navbar-nav>
          <b-button v-b-toggle.sidebar  size="sm" class="my-2" variant="dark">Menu</b-button>
        </b-navbar-nav>
        <b-navbar-brand href="#" class="pl-4">NavBar</b-navbar-brand>

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav class="ml-auto">
            <b-nav-form>
              <b-form-input size="sm" class="mr-2" placeholder="keyword"></b-form-input>
              <b-button size="sm" class="my-2 my-sm-0" type="submit" variant="dark">Search</b-button>
            </b-nav-form>

            <b-nav-item-dropdown>
              <template v-slot:button-content>
                <em>User</em>
              </template>
              <b-dropdown-item href="#">Profile</b-dropdown-item>
              <b-dropdown-item href="#">Sign Out</b-dropdown-item>
            </b-nav-item-dropdown>
          </b-navbar-nav>

        </b-collapse>
      </b-navbar>
    </div>

    <!-- sidebar -->
    <b-container id="sidebar-container">
      <b-sidebar id="sidebar" aria-labelledby="sidebar-title" shadow>
        <template  v-slot:default="{ hide }">
          <div class="p-1">
            <h4 class="p-3">Category</h4>
            <nav class="mb-5">
              <b-nav vertical pills>
                <b-nav-item>Top</b-nav-item>
                <b-nav-item>Tech</b-nav-item>
                <b-nav-item active>Business</b-nav-item>
                <b-nav-item>World</b-nav-item>
                <b-nav-item>Science</b-nav-item>
                <b-nav-item>Social</b-nav-item>
              </b-nav>
            </nav>
            <nav class="mb-5">
        <b-nav vertical>
          <h4>Now reading</h4>
          <b-list-group>
            <b-list-group-item class="d-flex align-items-center">
              <b-avatar class="mr-3"></b-avatar>
              <span class="mr-auto">J. Circlehead</span>
              <b-badge pill variant="info"> Rank 5</b-badge>
            </b-list-group-item>
            <b-list-group-item class="d-flex align-items-center">
              <b-avatar variant="primary" text="BV" class="mr-3"></b-avatar>
              <span class="mr-auto">BootstrapVue</span>
              <b-badge pill variant="danger">Rank 12</b-badge>
            </b-list-group-item>
            <b-list-group-item class="d-flex align-items-center">
              <b-avatar variant="info" src="https://placekitten.com/300/300" class="mr-3"></b-avatar>
              <span class="mr-auto">Super Kitty</span>
              <b-badge pill variant="info">Rank 9</b-badge>
            </b-list-group-item>
          </b-list-group>
        </b-nav>
            </nav>
            <b-button variant="dark" block @click="hide">Close</b-button>
          </div>
        </template>
      </b-sidebar>
    </b-container>

    <!-- main -->
    <b-row id="main-container" class="p-1">
      <b-col v-for="item in items" :key="item" cols="6">
        <b-card id="news"
          title="Sakura Mankai"
          img-src="https://picsum.photos/600/300/?image=25"
          style="max-height: 50rem;">
          <b-card-text>
            [{{ item }}]
            This area is news headline.<br>
            The width and height can be easily changed by the user's operation.
          </b-card-text>
          <b-row>
            <b-col>
              <b-button href="#" col="6" block>Go somewhere</b-button>
              </b-col>
            <b-col>
              <b-button href="#" col="6" block style="min-height:100%">Later</b-button>
            </b-col>
          </b-row>
        </b-card>
      </b-col>
    </b-row>
  </div>
</template>

<script>
import Vue from 'vue'

export default{
  data: function () {
    var item = new Vue({
      data: { items: ['1', '2', '3', '4', '5', '6', '7', '8', '9'] }
    })
    return item
  }
}
</script>
