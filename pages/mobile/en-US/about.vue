<template>
  <div>
    <EnMobileNav />
    <div class="mdui-center PNF">This Page is under development.</div>
    <EnMobileDisclaimer />
<EnMobileFooter />
  </div>
</template>
<script>
let baseurl = "https://data.miuier.com/data/";
let index = baseurl + "index.json";
let devices = baseurl + "devices.json"
export default {
  data() {
    return {
      site: [],
      devices: [],
      title: "About US - MIUI Official ROMs"
    }
  },
  async fetch() {
    this.site = await fetch(index).then(res => res.json())
    this.devices = await fetch(devices).then(res => res.json())
  },
  fetchOnServer: true,
  head() {
    return {
      title: this.title,
      htmlAttrs: {
        lang: "en-US",
      }
    }
  }
}
</script>
