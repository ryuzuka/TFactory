<template>
	<div class="contents" :class="{'bottom-sticky': isBookingYn}" ref="contents">
		<!-- slide -->
		<div class="slider-prd">
			<img ref="shareImage" src="../../../assets/images/program/class295-slide1.jpg" alt="3월의 콘썰트 | 십개월의 미래">
		</div>
		<!-- //slide -->
		<!-- details -->
		<div class="details sticky">
			<div class="details-header" style="padding: 31px 20px 40px 20px;">
				<kakao-share
          title="3월의 콘썰트"
          description="십개월의 미래"
        ></kakao-share>

        <em class="main-subtitle">T Factory x B tv</em>
        <h2 class="main-title" style="margin-top:9px;">3월의 콘썰트 상영작</h2>
        <p class="desc2" style="margin-top:8px;">
					‘임신’, 여성에게 있어서 큰 변화의 순간이 아닐까요? ‘십개월의 미래’는 어느날 갑자기 예고없이 ‘임산부’가 된 29살 프로그램 개발자 ‘미래’의 이야기입니다.<br />
					‘임신’이라는 주제가 담긴 영화는 그간 많았지만,<br />
					임산부 당사자의 성장이나 10개월간의 임신 과정을 담은 내용은 흔치 않은데요,<br />
					여성이라면 남 일 같지 않은 ‘미래’의 이야기,<br />
					T Factory x B tv 콘썰트에서 함께 공감해볼까요?
        </p>
			</div>
			<div class="line">
				<span style="margin: 0px 44px;">2023.03.25 PM6:30<em style="margin-left: 20px;">십개월의 미래</em></span>
				<img src="../../../assets/images/program/line-bg.png" alt="THECON line-bg">
			</div>
			<div class="details-header" style="padding: 40px 20px;">
				<em class="main-subtitle">영화 소개</em>
				<h2 class="main-title" style="margin-top:4px;">십개월의 미래</h2>
				<p class="desc_20" style="margin-top: 8px; margin-bottom: 30px;">
					십개월의 미래<br />남궁선 | 2021 | Fiction | HD | Color | 96분
				</p>
				<p class="desc_20" style="margin-top: 8px;">
					만성 숙취를 의심하던 미래는 자신이 임신 10주라는 사실을 알고 당황한다. <br />
					아무 예고 없이 찾아온 변수 앞에서 갈팡질팡하는 사이, 가족과 연인, 국가는 각기 다른 방향을 제시하고 미래의 십개월은 빠른 속도로 흘러간다.
				</p>
			</div>
			<div class="details-inner">
				<h2 class="main-title">일정</h2>
				<dl>
					<dd>
						<span class="sub_title" style="width: 65px; margin-bottom: 6px;">공연일</span>
						<span class="desc">03월 25일(토) 오후 6시 30분</span>
					</dd>
					<dd>
						<span class="sub_title" style="width: 65px; margin-bottom: 6px;">신청기간</span>
						<span class="desc">03월 8일(수) ~ 03월 21일(화)</span>
					</dd>
					<dd>
						<span class="sub_title" style="width: 65px; margin-bottom: 6px;">당첨자발표</span>
						<span class="desc">03월 22일(수) 오후 3시</span>
					</dd>
					<dd>
						<span class="sub_title" style="width: 65px;">장소</span>
						<span class="desc">T Factory 2층, 0 Stage</span>
					</dd>
				</dl>
			</div>
			<div class="details-inner notification">
				<h2 class="main-title">안내사항</h2>
				<ul>
					<li>※ 본 공연은 추첨을 통해 선정되며, 선정자는 개별 MMS 발송드립니다.</li>
					<li>※ 당첨자 중 무단 노쇼하시는 경우, 추후 공연 당첨에서 제외됩니다.</li>
					<li>※ 참석이 불가한 경우 홈페이지 참석을 취소해주세요.</li>
					<li>※ 정부의 방역지침 변경이 있을 시 공연의 주요내용도 변경이 있을 수 있습니다</li>
					<li>※콘썰트는 14세 미만의 고객도 보호자 동반 하에 당첨 및 참여가 가능하나, 보호자도 함께 응모에 당첨되어야 하는점 유의부탁드립니다.</li>
				</ul>
			</div>
			<div class="details-bottom details-inner" style="padding: 40px 20px 12px;">
        <em class="main-subtitle">3월의 콘썰트</em>
        <h2 class="main-title" style="margin:4px 0 0;">라인업</h2>
      </div>
	    <div class="lineup" style="padding: 0px 18px 12px 24px;">
        <ul>
          <li>
	          <div class="date">
		          <span>3.18<br />SAT</span>
	          </div>
	          <router-link to="/experience/program294?classId=254">
		          <div class="card" Style="margin-left: 0px;">
			          <div class="text">
				          <p class="name">성적표의 김민영</p>
				          <p class="time">감독: 임지선, 이재은 <br />배우: 김주아, 윤아정<br />PM 6:30</p>
			          </div>
			          <div class="image">
				          <img src="../../../assets/images/program/class293-musician1.png" alt="musician">
			          </div>
		          </div>
	          </router-link>
          </li>
          <li>
	          <div class="date">
		          <span>3.25<br />SAT</span>
	          </div>
	          <router-link to="/experience/program295?classId=255">
		          <div class="card" Style="margin-left: 19px;">
			          <div class="text">
				          <p class="name">십개월의 미래</p>
				          <p class="time">감독: 남궁선<br />배우: 유이든, 권아름<br />PM 6:30</p>
			          </div>
			          <div class="image">
				          <img src="../../../assets/images/program/class293-musician2.png" alt="musician">
			          </div>
		          </div>
	          </router-link>
          </li>
          <li>
	          <div class="date">
		          <span>4.01<br />SAT</span>
	          </div>
	          <router-link to="/experience/program296?classId=256">
		          <div class="card" Style="margin-left: 19px;">
			          <div class="text">
				          <p class="name">성덕</p>
				          <p class="time">감독: 오세연<br />배우: 오세연<br />PM 6:30</p>
			          </div>
			          <div class="image">
				          <img src="../../../assets/images/program/class293-musician3.png" alt="musician">
			          </div>
		          </div>
	          </router-link>
          </li>
        </ul>
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
  name: 'Program295',
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
	  if (this.$refs.shareImage) {
		  this.$emit('kakao-share-image', this.$refs.shareImage['src'])
	  }
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
.lineup ul li:before{height: 110px;}
.lineup ul li .card{height: 88px;}
.lineup ul li .card .text{padding: 6px 19px 17px;}
.lineup ul li .card .text .name{margin-bottom: 0;}
.lineup ul li .card .image img{width: 88px; height: 88px;}
</style>
