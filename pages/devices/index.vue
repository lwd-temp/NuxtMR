<template>
  <div>
    <CnMobileNav />
    <br />
    <div class="mdui-container-fluid" id="Xiaomi">
      <div class="mdui-panel mdui-panel-gapless mdui-shadow-0" mdui-panel="{accordion: true}">
        <div class="mdui-panel-item mdui-panel-item-open">
          <div class="mdui-panel-item-header">
            <div class="mdui-panel-item-title">小米手机</div>
            <i class="mdui-panel-item-arrow mdui-icon material-icons">keyboard_arrow_down</i>
          </div>
          <div class="mdui-panel-item-body">
            <div class="series">小米 系列：</div>
            <div v-for="{ code, NameCn } in devices.mi" class="mdui-chip">
              <a :href="('/devices/' + code)"><span class="mdui-chip-title"> {{ NameCn }}({{ code }}) </span></a>
            </div>
            <div class="series">小米SE 系列：</div>
            <div v-for="{ code, NameCn } in devices.mise" class="mdui-chip">
              <a :href="('/devices/' + code)"><span class="mdui-chip-title"> {{ NameCn }}({{ code }}) </span></a>
            </div>
            <div class="series">小米CC 系列：</div>
            <div v-for="{ code, NameCn } in devices.micc" class="mdui-chip">
              <a :href="('/devices/' + code)"><span class="mdui-chip-title"> {{ NameCn }}({{ code }}) </span></a>
            </div>
            <div class="series">小米Note 系列：</div>
            <div v-for="{ code, NameCn } in devices.minote" class="mdui-chip">
              <a :href="('/devices/' + code)"><span class="mdui-chip-title"> {{ NameCn }}({{ code }}) </span></a>
            </div>
            <div class="series">小米MAX 系列：</div>
            <div v-for="{ code, NameCn } in devices.mimax" class="mdui-chip">
              <a :href="('/devices/' + code)"><span class="mdui-chip-title"> {{ NameCn }}({{ code }}) </span></a>
            </div>
            <div class="series">小米MIX 系列：</div>
            <div v-for="{ code, NameCn } in devices.mimix" class="mdui-chip">
              <a :href="('/devices/' + code)"><span class="mdui-chip-title"> {{ NameCn }}({{ code }}) </span></a>
            </div>
            <div class="series">小米Civi 系列：</div>
            <div v-for="{ code, NameCn } in devices.micivi" class="mdui-chip">
              <a :href="('/devices/' + code)"><span class="mdui-chip-title"> {{ NameCn }}({{ code }}) </span></a>
            </div>
            <div class="series">小米A 系列：</div>
            <div v-for="{ code, NameCn } in devices.mia" class="mdui-chip">
              <a :href="('/devices/' + code)"><span class="mdui-chip-title"> {{ NameCn }}({{ code }}) </span></a>
            </div>
            <div class="series">小米平板 系列：</div>
            <div v-for="{ code, NameCn } in devices.mipad" class="mdui-chip">
              <a :href="('/devices/' + code)"><span class="mdui-chip-title"> {{ NameCn }}({{ code }}) </span></a>
            </div>
            <div class="series">其他小米手机：</div>
            <div v-for="{ code, NameCn } in devices.miothers" class="mdui-chip">
              <a :href="('/devices/' + code)"><span class="mdui-chip-title"> {{ NameCn }}({{ code }}) </span></a>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="mdui-container-fluid" id="Redmi">
      <div class="mdui-panel mdui-panel-gapless mdui-shadow-0" mdui-panel="{accordion: true}">
        <div class="mdui-panel-item mdui-panel-item-open">
          <div class="mdui-panel-item-header">
            <div class="mdui-panel-item-title">Redmi 手机</div>
            <i class="mdui-panel-item-arrow mdui-icon material-icons">keyboard_arrow_down</i>
          </div>
          <div class="mdui-panel-item-body">
            <div class="series">Redmi 系列：</div>
            <div v-for="{ code, NameCn } in devices.rm" class="mdui-chip">
              <a :href="('/devices/' + code)"><span class="mdui-chip-title"> {{ NameCn }}({{ code }}) </span></a>
            </div>
            <div class="series">Redmi Note 系列：</div>
            <div v-for="{ code, NameCn } in devices.rmnote" class="mdui-chip">
              <a :href="('/devices/' + code)"><span class="mdui-chip-title"> {{ NameCn }}({{ code }}) </span></a>
            </div>
            <div class="series">Redmi K 系列：</div>
            <div v-for="{ code, NameCn } in devices.rmk" class="mdui-chip">
              <a :href="('/devices/' + code)"><span class="mdui-chip-title"> {{ NameCn }}({{ code }}) </span></a>
            </div>
            <div class="series">Redmi Pad 系列：</div>
            <div v-for="{ code, NameCn } in devices.rmpad" class="mdui-chip">
              <a :href="('/devices/' + code)"><span class="mdui-chip-title"> {{ NameCn }}({{ code }}) </span></a>
            </div>
            <div class="series">其他 Redmi 手机：</div>
            <div v-for="{ code, NameCn } in devices.rmothers" class="mdui-chip">
              <a :href="('/devices/' + code)"><span class="mdui-chip-title"> {{ NameCn }}({{ code }}) </span></a>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="mdui-container-fluid" id="POCO">
      <div class="mdui-panel mdui-panel-gapless mdui-shadow-0" mdui-panel="{accordion: true}">
        <div class="mdui-panel-item mdui-panel-item-open">
          <div class="mdui-panel-item-header">
            <div class="mdui-panel-item-title">POCO 手机</div>
            <i class="mdui-panel-item-arrow mdui-icon material-icons">keyboard_arrow_down</i>
          </div>
          <div class="mdui-panel-item-body">
            <div class="series">POCO C 系列：</div>
            <div v-for="{ code, NameCn } in devices.pococ" class="mdui-chip">
              <a :href="('/devices/' + code)"><span class="mdui-chip-title"> {{ NameCn }}({{ code }}) </span></a>
            </div>
            <div class="series">POCO F 系列：</div>
            <div v-for="{ code, NameCn } in devices.pocof" class="mdui-chip">
              <a :href="('/devices/' + code)"><span class="mdui-chip-title"> {{ NameCn }}({{ code }}) </span></a>
            </div>
            <div class="series">POCO M 系列：</div>
            <div v-for="{ code, NameCn } in devices.pocom" class="mdui-chip">
              <a :href="('/devices/' + code)"><span class="mdui-chip-title"> {{ NameCn }}({{ code }}) </span></a>
            </div>
            <div class="series">POCO X 系列：</div>
            <div v-for="{ code, NameCn } in devices.pocox" class="mdui-chip">
              <a :href="('/devices/' + code)"><span class="mdui-chip-title"> {{ NameCn }}({{ code }}) </span></a>
            </div>
          </div>
        </div>
      </div>
    </div>
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
      title: "机型列表 - MIUI官方ROM仓库"
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
