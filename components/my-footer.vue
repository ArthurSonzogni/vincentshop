<template>
  <footer>
    <div class="row">
      <a href="https://google.com">contact</a>
      <a href="https://google.com">Services</a>
    </div>
    <div class="row">
      <a href="https://google.com">facebook</a>
      <a href="https://google.com">instagram</a>
      <a href="https://google.com">twitter</a>
      <a href="https://google.com">linkedin</a>
      <a href="https://google.com">pinterest</a>
    </div>
    <p id="copyright">Copyright 2023 Haute Joaillerie. Tous droits réservés.</p>
  </footer>
</template>

<style scoped>
footer {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: #888;
  margin: 0;
  padding-top: 30px;
  max-width: 700px;
  margin-left: auto;
  margin-right: auto;
}

.row {
  display: flex;
}

a {
  text-transform: uppercase;
  text-decoration: none;
  font-size: 15px;
  transition: color 0.4s;
  margin: 10px;
}

a:hover {
  color: black;
}

#copyright {
  border-top: 1px solid rgb(0 0 0 / 10%);
  padding: 20px;
  margin-top: 20px;
  font-size: 10px;
}
</style>
