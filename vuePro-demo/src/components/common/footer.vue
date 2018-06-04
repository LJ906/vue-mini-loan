<template>
  <div class="footer">
    <ul>
      <!-- 当前的index === 传过来的idx 则 添加类名on [{item.cls:intem.cls}, {}] -->
      <li v-for='(item,index) of items' :class='[ item.cls , {on:index === idx} ]' 
      @click="$router.push(item.push)">
        {{item.name}}
      </li>
    </ul>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        items: [{
          cls: "loan",
          name: "借款",
          push: "/loan"
        },
          {
            cls: "credit",
            name: "信用",
            push: "/credit"
          },
          {
            cls: "user",
            name: "个人中心",
            push: "/user"
          }
        ]
      }
    },
    props: ['idx']
  }
</script>
