<template>
  <div class="wrap">
    <Header v-if="programType === 'basic'" type="back" title="예약/신청 내역 상세"></Header> <!-- 21.03.30 수정 : 예약 상세 내역 -->
    <Header v-else-if="programType === 'select'" type="back" title="예약/신청 내역 상세"></Header> <!-- 21.03.30 추가 : 신청 상세 내역 -->
    <MyBookingDetail :booking-type="bookingType"></MyBookingDetail>

    <modals-container></modals-container>
    <v-dialog></v-dialog>
  </div>
</template>

<script>
import Header from '../../components/common/Header'
import MyBookingDetail from '../../components/mypage/booking/BookingDetail'

export default {
  name: 'page-booking',
  components: {
    Header,
    MyBookingDetail
  },
  data () {
    return {
      bookingType: this.$route.params.type,
      programType: 'basic'
    }
  },
  mounted () {
    this.$on('change-application-type', e => {
      if (e.type === 'select') {
        this.programType = 'select'
      }
    })
  }
}
</script>
