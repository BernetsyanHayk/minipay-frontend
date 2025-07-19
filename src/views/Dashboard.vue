<template>
  <admin-layout>
    <div class="grid grid-cols-12 gap-4 md:gap-6">
      <div class="col-span-12 space-y-6 xl:col-span-7">
        <cards />
        <statistics-chart />
      </div>
      <div class="col-span-12 xl:col-span-5">
        <monthly-sale />
      </div>

      <div class="col-span-12">
        <recent-transactions />
      </div>
    </div>
  </admin-layout>
</template>

<script>
import AdminLayout from '../components/layout/AdminLayout.vue'
import Cards from '../components/dashboard/Cards.vue'
import MonthlyTarget from '../components/dashboard/MonthlySale.vue'
import MonthlySale from '../components/dashboard/MonthlyTarget.vue'
import CustomerDemographic from '../components/dashboard/CustomerDemographic.vue'
import StatisticsChart from '../components/dashboard/StatisticsChart.vue'
import RecentTransactions from '../components/dashboard/RecentTransactions.vue'
export default {
  components: {
    AdminLayout,
    Cards,
    MonthlyTarget,
    MonthlySale,
    CustomerDemographic,
    StatisticsChart,
    RecentTransactions,
  },
  name: 'Dashboard',
}
</script>
