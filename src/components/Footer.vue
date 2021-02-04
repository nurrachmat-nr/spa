<template>
    <div class="footer">
        <p>Copyright &copy; 202 - Nur Rachmat</p>

        <h3>Thanks To</h3>
        <ul>
            <li>VUE JS</li>
            <li><a href="http://mdp.ac.id" target="_blank">Kampus MDP</a></li>
        </ul>
    </div>
</template>
<script>
export default {
    name : 'Footer'
}
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>