<template>
  <div class="container--medtime">
    <div class="graph">
      <div class="graph__container">
        <CpText tag="p" type="ext">{{ time }} Minutes</CpText>
        <CpText tag="p" type="ext">{{ time }} Minutes</CpText>
        <CpText tag="p" type="title">{{ time }} Minutes</CpText>
        <CpText tag="p" type="ext">{{ time }} Minutes</CpText>
        <CpText tag="p" type="ext">{{ time }} Minutes</CpText>
      </div>
    </div>
    <div class="content">
      <CpText tag="h3" type="title">{{ title }}</CpText>
      <div class="container--buttons">
        <ButtonText @click.native="moyen()" :type="med" content="Moyenne"/>
        <ButtonText @click.native="long()" :type="max" content="Morceau le + long"/>
        <ButtonText @click.native="minimum()" :type="min" content="Morceau le + court"/>
      </div>
      <CpText v-if="(min == 'active' || max == 'active')" tag="p" type="value">Titre : {{ titre }}</CpText>
    </div>
  </div>
</template>

<script>
import CpText from "@/components/01_atoms/CpText/CpText.vue";
import ButtonText from "@/components/02_molecules/ButtonText/ButtonText.vue";

export default {
  name: "MedTime",
  components: {
    CpText,
    ButtonText
  },
  props: {
    data: {
      type: Object
    }
  },
  data() {
    return {
      title: "Durée moyenne d’un morceau",
      time: this.data.time_med,
      med: "active",
      min: "inactive",
      max: "inactive",
      titre: "test"
    };
  },
  methods: {
    print: function(a) {
      console.log(a);
      console.log(JSON.stringify(a));
      return a;
    },
    long: function() {
      this.med = "inactive";
      this.min = "inactive";
      this.max = "active";
      this.time = this.data.time_max;
      this.titre = this.data.time_max_name;
    },
    moyen: function() {
      this.max = "inactive";
      this.min = "inactive";
      this.med = "active";
      this.time = this.data.time_med;
    },
    minimum: function() {
      this.med = "inactive";
      this.max = "inactive";
      this.min = "active";
      this.time = this.data.time_min;
      this.titre = this.data.time_min_name;
    }
  }
};
</script>

<style lang="scss">
@import "./MedTime.scss";
</style>
