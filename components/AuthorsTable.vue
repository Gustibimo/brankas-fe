<template>
  <div class="card">
    <div class="card-header pb-0">
      <h6>E-commerce Account List</h6>
    </div>
    <div class="card-body px-0 pt-0 pb-2">
      <div class="table-responsive p-0">
        <table class="table align-items-center mb-0">
          <thead>
            <tr>
              <th class="text-uppercase text-secondary text-xxs font-weight-bolder opacity-7">Jurnal Account</th>
              <th class="text-uppercase text-secondary text-xxs font-weight-bolder opacity-7 ps-2">Email</th>
              <th class="text-uppercase text-secondary text-xxs font-weight-bolder opacity-7 ps-2">Account No</th>
              <th class="text-uppercase text-secondary text-xxs font-weight-bolder opacity-7 ps-2">Account Holder</th>
              <th class="text-uppercase text-secondary text-xxs font-weight-bolder opacity-7 ps-2">Institution</th>
              <th class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7">Status</th>
              <th class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7">Last Data Sync</th>
              <th class="text-secondary opacity-7"></th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="account in accounts" :key="account.id">
              <td>
                <div class="d-flex px-2 py-1">
                  <div class="d-flex flex-column justify-content-center">
                    <p class="text-xs text-secondary mb-0">{{ account.jurnal_account }}</p>
                  </div>
                </div>
              </td>
              <td>
                <div class="d-flex px-2 py-1">
                  <div class="d-flex flex-column justify-content-center">
                    <h6 class="mb-0 text-sm">{{ account.name }}</h6>
                    <p class="text-xs text-secondary mb-0">{{ account.email }}</p>
                  </div>
                </div>
              </td>
              <td>
                <p class="text-xs font-weight-bold mb-0">{{ account.account_no }}</p>
                <p class="text-xs text-secondary mb-0">{{ account.institution }}</p>
              </td>
              <td>
                <p class="text-xs font-weight-bold mb-0">{{ account.account_holder }}</p>
              </td>
              <td>
                <p class="text-xs text-secondary mb-0">{{ account.institution }}</p>
              </td>
              <td class="align-middle text-center text-sm">
                <span :class="'badge badge-sm bg-gradient-' + (account.status === 'Linked' ? 'success' : 'secondary')">{{ account.status }}</span>
              </td>
              <td class="align-middle text-center">
                <span class="text-secondary text-xs font-weight-bold">{{ account.lastSync }}</span>
              </td>
              <td class="align-middle">
                <a href="javascript:;" class="text-secondary font-weight-bold text-xs" data-toggle="tooltip" data-original-title="Edit user">Edit</a>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>


<script>
import Navbar from "@/components/Navbar.vue";
export default {
  name: "authors-table",
  data() {
    return {
      accounts: [
      {
          account_holder: 'John Michael',
          account_no: '076555512223',
          email: 'john@creative-tim.com',
          jurnal_account: 'Manager',
          institution: 'Organization',
          status: 'Linked',
          lastSync: '23/04/18',
        },
        {
          account_holder: 'Alexa Liras',
          account_no: '076555512223',
          email: 'alexa@creative-tim.com',
          jurnal_account: 'Manager',
          institution: 'Organization',
          status: 'Linked',
          lastSync: '23/04/18',
        },
        {
          account_holder: 'Laurent Perrier',
          account_no: '076555512223',
          email: 'laurent@creative-tim.com',
          jurnal_account: 'Manager',
          institution: 'Organization',
          status: 'Unlinked',
          lastSync: '23/04/18',
        },
        {
          account_holder: 'Sean Paul',
          account_no: '076555512223',
          email: 'sean@creative-tim.com',
          jurnal_account: 'Manager',
          institution: 'Organization',
          status: 'Linked',
          lastSync: '23/04/18',
        },
      ],
    };
  },
};
</script>
