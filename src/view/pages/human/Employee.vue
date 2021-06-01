<template>
    <div>
        <div class="card card-custom gutter-b">
            <div class="card-header flex-wrap">
                <div class="card-title">
                    <h3 class="card-label">Data Karyawan</h3>
                </div>
                <div class="card-toolbar">
                    <b-dropdown
                        size="md"
                        variant="primary"
                        toggle-class="btn btn-light-primary font-weight-bolder mr-2"
                        text="Export"
                    >
                        <template #button-content>
                            <span class="svg-icon svg-icon-md">
                                <i class="menu-icon flaticon-file"></i>
                            </span>Export
                        </template>
                        <div class="navi navi-hover min-w-md-200px">
                            <b-dropdown-text tag="div" class="navi-header pb-1">
                                <span class="text-primary text-uppercase font-weight-bold">Choose an option</span>
                            </b-dropdown-text>
                            <b-dropdown-text tag="div" class="navi-item">
                                <a href="#" class="navi-link">
                                    <span class="navi-icon">
                                        <i class="la la-file-pdf-o"></i>
                                    </span>
                                    <span class="navi-text">PDF</span>
                                </a>
                            </b-dropdown-text>
                            <b-dropdown-text tag="div" class="navi-item">
                                <a href="#" class="navi-link">
                                    <span class="navi-icon">
                                        <i class="la la-file-text-o"></i>
                                    </span>
                                    <span class="navi-text">CSV</span>
                                </a>
                            </b-dropdown-text>
                            <b-dropdown-text tag="div" class="navi-item">
                                <a href="#" class="navi-link">
                                    <span class="navi-icon">
                                        <i class="la la-file-excel-o"></i>
                                    </span>
                                    <span class="navi-text">Excel</span>
                                </a>
                            </b-dropdown-text>
                        </div>
                    </b-dropdown>
                    <a href="javascript:;" class="btn btn-primary font-weight-bolder">
                    <span class="svg-icon svg-icon-md">
                        <i class="menu-icon flaticon-add-circular-button"></i>
                    </span>Tambah</a>
                </div>
            </div>
            <div class="card-body">
                <div class="row">
                    <div class="col-lg-9 col-xl-8">
                    </div>
                    <div class="col-lg-3 col-xl-4 mt-5 mt-lg-0">
                        <div class="input-icon">
                            <input type="text" class="form-control" placeholder="Search..." v-model="search" name="search">
                            <span>
                                <i class="flaticon2-search-1 text-muted"></i>
                            </span>
                        </div>
                    </div>
                </div>
                <div class="table-responsive">
                    <table class="table table-separate table-head-custom table-checkable kt_datatable1" id="kt_datatable1">
                        <thead>
                            <tr>
                                <th>ID</th>
                                <th>NIK</th>
                                <th>Name</th>
                                <th>Gender</th>
                                <th>Date of birth</th>
                                <th>Nationality</th>
                                <th>Actions</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="item in companies" :key="item.id">
                                <td>{{item.id}}</td>
                                <td>{{item.nik}}</td>
                                <td>{{item.name}}</td>
                                <td>{{item.gender.toUpperCase()}}</td>
                                <td>{{item.date_of_birth}}</td>
                                <td>{{item.nationality}}</td>
                                <td>
                                    <a href="javascript:;" class="btn btn-sm btn-clean btn-icon" title="Edit details">
                                        <i class="la la-edit"></i>
                                    </a>
                                    <a href="javascript:;" class="btn btn-sm btn-clean btn-icon" title="Delete">
                                        <i class="la la-trash"></i>
                                    </a>
                                </td>
                            </tr>
                            <tr v-if="companies.length == 0 && !loading">
                                <td colspan="7" class="text-center">No data available in table</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
                <div class="text-center" v-if="loading">
                    <b-spinner variant="primary" label="Text Centered"></b-spinner>
                </div>
                <div align="right">
                    <vue-pagination :data="companiesData" v-on:pagination-change-page="getCompanies" :limit="5"></vue-pagination>
                </div>
            </div>
        </div>
    </div>
</template>
<style lang="scss">
    .dropdown-menu {
        outline: none;
    }
    .b-dropdown-text {
        padding: 0;
    }
    .table th, .table td{
        vertical-align: middle;
    }
</style>
<script>

import ApiService from "@/core/services/api.service";
import { SET_BREADCRUMB } from "@/core/services/store/breadcrumbs.module";

export default {
    name:"Employee",
    data() {
        return{
            companies: [],
            companiesData: {},
            url: 'http://ebhr.test/api/employees',
            loading: true,
            search: ''
        }
    },
    components: {
        
    },
    watch: {
        search: function (q) {
            if (q != '') {
                this.searchCompany()  
            }else {
                this.getCompanies()
            }
        }
    },
    methods:{
        getCompanies(page) {
            if (typeof page === 'undefined') {
                page = 1;
            }
            var this_ = this
            this_.loading = true;
            this_.companies = []
            this_.companiesData = {}
            // ApiService.get(this_.url + '?page=' + page)
            ApiService.query("employees?page=" + page)
                .then(function (resp) {
                    // console.log(resp.data, this_.url + '?page=' + page)
                    this_.companies = resp.data.data;
                    this_.companiesData = resp.data;
                    this_.loading = false;
                    // this_.$forceUpdate();
                })
                .catch(function (resp) {
                    // console.log(resp);
                    this_.loading = false;
                    this_.makeToastVariant('danger','error','Could not load data')
                });
        },
        searchCompany(page){
            if (typeof page === 'undefined') {
                page = 1;
            }
            var this_ = this
            this_.loading = true;
            this_.companies = []
            ApiService.query(this_.url+'?q='+this_.search+'&page='+page)
            .then(function (resp) {
                this_.companies = resp.data.data;
                this_.companiesData = {};
                this_.loading = false;
                // this_.$forceUpdate();
            })
            .catch(function (resp) {
                // console.log(resp);
                this_.loading = false;
                this_.makeToastVariant('danger','error','Could not load data')
            });
        },
        makeToastVariant(variant = null,title,msg) {
            this.$bvToast.toast(msg, {
                title: title,
                variant: variant,
                solid: true
            });
        }
    },
    mounted() {
        this.$store.dispatch(SET_BREADCRUMB, [
            { title: "Human Resources", route: "employee" },
            { title: "Data Karyawan" }
        ]);
        this.getCompanies();
    },
    created () {
        document.title = 'EBS | Data Karyawan';
    },
};
</script>