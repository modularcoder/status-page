<script setup>
  const statusHistoryApi = Array.apply(null, Array(200))
    .map(
      function (x, i) { 
        return {
          status:  i % 7 === 0 ? 'warning' : 'success',
        }; 
    })

    const statusHistoryDashboard = Array.apply(null, Array(200))
      .map(
        function (x, i) { 
          return {
            status:  i % 9 === 0 ? 'warning' : 'success',
          }; 
      })

    const statusHistoryLanding = Array.apply(null, Array(200))
      .map(
        function (x, i) { 
          return {
            status:  i % 11 === 0 ? 'danger' : 'success',
          }; 
      })
</script>

<template>
  <div class="PageContainer">
    <header class="Header">
      <div class="HeaderLogoGroup">
        <div class="LogoContainer">
          <img src="./_assets/logo.svg" />
        </div>
        <div class="HeaderLogoGroupDivider"></div>
        <div class="BreadCrumbsContainer">
          <span>Status</span>
        </div>
      </div>

      <a class="BaseButton">
        E-mail helpdesk
      </a>
    </header>
    <scetion class="SectionSatusOverview">
        <div class="StatusIcon --sucess">
          <svg width="29" height="22" viewBox="0 0 29 22" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M25.75 3.5L10.625 18.625L3.75 11.75" stroke="white" stroke-width="6" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </div>
        <h2>All services are online</h2>
        <p class="StatusDate">As of June 1st, 1:46 PM ET</p>

    </scetion>
    <section class="SectionStatusByService">
      <div class="SectionStatusByServiceHeader">
        <h4>
          Current status by service
        </h4>
      </div>
      <div class="SectionStatusByServiceItem">
        <div class="StatusHistoryItem">
          <header class="StatusHistoryItemHeader">
            <h5>API</h5>
            <span class="StatusHistoryItemHeaderUptime">99.987% uptime</span>
          </header>
          <div class="StatusHistoryItemChart">
            <div 
              class="StatusHistoryItemChartPoint" 
              :class="[
                item.status === 'success' && 'success',
                item.status === 'warning' && 'warning',
                item.status === 'danger' && 'danger',
              ]" 
              :style="{
                left: `${index * 8}px`
              }"
              v-for="(item, index) in statusHistoryApi"></div>
          </div>
        </div>
      </div>
      <div class="SectionStatusByServiceItem">
        <div class="StatusHistoryItem">
          <header class="StatusHistoryItemHeader">
            <h5>Dashboard</h5>
            <span class="StatusHistoryItemHeaderUptime">99.987% uptime</span>
          </header>
          <div class="StatusHistoryItemChart">
            <div 
              class="StatusHistoryItemChartPoint" 
              :class="[
                item.status === 'success' && 'success',
                item.status === 'warning' && 'warning',
                item.status === 'danger' && 'danger',
              ]" 
              :style="{
                left: `${index * 8}px`
              }"
              v-for="(item, index) in statusHistoryDashboard"></div>
          </div>
        </div>
      </div>
      <div class="SectionStatusByServiceItem">
        <div class="StatusHistoryItem">
          <header class="StatusHistoryItemHeader">
            <h5>Landing Page</h5>
            <span class="StatusHistoryItemHeaderUptime">99.987% uptime</span>
          </header>
          <div class="StatusHistoryItemChart">
            <div 
              class="StatusHistoryItemChartPoint" 
              :class="[
                item.status === 'success' && 'success',
                item.status === 'warning' && 'warning',
                item.status === 'danger' && 'danger',
              ]" 
              :style="{
                left: `${index * 8}px`
              }"
              v-for="(item, index) in statusHistoryLanding"></div>
          </div>
        </div>
      </div>
    </section>
    <footer class="Footer">
      <div class="FooterCopyrightDate">
        @ 2020 wallmine
      </div>
      <div class="FooterPoweredBy">
        Powered by
        <svg class="FooterPoweredByLogo" width="96" height="21" viewBox="0 0 96 21" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M25.9879 9.95713C26.8368 9.74193 27.3867 9.20395 27.3867 8.24753C27.3867 6.89659 26.4661 6.10754 24.1588 6.10754H21.2537V14.4762H24.625C26.8846 14.4762 27.841 13.46 27.841 12.0732C27.841 10.9494 27.2313 10.1962 25.9879 9.95713ZM24.2903 7.41066C25.2467 7.41066 25.7608 7.67368 25.7608 8.42686C25.7608 9.19199 25.2108 9.49087 24.4935 9.49087H22.8318V7.41066H24.2903ZM24.6968 13.1731H22.8318V10.6744H24.6729C25.3782 10.6744 26.1792 10.8896 26.1792 11.9656C26.1792 12.7905 25.5575 13.1731 24.6968 13.1731Z" fill="#0E153A"/>
          <path d="M31.4376 7.99647C29.4649 7.99647 28.389 9.38328 28.389 11.3081C28.389 13.209 29.5486 14.6436 31.5332 14.6436C32.8483 14.6436 33.7808 14.1056 34.3546 13.1731L33.1113 12.5395C32.8363 13.0535 32.3462 13.4241 31.6049 13.4241C30.6007 13.4241 30.0029 12.8264 29.9551 11.6667H34.4025V11.3559C34.4025 9.40719 33.3265 7.99647 31.4376 7.99647ZM31.4256 9.16808C32.2505 9.16808 32.7646 9.64629 32.8363 10.6266H29.9671C30.0508 9.6702 30.5887 9.16808 31.4256 9.16808Z" fill="#0E153A"/>
          <path d="M37.1829 6.58575L35.6526 7.17024V8.23557H34.7918V9.35937H35.6526V12.8383C35.6526 13.9263 36.1428 14.6436 37.5655 14.6436C38.0795 14.6436 38.5219 14.5599 38.8805 14.4403V13.2448C38.6056 13.3165 38.2828 13.3883 37.9361 13.3883C37.3622 13.3883 37.1829 13.1372 37.1829 12.6112V9.35937H38.749V8.23557H37.1829V6.58575Z" fill="#0E153A"/>
          <path d="M41.4676 6.58575L39.9374 7.17024V8.23557H39.0766V9.35937H39.9374V12.8383C39.9374 13.9263 40.4275 14.6436 41.8502 14.6436C42.3643 14.6436 42.8066 14.5599 43.1653 14.4403V13.2448C42.8903 13.3165 42.5675 13.3883 42.2208 13.3883C41.647 13.3883 41.4676 13.1372 41.4676 12.6112V9.35937H43.0338V8.23557H41.4676V6.58575Z" fill="#0E153A"/>
          <path d="M46.5801 7.99647C44.6075 7.99647 43.5315 9.38328 43.5315 11.3081C43.5315 13.209 44.6912 14.6436 46.6757 14.6436C47.9908 14.6436 48.9233 14.1056 49.4972 13.1731L48.2538 12.5395C47.9788 13.0535 47.4887 13.4241 46.7475 13.4241C45.7432 13.4241 45.1455 12.8264 45.0976 11.6667H49.545V11.3559C49.545 9.40719 48.469 7.99647 46.5801 7.99647ZM46.5681 9.16808C47.393 9.16808 47.9071 9.64629 47.9788 10.6266H45.1096C45.1933 9.6702 45.7313 9.16808 46.5681 9.16808Z" fill="#0E153A"/>
          <path d="M53.7959 7.99647C53.1145 7.99647 52.4928 8.37904 52.0624 9.20395V8.1758H50.556V14.4762H52.0863V11.7385C52.0863 10.0049 52.8514 9.5387 53.8437 9.5387C53.9274 9.5387 54.0231 9.5387 54.2263 9.55065V8.03234C54.0948 8.00843 53.9394 7.99647 53.7959 7.99647Z" fill="#0E153A"/>
          <path d="M64.2087 6.10754H62.6187V11.4396C62.6187 12.7307 62.0448 13.3524 60.8852 13.3524C59.7136 13.3524 59.1397 12.7786 59.1397 11.4396V6.10754H57.5616V11.4754C57.5616 13.1014 58.3507 14.7034 60.8732 14.7034C63.336 14.7034 64.2087 13.1253 64.2087 11.4754V6.10754Z" fill="#0E153A"/>
          <path d="M68.9284 7.99647C68.2589 7.99647 67.5894 8.23557 67.1112 8.84529V8.1758H65.6168V16.4488H67.1471V13.8426C67.5297 14.3567 68.1513 14.6436 68.9045 14.6436C70.6261 14.6436 71.702 13.209 71.702 11.2961C71.702 9.35937 70.5902 7.99647 68.9284 7.99647ZM68.5817 9.25177C69.5621 9.25177 70.112 10.0169 70.112 11.2961C70.112 12.659 69.4784 13.4002 68.5698 13.4002C67.7209 13.4002 67.0634 12.7547 67.0634 11.3081C67.0634 9.93322 67.709 9.25177 68.5817 9.25177Z" fill="#0E153A"/>
          <path d="M74.508 6.58575L72.9777 7.17024V8.23557H72.1169V9.35937H72.9777V12.8383C72.9777 13.9263 73.4679 14.6436 74.8905 14.6436C75.4046 14.6436 75.847 14.5599 76.2056 14.4403V13.2448C75.9306 13.3165 75.6079 13.3883 75.2612 13.3883C74.6873 13.3883 74.508 13.1372 74.508 12.6112V9.35937H76.0741V8.23557H74.508V6.58575Z" fill="#0E153A"/>
          <path d="M77.7885 5.34241C77.2864 5.34241 76.856 5.74889 76.856 6.25101C76.856 6.75313 77.2864 7.1596 77.7885 7.1596C78.2906 7.1596 78.721 6.75313 78.721 6.25101C78.721 5.74889 78.2906 5.34241 77.7885 5.34241ZM78.5536 8.1758H77.0233V14.4762H78.5536V8.1758Z" fill="#0E153A"/>
          <path d="M86.9476 7.99647C86.1824 7.99647 85.4293 8.29535 84.9511 9.03658C84.6522 8.37904 84.0664 7.99647 83.1936 7.99647C82.4883 7.99647 81.9144 8.27144 81.4601 8.89311V8.1758H79.9538V14.4762H81.484V10.9255C81.484 9.95713 82.022 9.29959 82.7513 9.29959C83.5762 9.29959 83.7077 9.87344 83.7077 11.057V14.4762H85.238V10.9255C85.238 9.95713 85.764 9.29959 86.4933 9.29959C87.3062 9.29959 87.4617 9.87344 87.4617 11.057V14.4762H88.9919V10.4234C88.9919 8.89311 88.3105 7.99647 86.9476 7.99647Z" fill="#0E153A"/>
          <path d="M93.035 7.99647C91.0624 7.99647 89.9865 9.38328 89.9865 11.3081C89.9865 13.209 91.1461 14.6436 93.1307 14.6436C94.4458 14.6436 95.3783 14.1056 95.9521 13.1731L94.7088 12.5395C94.4338 13.0535 93.9436 13.4241 93.2024 13.4241C92.1982 13.4241 91.6004 12.8264 91.5526 11.6667H95.9999V11.3559C95.9999 9.40719 94.924 7.99647 93.035 7.99647ZM93.0231 9.16808C93.848 9.16808 94.3621 9.64629 94.4338 10.6266H91.5645C91.6482 9.6702 92.1862 9.16808 93.0231 9.16808Z" fill="#0E153A"/>
          <path d="M8.63434 10.022V3.72057C8.63434 2.65354 7.29426 2.17776 6.62141 3.00589L1.5015 9.30731C0.899726 10.048 1.42679 11.1553 2.3811 11.1553H7.501C8.12693 11.1553 8.63434 10.6479 8.63434 10.022Z" fill="url(#paint0_linear_2_12097)"/>
          <path d="M13.5591 9.8269H8.43924C7.81332 9.8269 7.30591 10.3343 7.30591 10.9602V17.2617C7.30591 18.3287 8.64598 18.8045 9.31884 17.9763L14.4387 11.6749C15.0405 10.9343 14.5135 9.8269 13.5591 9.8269Z" fill="#0E153A"/>
          <defs>
          <linearGradient id="paint0_linear_2_12097" x1="3.98508" y1="2.85307" x2="9.63061" y2="13.4799" gradientUnits="userSpaceOnUse">
          <stop stop-color="#BCBECD"/>
          <stop offset="1" stop-color="#BCBECD" stop-opacity="0"/>
          </linearGradient>
          </defs>
        </svg>
      </div>

    </footer>
  </div>
