<template>
  <div class="contents bottom-sticky" ref="contents">
    <!-- slide -->
    <div class="slider-prd swiper-top">
      <swiper :options="swiperOption">
        <swiper-slide>
          <div class="thumb"><img src="../../../assets/images/program/class49-slide1.jpg" alt=""></div>
        </swiper-slide>
        <swiper-slide>
          <div class="thumb"><img src="../../../assets/images/program/class49-slide2.jpg" alt=""></div>
        </swiper-slide>
        <swiper-slide>
          <div class="thumb"><img src="../../../assets/images/program/class49-slide3.jpg" alt=""></div>
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>
    <!-- //slide -->
    <!-- details -->
    <div class="details">
      <div class="details-header">
        <kakao-share
          title="곰손도 가능! 에어팟 가죽케이스 만들기"
          description="크루와 함께하는 원데이 클래스"
        ></kakao-share>

        <em class="flag-solid7">DIY CLASS</em>
        <h2 class="details-tit">
          곰손도 가능!<br>
          에어팟 가죽케이스 만들기
        </h2>
        <div class="tags">
          <span class="flag-basic">원데이클래스</span>
          <span class="flag-basic">초보용</span>
          <span class="flag-basic">가죽공예</span>
        </div>
        <p class="desc type2">
          크루와 함께하는 원데이 클래스<br>
          초보자도 곰손도 쉽게 가죽 케이스를 만들 수 있습니다.
        </p>
        <ul class="texts-info" style="margin-top: 8px; padding-left: 14px; text-indent: -14px;">
          <li>※ 본 프로그램은 SKT의 IT/문화체험 증진 프로그램의 일환으로 무료로 진행됩니다.</li>
        </ul>
      </div>
      <div class="details-inner">
        <h3 class="subtit">클래스 소개</h3>
        <p>
          한 땀 한 땀, 가죽을 꿰매<br>
          에어팟 케이스를 직접 만들며 힐링할 수 있는 클래스!<br>
          바느질을 해본 적 없어도 누구나 나만의 에어팟케이스를 제작할 수 있어요.
        </p>
        <ul class="texts-info" style="margin-top: 20px;">
          <li>
            * 클래스는 Hobby in the Box의 DIY 키트를 통해 진행되는<br>
            클래스입니다.
          </li>
          <li style="margin-top: 0;">
            * 본 클래스에서는 에어팟1, 2세대 및 에어팟 프로 버전이 준비<br>
            되어 있으며, 1개를 선택하여 케이스를 제작할 수 있습니다.
          </li>
        </ul>
        <h3 class="subtit">클래스 구성</h3>
        <ol class="step-list" start="margin-top:20px">
          <li>바느질 기초 배우기</li>
          <li>케이스 종류 및 가죽 선택하기 (에어팟 모델, 색상)</li>
          <li>선택한 가죽을 바느질하기</li>
          <li>완성!</li>
        </ol>
        <ul class="texts-info" style="margin-top: 20px;">
          <li>* 클본 클래스에 제공되는 가죽은 유럽인증 친환경 인조가죽입니다.</li>
          <li style="margin-top: 0;">* 본 클래스는 초보자 전용으로, 재단 및 타공이된 가죽을 사용하여, 재단, 바느질 구멍 타공 등은 배우지 않습니다.</li>
        </ul>
        <h3 class="subtit">준비물</h3>
        <p>
          에어팟 또는 에어팟 프로<br>
          (완성사진을 찍을 용도로 사용하며, 없어도 무방합니다.)
        </p>
        <h3 class="subtit">추천 대상</h3>
        <ul class="texts-list">
          <li>무언가에 집중하면서 몸과 마음의 힐링이 필요하신 분</li>
          <li>나만의 에어팟 케이스를 갖고 싶으신 분</li>
          <li>가죽공예를 아주 살짝 맛만 보고 싶으신 분</li>
          <li>색다른 이색 데이트가 필요한 커플</li>
        </ul>
        <h3 class="subtit">소요시간 및 장소</h3>
        <p>
          1시간<br>
          T Factory 2층, Consulting Zone
        </p>
        <h3 class="subtit">{{ $t('prd.leader-introduction')}}</h3>
        <div class="thumb"><img src="../../../assets/images/program/class49-leader.jpg" alt=""></div>
        <div class="profile">
          <em>T FACTORY CREW</em>
          <span>
            Elline<br>
            엘린
          </span>
          <span style="margin-top:12px;">
            누구나 쉽게 가죽케이스를 완성할 수 있도록,<br>
            엘린이 도와드릴게요.
          </span>
        </div>
        <h3 class="subtit">유의사항</h3>
        <p>
          - 해당 클래스는 약 1시간 소요됩니다.<br>
          - 미취학 아동의 경우 클래스 참여가 제한됩니다.<br>
          - 동일한 클래스에 중복 참여는 불가합니다.
        </p>
      </div>
    </div>

    <!-- //details -->
    <program-button></program-button>
  </div>
</template>

<script>
import KakaoShare from '../../common/KakaoShare'
import ProgramButton from './components/ProgramButton'

export default {
  name: 'Program49',
  components: {
    KakaoShare,
    ProgramButton
  },
  data () {
    return {
      swiperOption: {
        slidesPerView: 1,
        pagination: {
          el: '.swiper-pagination'
        }
      }
    }
  },
  created () {
  },
  mounted () {
  },
  methods: {
  }
}
</script>

<style lang="scss">
  @import 'src/assets/css/product';
</style>
