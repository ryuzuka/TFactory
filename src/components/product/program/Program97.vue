<template>
  <div class="contentss" ref="contents">
    <!-- slide -->
    <div class="slider-prd">
      <img src="../../../assets/images/program/class97-slide1.jpg" alt="<NEXT 트레이서>">
    </div>
    <!-- //slide -->
    <!-- details -->
    <div class="details sticky">
      <div class="details-header">
        <kakao-share
          title="<NEXT 트레이서>"
          description="조세5국 신입 사원이 되어 숨겨진 돈을 찾아라"
        ></kakao-share>

        <em class="flag-solid7">EXHIBITION</em>
        <h2 class="details-tit">
          &#60;NEXT 트레이서&#62;
          </h2>
        <div class="tags">
          <span class="flag-basic">전시</span>
          <span class="flag-basic">체험</span>
          <span class="flag-basic">이벤트</span>
        </div>
        <p class="desc type2">조세5국 신입 사원이 되어 숨겨진 돈을 찾아라</p>
      </div>
      <div class="details-inner">
        <h3 class="subtit">전시 소개</h3>
        <p>
          2022년 wavve 오리지널 콘텐츠 &#60;트레이서&#62;<br>
          누군가에겐 판검사보다 무서운 곳, 국세청. 일명  ‘쓰레기 하치장’이라 불리는 조세5국에 굴러온 독한 놈의 물불 안 가리는 활약을 그린 통쾌한 추적 활극 &#60;트레이서&#62;. 다소 무거울 수 있는 주제를 유쾌하게 그려내며 시즌 1의 마지막까지 시청률 고공 행진을 거듭했습니다. 종영이 아쉬운 분들을 위해 T Factory와 wavve가 특별한 방 탈출 이벤트를 준비했습니다.<br><br>
          이제 여러분이 ‘NEXT 트레이서’입니다. 트레이서의 주인공처럼 숨겨진 돈에 대한 단서를 찾아 돈벼락을 맞는 통쾌함을 경험해 보세요!
        </p>
        <div class="btn-wrap" style="margin: 24px 0 16px;">
          <button class="btn-line big" @click="clickButton('https://www.instagram.com/tfactory_sampler/')">
            공식 인스타그램 방문하기
          </button>
        </div>
        <h3 class="subtit" style="margin: 48px 0 9px;">일정 및 장소</h3>
        <p style="margin-top: 9px;">
          2022년 2월 5일(토)~4월 중<br>
          T Factory 홍대
        </p>
      </div>
      <div class="details-inner">
        <h3 class="subtit">트레이서 주연배우<br>사인포스터 깜짝 증정 이벤트</h3>
        <p>
         T Factory에 방문해 &#60;NEXT 트레이서&#62;를 즐긴 후 아래 필수 해시태그와 함께 인증샷을 SNS에 업로드해주세요. 추첨을 통해 트레이서 출연 배우 3인의 사인 포스터, 트레이서 OST CD를 드립니다.<br>필수 해시태그: <span style="color: #3c1ddc;">#T팩토리 #트레이서 #찐팬 #wavve</span><br>@tfactory_sampler를 팔로우하면 당첨확률이 더 높아집니다!
        </p>
        <h3 class="subtit" style="margin: 32px 0 9px;">이벤트 기간</h3>
        <p style="margin-top: 9px;">
          3월 22일(화)~체험존 종료일
        </p>
      </div>
      <div class="notice">
        <h4 class="subtit">유의사항</h4>
        <ul class="texts-info">
          <li>* 이 전시는 T Factory 홍대점을 방문하여 스마트폰으로 체크인할 경우에만 참여하실 수 있습니다. (체크인 가능 연령: 만 14세 이상)</li>
          <li style="margin-top:12px">* 이 전시의 자세한 사항은 업체 사정에 따라 안내 없이 중단되거나 변경될 수 있습니다.</li>
        </ul>
      </div>
    </div>
    <!-- //details -->

    <!-- button set -->
		<!--<program-button></program-button>-->
    <!-- // button set -->
  </div>
</template>

<script>
import KakaoShare from '../../common/KakaoShare'
import ProgramButton from './components/ProgramButton'
import * as NATIVE from '../../../js/native'

export default {
  name: 'Program84',
  components: {
    KakaoShare,
    ProgramButton
  },
  data () {
    return {
    }
  },
  created () {
  },
  mounted () {
  },
  methods: {
    clickButton (redirectURL) {
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
.texts-list li:before {
  content: '-' !important;
  margin-left: -9px;
}
.step-list>li:first-child::before {
    margin: 3px 6px 0 -22px;
}
.experience .details-inner {
    padding: 30px 20px 40px;
}
</style>
