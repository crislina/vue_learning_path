<template>
  <div>
    <b-nav>
      <b-nav-item disabled>Quiz Questions</b-nav-item>
      <b-nav-item disabled>Counter: {{ numOfCorrectness }}/{{ numOfTotal }}</b-nav-item>
    </b-nav>
  </div>
</template>

<script>
export default {
    props:[
        'numOfCorrectness','numOfTotal'
    ]
}
</script>