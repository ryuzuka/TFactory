<template>
  <div class="wrap">
    <Header type="back" :title="$t('comm.reservation') + $t('comm.modify')"></Header>
    <!-- <Header type="back" :title="$t('comm.application') + $t('comm.modify')"></Header> --><!-- 21.03.30 추가 : 신청 수정일 경우 -->
    <my-booking-modify :booking-type="bookingType"></my-booking-modify>

    <modals-container></modals-container>
    <v-dialog></v-dialog>
  </div>
</template>

<script>
import Header from '../../components/common/Header'
import MyBookingModify from '../../components/mypage/booking/BookingModify'

export default {
  name: 'page-booking',
  components: {
    Header,
    MyBookingModify
  },
  data () {
    return {
      bookingType: this.$route.params.type
    }
  },
  created () {
  }
}
</script>
