<!-- prettier-ignore -->
<template>
  <div class="container-fluid py-4" style="min-height: 450px">
    <div class="row">
      <div class="col-12">
        <div class="card my-4">
          <div class="card-header p-0 position-relative mt-n4 mx-3 z-index-2">
            <div
              class="bg-gradient-info shadow-light border-radius-lg pt-4 pb-3"
            >
              <h6 class="text-white text-capitalize ps-3" >Data Alumni</h6>
            </div>
          </div>
          <div class="card-body pb-1">
            <form id="form_alumni">
              <!-- <div class="row">
                <div class="col-3">
                  <div class="input-group input-group-outline mb-3">
                    <label class="col-12">Tahun Lulus</label><br/>
                    <div class="col-12">
                        <Select2 v-model="tahunLulus" :options="optionsTahunLulus" :settings="{ settingOption: value, settingOption: value }" @change="myChangeEvent($event)" @select="mySelectEvent($event)" />
                    </div>
                  </div>
                </div>
                <div class="col-3">
                  <div class="input-group input-group-outline mb-3">
                    <label class="label col-12">Fakultas</label><br/>
                    <div class="col-12">
                        <Select2 v-model="fakultas" :options="optionsFakultas" :settings="{ settingOption: value, settingOption: value }" @change="myChangeEvent($event)" @select="mySelectEvent($event)" />
                    </div>
                  </div>
                </div>
                <div class="col-3">
                  <div class="input-group input-group-outline mb-3">
                    <label class="label col-12">Jurusan</label><br/>
                    <div class="col-12">
                        <Select2 v-model="jurusan" :options="optionsJurusan" :settings="{ settingOption: value, settingOption: value }" @change="myChangeEvent($event)" @select="mySelectEvent($event)" />
                    </div>
                  </div>
                </div>
                <div class="col-2">
                  <vmd-button
                      class="my-4 mb-2"
                      id="btnSimpan"
                      variant="gradient"
                      color="info"
                      fullWidth
                      >Search
                    </vmd-button>
                </div>
              </div> -->
            </form>
            <div class="table-responsive p-0" id="tbl_alumni">
              <table
                class="table align-items-center mb-0"
              >
                <thead>
                  <tr>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      Aktivasi
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      Dokumen
                    </th>
                    <th
                      class="text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      Nama
                    </th>
                    <th
                      class="text-uppercase text-secondary text-xxs font-weight-bolder opacity-7 ps-2"
                    >
                      NIM
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      NIK
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      Jenis Kelamin
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      Tempat Lahir
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      Tanggal Lahir
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      Fakultas
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      Jurusan
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      No Hp
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      Alamat Tinggal
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      Tahun Masuk
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      Tahun Lulus
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      Gelar Depan
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      Gelar Belakang
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      Act
                    </th>
                  </tr>
                </thead>
                <tbody>
                  <tr v-for="alumni in alumnis" :key="alumni.id">
                    <td class="d-flex flex-column justify-content-center">
                      <strong class="text-success p-1" style="font-size:12px"
                        v-if="alumni.completed == '1'"
                      >
                        <i class="fa fa-check"></i> 
                        Data Lengkap
                      </strong>
                      <strong class="text-warning p-1" style="font-size:12px"
                        v-else
                      >
                        <i class="fa fa-exclamation-triangle"></i> 
                        Belum Lengkap
                      </strong>
                      <strong class="text-success p-1" style="font-size:12px"
                        v-if="alumni.validated == '1'"
                      >
                        <i class="fa fa-check"></i> 
                        Tervalidasi
                      </strong>
                      <strong class="text-danger p-1" style="font-size:12px"
                        v-else-if="alumni.validated == '0'"
                      >
                        <i class="fa fa-times"></i> 
                        Tidak Tervalidasi
                      </strong>
                      
                    </td>
                    <td>
                      <div class="d-flex px-2 py-1">
                        <div class="d-flex flex-column justify-content-center">
                          <a v-if="alumni.bachelor_certificate_url != null"
                            href="javascript:;"
                            class="badge badge-sm bg-gradient-info mb-1"
                            data-toggle="tooltip"
                            data-original-title=""
                          >
                            <i class="fa fa-check"></i>
                            Ijazah
                          </a>
                          <a v-else
                            href="javascript:;"
                            class="badge badge-sm bg-gradient-danger mb-1"
                            data-toggle="tooltip"
                            data-original-title=""
                          >
                            <i class="fa fa-times"></i>
                            Ijazah
                          </a>
                          <a v-if="alumni.identity_card_url != null"
                            href="javascript:;"
                            class="badge badge-sm bg-gradient-info"
                            data-toggle="tooltip"
                            data-original-title=""
                          >
                            <i class="fa fa-check"></i>
                            KTP
                          </a>
                          <a v-else
                            href="javascript:;"
                            class="badge badge-sm bg-gradient-danger mb-1"
                            data-toggle="tooltip"
                            data-original-title=""
                          >
                            <i class="fa fa-times"></i>
                            KTP
                          </a>
                          <!-- <a
                            v-if="profil.ijazah === 'ya'"
                            href="javascript:;"
                            class="badge badge-sm bg-gradient-primary mb-1"
                            data-toggle="tooltip"
                            data-original-title=""
                          >
                            <i class="fa fa-check"></i>
                            Ijazah
                          </a>
                          <a
                            v-if="profil.ktp === 'ya'"
                            href="javascript:;"
                            class="badge badge-sm bg-gradient-info"
                            data-toggle="tooltip"
                            data-original-title=""
                          >
                            <i class="fa fa-check"></i>
                            KTP
                          </a> -->
                        </div>
                      </div>
                    </td>
                    <td>
                      <div class="d-flex px-2 py-1">
                        <div>
                          <img v-if="alumni.photo_url != null"
                            :src="alumni.photo_url"
                            class="avatar avatar-sm me-3 border-radius-lg"
                            alt="user"
                          />
                          <img v-else
                            src="/img/user.4968cec9.png"
                            class="avatar avatar-sm me-3 border-radius-lg"
                            alt="user"
                          />
                        </div>
                        <div class="d-flex flex-column justify-content-center">
                          <h6 class="mb-0 text-sm">
                            <a
                              href="#"
                              @click="show(alumni)"
                            >
                              {{ alumni.name }}
                            </a>
                          </h6>
                          <p class="text-xs text-secondary mb-0">
                            {{ alumni.email }}
                          </p>
                        </div>
                      </div>
                    </td>
                    <td>
                      <p class="text-xs font-weight-bold mb-0">
                        {{ alumni.nim }}
                      </p>
                    </td>
                    <td class="align-middle text-left text-sm">
                      <p class="text-xs font-weight-bold mb-0">
                        {{ alumni.nik }}
                      </p>
                    </td>
                    <td class="align-middle text-center">
                      <span class="text-secondary text-xs font-weight-bold">
                        {{ alumni.gender }}
                      </span>
                    </td>
                    <td class="align-middle text-center">
                      <span class="text-secondary text-xs font-weight-bold">
                        {{ alumni.birth_place }}
                      </span>
                    </td>
                    <td class="align-middle text-center">
                      <span class="text-secondary text-xs font-weight-bold">
                        {{ alumni.birth_date }}
                      </span>
                    </td>
                    <td class="align-middle text-center">
                      <span class="text-secondary text-xs font-weight-bold">
                        {{ alumni.faculty }}
                      </span>
                    </td>
                    <td class="align-middle text-center">
                      <span class="text-secondary text-xs font-weight-bold">
                        {{ alumni.departement }}
                      </span>
                    </td>
                    <td class="align-middle text-center">
                      <span class="text-secondary text-xs font-weight-bold">
                        {{ alumni.phone_number }}
                      </span>
                    </td>
                    <td class="align-middle text-center">
                      <span class="text-secondary text-xs font-weight-bold">
                        {{ alumni.address }}
                      </span>
                    </td>
                    <td class="align-middle text-center">
                      <span class="text-secondary text-xs font-weight-bold">
                        {{ alumni.entry_year }}
                      </span>
                    </td>
                    <td class="align-middle text-center">
                      <span class="text-secondary text-xs font-weight-bold">
                        {{ alumni.graduate_year }}
                      </span>
                    </td>
                    <td class="align-middle text-center">
                      <span class="text-secondary text-xs font-weight-bold">
                        
                      </span>
                    </td>
                    <td class="align-middle text-center">
                      <span class="text-secondary text-xs font-weight-bold">
                        
                      </span>
                    </td>
                    <td class="align-middle">
                      <a 
                        href="#"
                        @click="show(alumni)"
                        class="badge bg-gradient-primary"
                        data-toggle="tooltip"
                        data-original-title="Lihat Alumni"
                        style="margin-right:5px"
                      >
                        <i class="fa fa-user"></i>
                      </a>
                      <a
                        href="javascript:;"
                        class="badge bg-gradient-info"
                        data-toggle="tooltip"
                        data-original-title="Edit Alumni"
                        style="margin-right:5px"
                      >
                        <i class="fa fa-pencil"></i>
                      </a>
                      <a
                        href="#"
                        @click="hapus(alumni)"
                        class="badge bg-gradient-danger"
                        data-toggle="tooltip"
                        data-original-title="Hapus Alumni"
                        style="margin-right:5px"
                      >
                        <i class="fa fa-trash"></i>
                      </a>
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
/* eslint-disable */
import Select2 from 'vue3-select2-component';
import VmdButton from "@/components/VmdButton.vue";
import axios from "axios";
// import $ from "jquery";

