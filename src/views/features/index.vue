<template>
  <div class="features">
    <BaseCard title="I18n">
      <van-radio-group v-model="$i18n.locale">
        <van-radio name="zh" style="margin-bottom:10px">简体中文</van-radio>
        <van-radio name="en">English</van-radio>
      </van-radio-group>
      <p>{{ $t('hello') }}</p>
    </BaseCard>

    <BaseCard title="内置过滤器">
      <h3>日期过滤器 - date</h3>
      <BaseCardItem label="原值">2018-12-1</BaseCardItem>
      <BaseCardItem label="过滤值">{{'2018-12-1'|date('YYYY年MM月DD日')}}</BaseCardItem>
      <h3>金额过滤器 - currency</h3>
      <BaseCardItem label="原值">430000（分）</BaseCardItem>
      <BaseCardItem label="过滤值">{{'430000'|currency}}</BaseCardItem>
    </BaseCard>

    <BaseCard title="UI组件">
      <h3>vant-ui</h3>
      <VantUi></VantUi>
    </BaseCard>

    <BaseCard title="用户反馈">
      <h3>波纹效果(点击)</h3>
      <div>
        <div v-waves="['rounded-btn', 'waves-circle']">←</div>
        <div v-waves="['dark-btn', 'waves-light']">●</div>
      </div>
      <h3>状态改变</h3>
      <div>成功失败图标</div>
      <UeStatusChange></UeStatusChange>
    </BaseCard>

    <BaseCard title="用户体验">
      <h3>骨架屏</h3>
      <SkeletonScreen></SkeletonScreen>
    </BaseCard>

    <BaseCard title="开发体验">
      <h3>魔法数字说拜拜</h3>
      <NoMagicNumber></NoMagicNumber>
    </BaseCard>

    <BaseCard title="权限校验体系">
      <Permission></Permission>
    </BaseCard>

    <BaseCard title="Axios封装以及接口Mock">
      <AxiosWp></AxiosWp>
    </BaseCard>
  </div>
</template>

<script>
import Vue from 'vue'
import { RadioGroup, Radio } from 'vant'
import BaseCard from '@/components/base-card'
import BaseCardItem from '@/components/base-card/base-card-item'
import UeStatusChange from './examples/ue-status-change'
import SkeletonScreen from './examples/skeleton-screen'
import Permission from './examples/permission/index'
import AxiosWp from './examples/axios-wp'
import VantUi from './examples/vant-ui'
import NoMagicNumber from './examples/no-magic-number'

Vue.use(RadioGroup)
Vue.use(Radio)

export default {
  name: 'Features',
  components: {
    BaseCard,
    BaseCardItem,
    UeStatusChange,
    SkeletonScreen,
    Permission,
    AxiosWp,
    VantUi,
    NoMagicNumber
  },
  data() {
    return {
      data1: ''
    }
  }
}
</script>

<style lang="scss" scoped>
.features {
  padding: 20px;
  width: 100%;
  box-sizing: border-box;
  background-color: #334a55;
  line-height: 1.5em;
  /deep/ {
    .base-card {
      box-shadow: 3px 4px 12px 1px rgba(56, 132, 192, 0.53);
    }
    .code {
      background-color: #eee;
      padding: 2px 4px;
      font-size: 14px;
      font-weight: bold;
    }
    pre {
      padding: 16px;
      overflow: auto;
      font-size: 85%;
      line-height: 1.45;
      background-color: #f6f8fa;
      border-radius: 3px;
    }
    pre,
    code {
      font-family: 'Microsoft Yahei';
    }
  }
}

.rounded-btn {
  background-color: blanchedalmond;
  color: #666;
  font-size: 12px;
  padding: 4px;
}
.dark-btn {
  padding: 10px;
  background-color: #334a55;
  color: #fff;
  border-radius: 4px;
  margin-left: 10px;
  vertical-align: top;
}
</style>

<i18n>
{
  "en": {
    "hello": "hello world!"
  },
  "zh": {
    "hello": "你好世界！"
  }
}
</i18n>
