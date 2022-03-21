<template>
<div v-if="job">

<h1>{{job.title}}</h1>
<p>The Job id is {{id}}</p>
<p>{{job.detail}}</p>
</div>
<div v-if ="!job" class="mt-10">
<div class="border border-blue-300 shadow rounded-md p-4 max-w-sm w-full mx-auto">
  <div class="animate-pulse flex space-x-4">
    <div class="rounded-full bg-slate-700 h-10 w-10"></div>
    <div class="flex-1 space-y-6 py-1">
      <div class="h-2 bg-slate-700 rounded"></div>
      <div class="space-y-3">
        <div class="grid grid-cols-3 gap-4">
          <div class="h-2 bg-slate-700 rounded col-span-2"></div>
          <div class="h-2 bg-slate-700 rounded col-span-1"></div>
        </div>
        <div class="h-2 bg-slate-700 rounded"></div>
      </div>
    </div>
  </div>
</div>
</div>
</template>


<script>


export default ({
    props:['id'],
    data() {
        return {
            job :null
        }
    },
    mounted () {
        fetch ('http://localhost:3000/jobs/'+ this.id)
        .then ((res) => res.json())
        .then ((data) => this.job=data)
        .catch ((err) => console.log(err))
    }
})
</script>

<style >

</style>