export default {
  name: "table-alumni",
  components: {
    Select2,
    VmdButton
  },
  data() {
        return {
            src: '',
            tahunLulus: 'Pilih Tahun',
            fakultas: 'Pilih Fakultas',
            jurusan: 'Pilih Jurusan',
            optionsFakultas: ['Pilih Fakultas','Teknik', 'Bahasa dan Seni', 'MIPA', 'Ekonomi', 'Ilmu Sosial'],
            optionsJurusan: ['Pilih Jurusan','Teknik Informatika', 'Teknik Mesin', 'Seni Rupa', 'Ekonomi Bisnis', 'Pendidikan Ilmu Sosial'],
            optionsTahunLulus: ['Pilih Tahun','2022', '2021', '2020', '2019', '2018'], // or [{id: key, text: value}, {id: key, text: value}]
            alumnis:[],
          }
    },
    methods: {
        load(){
          axios.get('http://api.alumni.eduraya.co.id/api/alumni').then(res => {
            this.alumnis = res.data.user
        }).catch ((err) => {
          console.log(err);
        })
      },
      show(alumni){ 
        this.$router.push('/admin/profile_alumni/'+alumni.id);
      },
      hapus(alumni){ 
        axios.delete('http://api.alumni.eduraya.co.id/api/alumni/'+alumni.id).then(res => {
            console.log(res.data)
            this.load()
            let index = this.alumnis.indexOf(alumni.id)
            this.alumnis.splice(index,1)
        }).catch ((err) => {
          console.log(err);
        })
      },
    },
    mounted() {
      this.load();
      // $('#tbl_alumni').hide();
      // $("#btnSimpan").click(function(e){
      //   e.preventDefault();
      //   $("#tbl_alumni").show();
      //   $("#form_alumni").hide();
      // })
  },
};
</script>
