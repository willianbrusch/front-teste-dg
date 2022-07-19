<template>
  <div class="person-card">
    <p>{{ personInfo.name }}</p>
    <p>{{ personInfo.age }}</p>
    <div class="extra-action-card">
      <a>
        <Icon icon="ic:baseline-edit" color="#227bff" width="30" />
      </a>
      <a>
        <Icon icon="ic:baseline-close" color="red" width="35" />
      </a>
    </div>
  </div>
</template>

<script>
import { Icon } from "@iconify/vue";

export default {
  components: {
    Icon,
  },
  props: {
    personInfo: {},
  },
};
</script>

<style>
.person-card {
  width: 70vw;
  height: 50px;
  padding: 25px;
  margin: 5px;

  border-bottom: 2px solid var(--primaryBlue);
  background-color: #f1f6ff;

  display: flex;
  align-items: center;
  justify-content: space-between;
}

.extra-action-card {
  width: 90px;
  height: 45px;

  display: flex;
  justify-content: space-between;
  align-items: flex-end;
}

p {
  width: 150px;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

@media (max-width: 520px) {
  .person-card {
    width: 95vw;
  }

  .extra-action-card {
  width: 40px;
  height: 45px;

  display: flex;
  justify-content: space-between;
  align-items: flex-end;
}

p {

  width: 120px;
  text-align: center;
}
}
</style>
