<template>
  <div>
    <CnMobileNav />
    <div class="mdui-center PNF">该页面正在构建中</div>
    <br />
    <CnMobileDisclaimer />
    <CnMobileFooter />
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
      title: "关于本站 - MIUI官方ROM仓库"
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
        lang: "zh-CN",
      }
    }
  }
}
</script>
