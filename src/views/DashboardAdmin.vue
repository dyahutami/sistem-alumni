<template>
  <div class="py-4 container-fluid" style="min-height: 450px">
    <div class="row mb-4">
      <div class="col-lg-12 position-relative z-index-2">
        <div class="row">
          <div class="col-lg-4 col-md-6 col-sm-6 mt-lg-0 mt-4">
            <mini-cards
              title="Data Profil Lengkap"
              value="2"
              iconName="person"
              iconClass="text-white"
              iconBackground="bg-gradient-info"
            />
          </div>
          <div class="col-lg-4 col-md-6 col-sm-6 mt-lg-0 mt-4">
            <mini-cards
              title="Data Tracer Study Lengkap"
              value="1"
              iconName="person"
              iconClass="text-white"
              iconBackground="bg-gradient-success"
            />
          </div>
          <div class="col-lg-4 col-md-6 col-sm-6 mt-lg-0 mt-4">
            <mini-cards
              title="Data Alumni"
              value="6"
              iconName="person"
              iconClass="text-white"
              iconBackground="bg-gradient-warning"
            />
          </div>
          <div class="col-lg-4 col-md-6 col-sm-6 mt-lg-0 mt-4">
            <mini-cards
              title="Bekerja"
              value="1"
              iconName="work"
              iconClass="text-white"
              iconBackground="bg-gradient-info"
            />
          </div>
          <div class="col-lg-4 col-md-6 col-sm-6 mt-lg-0 mt-4">
            <mini-cards
              title="Melanjutkan"
              value="0"
              iconName="school"
              iconClass="text-white"
              iconBackground="bg-gradient-success"
            />
          </div>
          <div class="col-lg-4 col-md-6 col-sm-6 mt-lg-0 mt-4">
            <mini-cards
              title="Wirausaha"
              value="0"
              iconName="storefront"
              iconClass="text-white"
              iconBackground="bg-gradient-warning"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
  <!-- prettier-ignore -->
  <div class="modal fade" id="modalDokumen">
    <div class="modal-dialog modal-dialog-centered" role="document">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title font-weight-normal" id="exampleModalLabel">Upload Dokumen</h5>
          <button type="button" class="btn-close text-dark closeModal" data-bs-dismiss="modal" aria-label="Close">
            <span aria-hidden="true">&times;</span>
          </button>
        </div>
        <div class="modal-body">
          <div class="row">
            <div class="col-md-6">
              <div class="input-group input-group-outline mb-3">
                <label class="label col-12">KTP</label><br/>
                <input type="file" class="form-control" name="ktp" isrequired="true">
              </div>
            </div>
            <div class="col-md-6">
              <div class="input-group input-group-outline mb-3">
                <label class="label col-12">Ijazah</label><br/>
                <input type="file" class="form-control" name="ijazah" isrequired="true">
              </div>
            </div>
          </div>
        </div>
        <div class="modal-footer">
          <button type="button" class="btn bg-gradient-secondary closeModal" data-bs-dismiss="modal"><i class="fa fa-times"></i> Tutup</button>
          <button type="button" class="btn bg-gradient-primary saveModal"><i class="fa fa-save"></i> Save</button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import MiniCards from "./components/MiniCards.vue";
// import $ from "jquery";

export default {
  name: "dashboard-default",
  components: {
    MiniCards,
  },
  data() {
    return {
      profil_lengkap: "tidak",
      survey_lengkap: "ya",
    };
  },
  mounted() {
    // window.location.href = "/form_profile";
    // $("#modalDokumen").addClass("show");
    // $(".modal").css("display", "block");
    // $(".closeModal").click(function () {
    //   $("#modalDokumen").removeClass("show");
    //   $(".modal").css("display", "none");
    // });
    // $(".saveModal").click(function () {
    // });
  },
};
</script>
