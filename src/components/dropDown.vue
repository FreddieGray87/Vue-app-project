<template>
    <div class="btn-group">
        <li @click="toggleMenu()" class="dropdown-toggle" v-if="selectedOption.name !== undefined">
          {{ selectedOption.name }}
          <span class="caret"></span>
        </li>

        <li @click="toggleMenu()" class="dropdown-toggle" v-if="selectedOption.name === undefined">
          {{placeholderText}}
          <span class="caret"></span>
        </li>

        <ul class="dropdown-menu" v-if="showMenu">
            <li v-bind="option in options">
                <a href="javascript:void(0)" @click="updateOption(option)">
                    {{ option.name }}
                </a>
            </li>
        </ul>
        <dropdown :options="arrayOfObjects" 
          :selected="object" 
          v-on:updateOption="methodToRunOnSelect" 
          :placeholder="'Select an Item'">
</dropdown>
    </div>
    
</template>


<script>
    export default {
  name: 'app',
  data () {
    return {
      arrayOfObjects: [
        {id: 1, name: 'Tip Cal'},
        {id: 2, name: 'Second Option'},
        {id: 3, name: 'Third Option'},
      ],
      selectedObject: {},
    }
  },
  components: {
    'dropdown': dropdown,
  },
  methods: {
    updateSelected(payload) {
      this.selectedObject = payload;
    }
  }
}
</script>
<template>
    <nav class="navbar navbar-expand-lg navbar-light bg-light mb-2">
        <router-link class="navbar-brand" to='/'>FSWD</router-link>
        <ul class="navbar-nav mr-auto">
            <li class="nav-item" v-show='!isLoggedIn'>
                <router-link class="nav-link" to='/login'>Login</router-link>
            </li>
            <li class="nav-item" v-show='!isLoggedIn'>
                <router-link class="nav-link" to='/register'>Register</router-link>
            </li>
            <li class="nav-item" v-show="isLoggedIn">
                <router-link class="nav-link" to='/users'>Users</router-link>
            </li>
        </ul>
        <ul class='navbar-nav' v-show='isLoggedIn'>
            <li class='nav-item dropdown'>
                <a class='nav-link dropdown-toggle' href='#' id="navbarDropdownMenuLink" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                    {{ username }}
                </a>
                <div class="dropdown-menu dropdown-menu-right" aria-labelledby="navbarDropdownMenuLink">
                    <a class="dropdown-item" @click="logout">Logout</a>
                </div>                
            </li>
        </ul>
    </nav>
</template>

<script>

<style>
.btn-group {
  min-width: 160px;
  height: 40px;
  position: relative;
  margin: 10px 1px;
  display: inline-block;
  vertical-align: middle;
}
.btn-group a:hover {
  text-decoration: none;
}
.dropdown-toggle {
  color: #636b6f;
  min-width: 160px;
  padding: 10px;
  text-transform: none;
  font-weight: 300;
  margin-bottom: 7px;
  border: 0;
  background-image: linear-gradient(#009688, #009688), linear-gradient(#D2D2D2, #D2D2D2);
  background-size: 0 2px, 100% 1px;
  background-repeat: no-repeat;
  background-position: center bottom, center calc(100% - 1px);
  background-color: transparent;
  transition: background 0s ease-out;
  float: none;
  box-shadow: none;
  border-radius: 0;
}
.dropdown-toggle:hover {
  background: #e1e1e1;
  cursor: pointer;
}
.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  z-index: 1000;
  float: left;
  min-width: 160px;
  padding: 5px 0;
  margin: 2px 0 0;
  list-style: none;
  font-size: 14px;
  text-align: left;
  background-color: #fff;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  background-clip: padding-box;
}
.dropdown-menu > li > a {
  padding: 10px 30px;
  display: block;
  clear: both;
  font-weight: normal;
  line-height: 1.6;
  color: #333333;
  white-space: nowrap;
  text-decoration: none;
}
.dropdown-menu > li > a:hover {
  background: #efefef;
  color: #409FCB;
}
.dropdown-menu > li {
  overflow: hidden;
  width: 100%;
  position: relative;
  margin: 0;
}
.caret {
  display: relative;
  width: 0;
  position: relative;
  top: 10px;
  height: 0;
  margin-left: 2px;
  vertical-align: middle;
  border-top: 4px dashed;
  border-top: 4px solid \9;
  border-right: 4px solid transparent;
  border-left: 4px solid transparent;
  float: right;
}
li {
    list-style: none;
}
</style>