</template>

<style lang="scss" scoped>
.PageContainer {
  max-width: 800px;
  margin: 0 auto;
  padding-top: 25px;
}

.Header {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.HeaderLogoGroup {
  display: flex;
  align-items: center;
}

.HeaderLogoGroupDivider {
  width: 1px;
  background: #BFC2D44D;
  height: 20px;
  margin-left: 16px;
  margin-right: 16px;
}

.BaseButton {
  background: #5F59F7;
  padding: 9px 20px;
  border-radius: 4px;
  line-height: 22px;
  font-weight: 500;
  color: #fff;
}

.SectionSatusOverview {
  padding-top: 100px;
  padding-bottom: 40px;
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.StatusIcon {
  width: 66px;
  height: 66px;
  border-radius: 100%;
  background: #21B062;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 12px;
}

.StatusDate {
  font-weight: 500;
  font-size: 14px;
  line-height: 20px;
  font-weight: normal;
  color: rgba(66, 71, 97, 0.5);
}

h2 {
  font-weight: 600;
  font-size: 28px;
  line-height: 43px;
}

h4 {
  font-family: Inter;
  font-size: 18px;
  font-weight: 600;
  line-height: 20px;
  letter-spacing: -0.5px;
  text-align: left;
}

h5 {
  font-family: Inter;
  font-size: 15px;
  font-weight: 600;
  line-height: 20px;
  letter-spacing: 0px;
  text-align: left;
}

.SectionStatusByService {
  background: #FFFFFF;
  box-shadow: 0px 20px 30px rgba(63, 63, 68, 0.07), 0px 1px 3px rgba(63, 63, 68, 0.15);
  border-radius: 8px;
}


.SectionStatusByServiceHeader {
  padding: 20px;
  background: linear-gradient(0deg, #FAFAFC, #FAFAFC), #FFFFFF;
  border-radius: 8px 8px 0 0;
}

.StatusHistoryItemHeaderUptime {

}

.SectionStatusByServiceItem {
  padding: 20px;
}

.StatusHistoryItemHeader {
  width: 100%;
  margin-bottom: 12px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}

.StatusHistoryItemChart {
  flex-wrap: nowrap;
  overflow: hidden;
  position: relative;
  height: 40px;
}

.StatusHistoryItemChartPoint {
  position: absolute;
  width: 5px;
  margin-right: 3px;
  border-radius: 3px;
  height: 100%;
}

.StatusHistoryItemChartPoint.success {
  background: #21B062;
}

.StatusHistoryItemChartPoint.warning {
  background: #FFB72B;
}

.StatusHistoryItemChartPoint.danger {
  background: #DE3618;
}


.Footer {
  margin-top: 32px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  font-family: Inter;
  font-size: 12px;
  font-weight: 500;
  line-height: 20px;
  letter-spacing: 0px;
  text-align: right;
  color: #424761;
}

.FooterPoweredBy {
  display: flex;
  align-items: center;
}

.FooterPoweredByLogo {
  margin-left: 8px;
}
</style>
