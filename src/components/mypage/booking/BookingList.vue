<template src="../../../assets/html/mypage/booking/booking-list.html"></template>

<script>
import * as STORE from '../../../js/store.js'

/**
 * apply: '신청완료',
 * ordered: '예약완료, 접수대기(상담원 배정중 - field, field_buy)'
 * operator_assigned: '접수완료(상담원 배정 완료)'
 * completed: '참여완료'
 * canceled: '취소'
 * canceled_by_operator: '취소(관리자)'
 * satisfaction_surveyed: '만족도 조사 완료'
 * counseling: '상담중'
 * no_show: '미방문'
 * selected: '당첨'
 * not_selected: '미당첨'
 * end: '종료'
 */

let BOOKING_STATUS = {
  'apply': 'apply', // 신청완료
  'ordered': 'success', // 예약완료
  'canceled': 'cancel', // 취소
  'canceled_by_operator': 'cancel', // 취소
  'completed': 'complete', // 참여완료
  'satisfaction_surveyed': 'complete', // 참여완료
  'end': 'end', // 종료
  'counseling': 'counseling', // 상담중
  'no_show': 'not', // 미방문
  'operator_assigned': 'operator_assigned', // 접수완료 (상담원 배정 완료)
  'selected': 'selected', // 당첨
  'not_selected': 'not_selected' // 미당첨
}

export default {
  name: 'MyBookingList',
  data () {
    return {
      loading: null,
      isLoading: false,
      listData: []
    }
  },
  methods: {
    goDetailBookInfo (data) {
      if (data.type !== 'twf-counseling') {
        this.$router.push(`/my/booking/${data.type}/detail/${data.status}?BOOK_ID=${data.BOOK_ID}`)
      }
    },
    clickMore () {
      this.getBookingList()
    },
    getBookingList () {
      STORE.getMyBookingList(this.lastIndex).then(result => {
        result['BOOKING'].forEach(booking => {
          booking.type = booking.TYPE
          let STATUS = booking['STATUS']
          booking.status = BOOKING_STATUS[STATUS.toString()]
          if (parseInt(booking['PROGRAM_CLASS_ID']) === 36) { // Xbox 컨트롤러 TO-GO
            booking.date = this.$moment(booking.DATE).format('YYYY.MM.DD')
          } else {
            booking.date = this.$moment(booking.DATE).format('YYYY.MM.DD HH:mm')
          }
        })
        this.listData = result['BOOKING']
      })
    },
    clickSatisfaction (bookId) {
      this.$router.push('/my/satisfaction?bookId=' + bookId)
    }
  },
  mounted () {
    if (!this.$cookies.get('USER_AUTH')) {
      localStorage.setItem('previous_url', '/my/booking/list')
      this.$router.push({name: 'Login'})
    } else {
      this.getBookingList()
    }
  }
}
</script>

<style lang="scss">
  @import 'src/assets/css/mypage';
</style>
