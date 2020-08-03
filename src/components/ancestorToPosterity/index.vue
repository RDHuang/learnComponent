<template>
  <div>
    <Ancestor>
      <Middleman>
        <Posterity></Posterity>
      </Middleman>
    </Ancestor>
  </div>
</template>

<script>
import Ancestor from "./ancestor";
import Middleman from "./middleman";
import Posterity from "./posterity";
export default {
  components: {
    Ancestor,
    Middleman,
    Posterity,
  },
};
</script>
