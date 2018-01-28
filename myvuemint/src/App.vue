<template>
  <div id="app">
    <mt-header title="标题过长会隐藏后面的内容啊哈哈哈哈">
    <mt-button icon="back" slot="left">返回</mt-button>
  <mt-button icon="more" slot="right"></mt-button>
</mt-header>

<mt-index-list>
  <mt-index-section v-for="item in userdata" :index="item.index" :key="item.id">
    <mt-cell v-for="user in item.users" @click.native="telalert(user.tel)" :title="user.name" :key="user.id"></mt-cell> 
  </mt-index-section>
</mt-index-list>

  </div>
</template>

<script>
import { MessageBox } from 'mint-ui';
var userdata=[
{"index":"A","users":[
{"name":"a1","tel":"13011111111"},
{"name":"a2","tel":"13011111112"},
{"name":"a3","tel":"13011111113"}
]},
{"index":"B","users":[
{"name":"b1","tel":"13011111114"},
{"name":"b2","tel":"13011111115"},
{"name":"b3","tel":"13011111116"}
]},
{"index":"C","users":[
{"name":"c1","tel":"13011111117"},
{"name":"c2","tel":"13011111118"},
{"name":"c3","tel":"13011111119"}
]},
{"index":"D","users":[
{"name":"d1","tel":"13011111121"},
{"name":"d2","tel":"13011111122"},
{"name":"d3","tel":"13011111123"}
]},
{"index":"E","users":[
{"name":"e1","tel":"13011111131"},
{"name":"e2","tel":"13011111132"},
{"name":"e3","tel":"13011111133"}
]}
];
export default {
  name: 'app',
  data () {
    return {
      userdata:userdata
    }
  },
  methods:{
  telalert:function(tel){
				MessageBox({
			  title: '呼叫',
			  message: tel,
			  showCancelButton: true
			}).then(function(){
				alert(1212)
			});
  }
  }
}
</script>

<style>
*{margin:0;padding:0;}
</style>
