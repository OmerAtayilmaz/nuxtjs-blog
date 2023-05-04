<template>
  <img src="icon-green.svg" :width="50" alt=""/>
  THIS IS MAIN PAGE
  <Counter/>
  x: {{ x }} - y {{ y }}

  <ul>
    <li v-for="t in users" :key="t.id">{{t.name}}</li>
  </ul><ul>
    <li v-for="t in users2" :key="t.id">{{t.name}}</li>
  </ul>
  <ul>
    <li v-for="t in users3" :key="t.id">{{t.name}}</li>
  </ul>
  <div>
    {{ user }}
  </div>
  <Calculator/>
</template>
<script setup>

  const { x, y } = useMouse();

  const users = ref([]);

  onMounted(() => {
    fetch("https://jsonplaceholder.typicode.com/users")
        .then(res => res.json())
        .then(data => users.value = data );
  })

  //sunucudan gelen
  const { data: users2 } = await useAsyncData('users2', () => $fetch("https://jsonplaceholder.typicode.com/users"));

  //2. kullanım -- sunucudan gelen
  const { data:users3 } = await useFetch("https://jsonplaceholder.typicode.com/users");

  //3. kullanımı sadece istediğimiz kolonları almak
  const { data:user } = await useFetch("https://jsonplaceholder.typicode.com/users/1",{
    pick: ['name','email']
  });

</script>
