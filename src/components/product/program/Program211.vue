<template>
	<div class="contents" :class="{'bottom-sticky': isBookingYn}" ref="contents">
		<!-- slide -->
		<div class="slider-prd">
			<img ref="shareImage" src="../../../assets/images/program/class211-slide1.jpg" alt="T Factory X FLO 플로리다 프로젝트 | 공개방송 방청 신청">
		</div>
		<!-- //slide -->
		<!-- details -->
		<div class="details sticky">
			<div class="details-header" style="padding: 31px 20px 40px 20px;">
				<kakao-share
          title="T Factory X FLO"
          description="T Factory X FLO 플로리다 프로젝트 공개방송 방청 신청"
        ></kakao-share>

        <em class="main-subtitle">T Factory X FLO</em>
        <h2 class="main-title" style="margin-top:4px; letter-spacing: -1px;">플로리다 프로젝트<br>공개방송 방청 신청</h2>
			</div>
			<div class="details-inner">
				<p class="desc2" style="color: #3617ce;">
					느슨해진 오디오씬에 긴장감을 전하러 왔다!!<br>
					장지수X미미미누X조나단의 본격 20대를 위한 어드벤쳐 토크쇼가 T Factory에 찾아옵니다.<br>
					요즘 애들 사이에서는 XX가 떡상한다던데? 어떤 내용인지 궁금하다면 사연과 함께 공개방송 방청에 지금 바로 신청해주세요!
        </p>
			</div>
			<div class="details-inner">
				<h2 class="main-title">일정</h2>
				<dl>
					<dd>
						<span class="sub_title" style="width: 113px;">공개방송 일정</span>
						<span class="desc">8월 13일 (토) 13:00</span>
					</dd>
					<dd>
						<span class="sub_title" style="width: 113px;">방청 신청기간</span>
						<span class="desc">8월 1일 (월) ~ 8월 7일 (일)</span>
					</dd>
					<dd>
						<span class="sub_title" style="width: 113px;">당첨자발표</span>
						<span class="desc">8월 9일 (화)<br> *당첨자 한해 개별 안내</span>
					</dd>
				</dl>
			</div>

			<div class="details-inner notification">
				<h2 class="main-title">안내사항</h2>
				<ul>
					<li>※본 프로그램은 T Factory 홍대점을 방문하여 스마트폰으로 본인 확인한 경우에만 참여 가능합니다. (본인확인 가능 연령 : 만 14세 이상)</li>
					<li>※ 본 프로그램 세부 사항들은 업체 사정에 따라 별도의 안내 없이 중단 또는 변경될 수 있습니다.</li>
				</ul>
			</div>
			<div class="details-inner" style="padding: 40px 0 59px">
				<h2 class="main-title" style="padding: 0 20px; color: #000;">다른 프로그램도 있어요!</h2>
				<div class="program">
					<div class="program">
						<router-link to="/experience/program111?classId=154">
							<div class="desc">
								<p class="detail">대학생 뮤지션이 꾸미는<br>덕콘의 스페셜 무대<br>THECON X University</p>
								<span class="topic">TUMF</span>
							</div>
							<div class="images">
								<img src="../../../assets/images/program/class107-conts1.jpg" alt="TUMF">
							</div>
						</router-link>
					</div>
				</div>
				<div class="program">
					<router-link to="/experience/program110?classId=156">
						<div class="desc">
							<p class="detail" style="margin-bottom: 25px;">Woluld you, 우주?</p>
							<span class="topic">T대학 우주 축제, TUF</span>
						</div>
						<div class="images">
							<img src="../../../assets/images/program/class107-conts2.jpg" alt="T대학 우주 축제, TUF">
						</div>
					</router-link>
				</div>
				<div class="program">
					<router-link to="/experience/program112?classId=155">
						<div class="desc">
							<p class="detail">미술 전공 대학생들의<br>일러스트로 꾸며진 팝업전시<br>POP-UP Exhibition X University</p>
							<span class="topic">TUAF</span>
						</div>
						<div class="images">
							<img src="../../../assets/images/program/class107-conts3.jpg" alt="POP-UP Exhibition X University">
						</div>
					</router-link>
				</div>
			</div>
		</div>
		<!-- //details -->

		<!-- button set -->
		<program-button></program-button>
		<!-- // button set -->
	</div>
</template>

<script>
import KakaoShare from '../../common/KakaoShare'
import ProgramButton from './components/ProgramButton'
import * as NATIVE from '../../../js/native'

export default {
  name: 'Program211',
  components: {
    KakaoShare,
	  ProgramButton
  },
  data () {
    return {
      isLogin: false,
	    isBookingYn: false
    }
  },
  created () {
	  this.$store.watch(() => {
		  if (this.$store.getters.CONSTANTS.session_alive === true) {
			  this.isLogin = true
		  }
	  })
  },
  mounted () {
	  this.$emit('kakao-share-image', this.$refs.shareImage.src)
	  this.$EventBus.$on('get-class-info', data => {
      if (data['PROGRAM_CLASS_BOOKING_YN'] === 1) {
        this.isBookingYn = true
      }
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
</style>
