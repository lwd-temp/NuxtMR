<template>
  <div>
    <EnPcNav />
    <div class="mdui-container-fluid">
      <div class="mdui-panel">
        <div class="mdui-panel-item mdui-panel-item-open">
          <div class="mdui-panel-item-header">
            <div class="mdui-panel-item-title mdui-text-color-orange">New start off</div>
          </div>
          <div class="mdui-panel-item-body">
            <div style="font-size: 30px;"><a href="https://hyperos.fans" style="text-decoration: none;color: black;font-weight: bolder;">Xiaomi Hyper<span style="color: #155ffe;">OS</span></a></div>
            <div style="font-size: 20px;font-weight: lighter;"><a href="https://hyperos.fans" style="text-decoration: none;color: black;font-weight: bolder;">Start your <span style="color: #155ffe;">New Journey</span> with Mi & get Hyped</a></div>
          </div>
        </div>
        <div class="mdui-panel-item mdui-panel-item-open">
          <div class="mdui-panel-item-header">
            <div class="mdui-panel-item-title mdui-text-color-orange">Site Version {{ site.ver }}</div>
          </div>
          <div class="mdui-panel-item-body">
            <div><b>Updated at：</b>{{ site.sudate }}</div>
            <br />
            <div v-if="site.newDeviceEn != ''"><b>Newly Added Devices ：</b>{{ site.newDeviceEn }}</div>
            <br />
            <div v-show="site.log.length > 0"><b>Update Log ：</b></div>
            <div v-for="( log, index ) in site.log" v-show="site.log['0'].En != ''">
              <p>{{ index + 1 }} . {{ log.En }}</p>
            </div>
          </div>
        </div>
        <div class="mdui-panel-item mdui-panel-item-open">
          <div class="mdui-panel-item-header">
            <div class="mdui-panel-item-title mdui-text-color-orange">MIUI China Beta Updates</div>
          </div>
          <div class="mdui-panel-item-body">
            <b>Update time : </b>{{ weeks.update }} (GMT+8)<br /><br />
            <b>This week's Versions ：</b><span>{{ weeks.versions }}</span>
            <br />
            <br />
            <b>Weekly Changelog ：</b><span><a :href="('/en-US/weekly/week-' + site.latest + '-cn')" target="_blank">{{ weeks.titleEn }}</a></span>
            <br />
            <br />
            <p v-show="weeks.showdevices != 0"><b>This Weeks China Beta Supports Following {{ weeks.devices.length }} devices ：</b><span v-for="(data, index) in weeks.devices">
              <span v-show="index != weeks.devices.length - 1">{{ data.NameEn }};</span>
              <span v-show="index == weeks.devices.length - 1">{{ data.NameEn }}</span>
            </span></p>
          </div>
        </div>
        <div class="mdui-panel-item mdui-panel-item-open" v-show="site.stable.length > 0">
          <div class="mdui-panel-item-header">
            <div class="mdui-panel-item-title mdui-text-color-orange">Stable Rom Updates</div>
          </div>
          <div class="mdui-panel-item-body">
            <div><b>Latest Update：</b>{{ site.date }} (GMT+8)</div>
            <div><b>Weekly Period ：</b>Week {{ site.week }} of Year {{ site.year }}({{ site.period }})</div>
            <p v-if="$fetchState.pending">Fetching Data....</p>
            <p v-else-if="$fetchState.error">Fetching Failed.</p>
            <ol v-else>
              <li v-for="{ NameEn, rom, code } in site.stable">
                {{ NameEn }}({{ code }}) :{{ rom }}
              </li>
            </ol>
          </div>
        </div>
        <div class="mdui-panel-item mdui-panel-item-open">
          <div class="mdui-panel-item-header">
            <div class="mdui-panel-item-title mdui-text-color-orange">Site's Supporting devices</div>
          </div>
          <div class="mdui-panel-item-body">
            <b>
              <div>Our site currently supports following {{ devices.mi.length + devices.mise.length + devices.micc.length + devices.minote.length + devices.minote.length + devices.mimax.length + devices.mimix.length + devices.mipad.length + devices.micivi.length + devices.mia.length + devices.miothers.length + devices.rm.length + devices.rmnote.length + devices.rmk.length + devices.rmpad.length + devices.rmothers.length + devices.pococ.length + devices.pocof.length + devices.pocom.length + devices.pocox.length - 7 }} devices：</div>
            </b>
            <ul>
              <li>Mi Series ：<span v-for="(data, index) in devices.mi">
                  <a :href="('/en-US/devices/' + data.code)" v-show="index != devices.mi.length - 1"> {{ data.NameEn }} /</a>
                  <a :href="('/en-US/devices/' + data.code)" v-show="index == devices.mi.length - 1"> {{ data.NameEn }} </a>
                </span></li>
              <li>Mi SE Series ：<span v-for="(data, index) in devices.mise">
                  <a :href="('/en-US/devices/' + data.code)" v-show="index != devices.mise.length - 1"> {{ data.NameEn }} /</a>
                  <a :href="('/en-US/devices/' + data.code)" v-show="index == devices.mise.length - 1"> {{ data.NameEn }} </a>
                </span>
              </li>
              <li>Mi CC Series ：<span v-for="(data, index) in devices.micc">
                  <a :href="('/en-US/devices/' + data.code)" v-show="index != devices.micc.length - 1"> {{ data.NameEn }} /</a>
                  <a :href="('/en-US/devices/' + data.code)" v-show="index == devices.micc.length - 1"> {{ data.NameEn }} </a>
                </span>
              </li>
              <li>Mi Note Series ：<span v-for="(data, index) in devices.minote">
                  <a :href="('/en-US/devices/' + data.code)" v-show="index != devices.minote.length - 1"> {{ data.NameEn }} /</a>
                  <a :href="('/en-US/devices/' + data.code)" v-show="index == devices.minote.length - 1"> {{ data.NameEn }} </a>
                </span>
              </li>
              <li>Mi MAX Series ：<span v-for="(data, index) in devices.mimax">
                  <a :href="('/en-US/devices/' + data.code)" v-show="index != devices.mimax.length - 1"> {{ data.NameEn }} /</a>
                  <a :href="('/en-US/devices/' + data.code)" v-show="index == devices.mimax.length - 1"> {{ data.NameEn }} </a>
                </span>
              </li>
              <li>Mi MIX Series ：<span v-for="(data, index) in devices.mimix">
                  <a :href="('/en-US/devices/' + data.code)" v-show="index != devices.mimix.length - 1"> {{ data.NameEn }} /</a>
                  <a :href="('/en-US/devices/' + data.code)" v-show="index == devices.mimix.length - 1"> {{ data.NameEn }} </a>
                </span>
              </li>
              <li>Mi Pad Series ：<span v-for="(data, index) in devices.mipad">
                  <a :href="('/en-US/devices/' + data.code)" v-show="index != devices.mipad.length - 1"> {{ data.NameEn }} /</a>
                  <a :href="('/en-US/devices/' + data.code)" v-show="index == devices.mipad.length - 1"> {{ data.NameEn }} </a>
                </span>
              </li>
              <li>Xiaomi Civi Series ：<span v-for="(data, index) in devices.micivi">
                  <a :href="('/en-US/devices/' + data.code)" v-show="index != devices.mipad.length - 1"> {{ data.NameEn }} /</a>
                  <a :href="('/en-US/devices/' + data.code)" v-show="index == devices.mipad.length - 1"> {{ data.NameEn }} </a>
                </span>
              </li>
              <li>Mi A Series ：<span v-for="(data, index) in devices.mia">
                  <a :href="('/en-US/devices/' + data.code)" v-show="index != devices.mia.length - 1"> {{ data.NameEn }} /</a>
                  <a :href="('/en-US/devices/' + data.code)" v-show="index == devices.mia.length - 1"> {{ data.NameEn }} </a>
                </span>
              </li>
              <li>Other Mi Phones ：<span v-for="(data, index) in devices.miothers">
                  <a :href="('/en-US/devices/' + data.code)" v-show="index != devices.mia.length - 1"> {{ data.NameEn }} /</a>
                  <a :href="('/en-US/devices/' + data.code)" v-show="index == devices.mia.length - 1"> {{ data.NameEn }} </a>
                </span>
              </li>
              <li>Redmi Series ：<span v-for="(data, index) in devices.rm">
                  <a :href="('/en-US/devices/' + data.code)" v-show="index != devices.mia.length - 1"> {{ data.NameEn }} /</a>
                  <a :href="('/en-US/devices/' + data.code)" v-show="index == devices.mia.length - 1"> {{ data.NameEn }} </a>
                </span>
              </li>
              <li>Redmi Note Series ：<span v-for="(data, index) in devices.rmnote">
                  <a :href="('/en-US/devices/' + data.code)" v-show="index != devices.rmnote.length - 1"> {{ data.NameEn }} /</a>
                  <a :href="('/en-US/devices/' + data.code)" v-show="index == devices.rmnote.length - 1"> {{ data.NameEn }} </a>
                </span>
              </li>
              <li>Redmi K Series ：<span v-for="(data, index) in devices.rmk">
                  <a :href="('/en-US/devices/' + data.code)" v-show="index != devices.rmk.length - 1"> {{ data.NameEn }} /</a>
                  <a :href="('/en-US/devices/' + data.code)" v-show="index == devices.rmk.length - 1"> {{ data.NameEn }} </a>
                </span>
              </li>
              <li>Redmi Pad ：<span v-for="(data, index) in devices.rmpad">
                  <a :href="('/en-US/devices/' + data.code)" v-show="index != devices.rmpad.length - 1"> {{ data.NameEn }} /</a>
                  <a :href="('/en-US/devices/' + data.code)" v-show="index == devices.rmpad.length - 1"> {{ data.NameEn }} </a>
                </span>
              </li>
              <li>Other Redmi Phones ：<span v-for="(data, index) in devices.rmothers">
                  <a :href="('/en-US/devices/' + data.code)" v-show="index != devices.rmothers.length - 1"> {{ data.NameEn }} /</a>
                  <a :href="('/en-US/devices/' + data.code)" v-show="index == devices.rmothers.length - 1"> {{ data.NameEn }} </a>
                </span>
              </li>
              <li>POCO C Series ：<span v-for="(data, index) in devices.pococ">
                  <a :href="('/en-US/devices/' + data.code)" v-show="index != devices.pococ.length - 1"> {{ data.NameEn }} /</a>
                  <a :href="('/en-US/devices/' + data.code)" v-show="index == devices.pococ.length - 1"> {{ data.NameEn }} </a>
                </span>
              </li>
              <li>POCO F Series ：<span v-for="(data, index) in devices.pocof">
                  <a :href="('/en-US/devices/' + data.code)" v-show="index != devices.pocof.length - 1"> {{ data.NameEn }} /</a>
                  <a :href="('/en-US/devices/' + data.code)" v-show="index == devices.pocof.length - 1"> {{ data.NameEn }} </a>
                </span>
              </li>
              <li>POCO M Series ：<span v-for="(data, index) in devices.pocom">
                  <a :href="('/en-US/devices/' + data.code)" v-show="index != devices.pocom.length - 1"> {{ data.NameEn }} /</a>
                  <a :href="('/en-US/devices/' + data.code)" v-show="index == devices.pocom.length - 1"> {{ data.NameEn }} </a>
                </span>
              </li>
              <li>POCO X Series ：<span v-for="(data, index) in devices.pocox">
                  <a :href="('/en-US/devices/' + data.code)" v-show="index != devices.pocox.length - 1"> {{ data.NameEn }} /</a>
                  <a :href="('/en-US/devices/' + data.code)" v-show="index == devices.pocox.length - 1"> {{ data.NameEn }} </a>
                </span>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
    <EnPcDisclaimer />
    <EnPcFooter />
  </div>
</template>

<script>
let index = "https://data.miuier.com/data/index.json";
let devices = "https://data.miuier.com/data/devices.json";
let week = ''
export default {
  data() {
    return {
      site: [],
      devices: [],
      weeks: [],
      beta: [],
      title: "MIUI Official ROMS - A MiFan\'s MIUI Roms Collection Site"
    }
  },
  async fetch() {
    this.site = await fetch(index).then(res => res.json())
    this.devices = await fetch(devices).then(res => res.json())
    this.week = "https://data.miuier.com/data/weekly/week-" + this.site.latest + "-cn.json"
    this.weeks = await fetch(this.week).then(res => res.json())
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
