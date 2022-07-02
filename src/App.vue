<template>

 <div class="wrapper">
    <div class="task-input">
      <ion-icon name="create-outline"></ion-icon>
      <input type="text" placeholder="Add a New Task + Enter">
    </div>
    <div class="controls">
      <div class="filters">
        <span class="active" id="all">All</span>
        <span id="pending">Pending</span>
        <span id="completed">Completed</span>
      </div>
      <button class="clear-btn">Clear All</button>
    </div>
    <ul class="task-box"></ul>
  </div>

</template>


<script>
export default {

}
</script>