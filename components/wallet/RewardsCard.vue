<template lang="pug">
.el-card.resource-page-card(v-if="account")
    .header
        i.el-icon-present
        span.text Genesis and Voting Rewards
    .main
      .item
        span.key.fwr Available Balance:
        span.value  {{ account.core_liquid_balance }}
      .item
        span.key.fwr Refunding CPU:
        span.value  {{ account.refund_request && account.refund_request.cpu_amount }}
      .item
        span.key.fwr Refunding NET:
        span.value  {{ account.refund_request && account.refund_request.net_amount }}

</template>

<script>
import { mapState } from 'vuex'

export default {
  name: 'RewardsCard',

  computed: {
    ...mapState(['account', 'user'])
  }
}
</script>

<style lang="scss" scoped>
.resource-page-card {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
}
.item {
  padding-bottom: 10px;
}
</style>
