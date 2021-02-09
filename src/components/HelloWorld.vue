<template>
  <div class="main">
    <div>
      <label for="FulltName">FullName</label>
      <input type="text" id="fName" class="styl" />
    </div>
    <div>
      <label for="FirstName">Email</label>
      <input type="email" id="email" class="styl" />
    </div>
    <div>
      <label for="Password">Password</label>
      <input type="password" id="password" class="styl" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'Helloworld',
};
</script>

<style>
* {
  letter-spacing: 3px;
  font-family: sans-serif;
}
.main {
  width: 700px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  vertical-align: middle;
}
.main div {
  position: relative;
  margin: 40px 0;
}
label {
  position: absolute;
  top: 0;
  margin: 10px;
  padding: 0 10px;
  background-color: #f05855;
  transition: top 0.2s ease-in-out, font-size 0.2s ease-in-out;
}
.active {
  top: -25px;
  font-size: 20px;
  font-weight: 900;
  letter-spacing: 6px;
  text-transform: uppercase;
}
input[type='text'],
input[type='password'],
input[type='email'] {
  width: 100%;
  padding: 20px;
  border: 2px solid #fff;
  font-size: 20px;
  font-weight: 800;
  background-color: #f05855;
  color: #fff;
}
input[type='text']:focus,
input[type='password']:focus,
input[type='email']:focus {
  outline: none;
}
</style>
