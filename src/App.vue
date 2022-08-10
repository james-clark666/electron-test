<template>
  <div>
    <div class="WinTitle">
      <div class="Logo">
        <img src="./assets/logo.png" style="height: 26px" />
        <span style="color:yellow">每日单词</span>
      </div>
      <div class="WinTitleControl"></div>
      <div class="Control elasticBox">
        <div class="Button" @click="BtnMinimize">
          <img src="./assets/icon/minimize.svg" style="height: 12px" />
        </div>
        <div class="Button" @click="BtnMaximize">
          <img src="./assets/icon/maximize.svg" style="height: 12px" />
        </div>
        <div class="Button" @click="BtnWinClose"><img src="./assets/icon/close.svg" style="height: 12px" /></div>
      </div>
    </div>
    <div class="WinContent"><router-view></router-view></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // ipcRenderer:window.electron.ipcRenderer
    }
  },

  components: {},

  mounted() {},

  destroyed() {},

  methods: {
    BtnMinimize() {
      console.log(1);
      // this.ipcRenderer.send('min')
    },
    BtnMaximize() {
      console.log(2);
      // this.ipcRenderer.send('max')
    },
    BtnWinClose() {
      console.log(3);
      // this.ipcRenderer.send('close')
    }
  }
}
</script>

<style>
@import './assets/css/ccs-mde-global.css';
#app {
  font-family: 'Consolas', '微软雅黑', monospace, 'Microsoft YaHei', 'hw-iconfont';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: var(--ccs-mde-primary-font-color);
}
.WinTitle {
  position: relative;
  width: 100vw;
  height: var(--ccs-mde-winTitle-height);
  background: var(--ccs-mde-winTitle-color);
  box-shadow: 0px 2px 4px #00000030; 
  z-index: 4000;
}

.WinContent {
  width: calc(100vw-10px);
}

.Logo {
  height: 100%;
  display: flex;
  align-items: center;
  padding-left: 16px;
}

.WinTitleControl {
  position: absolute;
  top: 0;
  height: 100%;
  /* 设置标题栏可拖动 */
  -webkit-app-region: drag;
}

.Control {
  position: absolute;
  top: 0;
  right: 0;
  height: 100%;
}

.Button {
  width: 32px;
  height: 32px;
  border-radius: 8px;
  background: var(--ccs-mde-winTitle-color);
  box-shadow: 3px 3px 6px #1a1a1b, -3px -3px 6px #303031;
  margin-right: 14px;
  display: flex;
  align-items: center;
  justify-content: center;
  user-select: none;
  transition: background 0.3s;
}

.Button:hover {
  background: #282828;
}

.Button:active {
  border-radius: 8px;
  background: #252526;
  box-shadow: inset 3px 3px 6px #1a1a1b, inset -3px -3px 6px #303031;
}



</style>
