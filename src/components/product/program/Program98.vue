<template>
  <div class="contents bottom-sticky" ref="contents">
    <!-- slide -->
    <div class="slider-prd">
      <img src="../../../assets/images/program/class98-slide1.jpg" alt="T Factory X FLO 덕후콘">
    </div>
    <!-- //slide -->
    <!-- details -->
    <div class="details sticky">
      <div class="details-header">
        <kakao-share
          title="2월의 덕콘"
          description="찐덕들만 초청하여 진행하는 덕콘."
        ></kakao-share>

        <em class="flag-solid7">CONCERT</em>
        <h2 class="details-tit">
          2월의 덕콘
        </h2>
        <div class="tags">
          <span class="flag-basic">공연관람형</span>
          <span class="flag-basic">소규모콘서트</span>
          <span class="flag-basic">아티스트</span>
        </div>
      </div>
      <div class="details-inner" style="padding-bottom:40px;">
        <h3 class="subtit">2월의 덕콘!</h3>
        <p>
          2월에도 다양한 장르의 특별한 아티스트들과<br>
          함께합니다.<br>
          아티스트가 낸 덕력고사 풀고<br>
          콘서트 초청의 기회를 잡으세요!
        </p>
        <ul class="desc-list" style="margin-top:12px;">
          <li><em style="font-weight:500;">2월의 덕콘 라인업</em></li>
          <li style="margin-top:4px;"><span class="day" style="width:36px;">2.11</span> 안녕하신가영</li>
          <li><span class="day" style="width:36px;">2.25</span> 데자부그룹</li>
          <ul class="texts-list" style="margin-top:0; margin-left:44px;">
          <li>Khundi Panda (쿤디판다)</li>
          <li>으네 (UNE)</li>
          <li>Son Simba (손 심바)</li>
          <li>Viann (비앙)</li>
          <li>최엘비 (CHOILB)</li>
        </ul>
        </ul>
      </div>
      <div class="details-inner" style="padding: 30px 20px 32px;">
        <h3 class="subtit">T Factory x FLO 덕콘(THECON)</h3>
        <div class="thumb"><img src="../../../assets/images/program/class86-conts1.jpg" alt="T Factory x FLO 입덕후콘서트"></div>
        <p>
          T Factory와 FLO가 함께 만드는 팬 초청 소규모 콘서트를 소개합니다.<br>
          콘서트가 사라진 요즘, 홍대 인디문화 부흥과 일상의 작은 위로를 전하고자 T Factory에서 매월 다양한 아티스트를 선정하여 무료 콘서트를 진행합니다.<br>
          아티스트가 직접 낸 덕력고사를 통과한 팬들 중 추첨을 통해 콘서트 초청의 기회를 드립니다.
        </p>
        <ul style="margin-top: 22px;">
          <li>※ 본 콘서트는 코로나19 방역 수칙을 준수하여 진행됩니다.</li>
          <li>※ 사회적 거리두기 단계에 따라 비대면으로 전환될 수 있습니다.</li>
        </ul>
        <h3 class="subtit" style="margin-top: 40px;">2월의 덕콘 라인업</h3>
        <program-lineup
            :class-id-list="['142', '143']"
        ></program-lineup>
        <!--ul class="list-program wide" style="margin-top: 12px;">
          <li>
            <a href="./program99">
              <div class="thumb">
                <img src="../../../assets/images/program/class98-conts1.jpg" alt="">
                </div>
              <div class="info">
                <span class="flag-solid8">모집중</span>
                <p class="tit"><em>안녕하신가영</em></p>
                <p class="subtext">2월 11일(금)</p>
              </div>
            </a>
          </li>
          <li>
            <a href="./program100">
              <div class="thumb">
                <img src="../../../assets/images/program/class98-conts2.jpg" alt="">
                </div>
              <div class="info">
                <span class="flag-solid8">모집중</span>
                <p class="tit"><em>데자부그룹</em></p>
                <p class="subtext">2월 25일(토)</p>
              </div>
            </a>
          </li>
        </ul-->
      </div>
    </div>
    <!-- //details -->
  </div>
</template>

<script>
import KakaoShare from '../../common/KakaoShare'
import ProgramLineup from './components/ProgramLineup'
import * as NATIVE from '../../../js/native'

export default {
  name: 'Program98',
  components: {
    KakaoShare,
    ProgramLineup
  },
  data () {
    return {
      isProgramNull: false
    }
  },
  created () {
  },
  mounted () {
    this.$on('program-null', e => {
      this.isProgramNull = true
    })
  },
  methods: {
    clickButton () {
      const redirectURL = 'https://www.instagram.com/tfactory_sampler/'
      const mobileOS = this.$cookies.get('platform')
      if (mobileOS === 'A' || mobileOS === 'I') {
        NATIVE.sysBrowserOpen(mobileOS, redirectURL)
      } else {
        window.open(redirectURL, '_blank')
      }
    }
  }
}
</script>

<style lang="scss">
  @import 'src/assets/css/product';
</style>
<style lang="scss" scoped>
  .texts-list li:nth-child(2):before {
    content: '-' !important;
    margin-left: -9px;
  }
</style>
