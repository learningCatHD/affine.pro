<template lang="pug">
.overview-sns
  .container.flex.flex-col.items-center
    h2.sns-title.section-grad2-title {{ $t('overviewPage.snsTitle') }}
    .sns-list.flex.flex-wrap.justify-center.gap-30px
      overview-sns-card(
        v-for="sns in COMMUNITY_SNS_LIST"
        :sns="sns"
      )
    .sns-desc(
      v-html="$t('overviewPage.snsDesc')"
    )

</template>

<script setup lang="ts">
import { PATH, COMMUNITY_SNS_LIST } from '~/utils/constants'

</script>

<style lang="stylus">
.overview-sns
  --hashtag-color: #244EE7

  .container
    border-top: 1px solid var(--divider-color)
    padding: fluid-value(60, 180) 20px

  .sns-title
    margin-bottom: fluid-value(40, 103)

  .sns-list
    margin-bottom: fluid-value(40, 115)

    @media $mediaInXS
      max-width: 300px
      column-gap: 16px
      row-gap: 40px

  .sns-desc
    color: var(--primary-deep)

    @media $mediaInXS
      max-width: 300px
      text-align: center

    .hashtag
      font-weight: 800
      color: var(--hashtag-color)

    .text-bold
      font-weight: 800

  /html.dark &
    --hashtag-color: #3E6FDB
</style>
