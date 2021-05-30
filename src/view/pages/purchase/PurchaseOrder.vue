<template>
    <div>
        <div class="card card-custom gutter-b">
            <div class="card-header flex-wrap">
                <div class="card-title">
                    <h3 class="card-label">Transaksi Order Pembelian</h3>
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
                    <a href="#" class="btn btn-primary font-weight-bolder" @click="showModalAdd($event.target)">
                    <span class="svg-icon svg-icon-md">
                        <i class="menu-icon flaticon-add-circular-button"></i>
                    </span>Tambah</a>
                    <b-modal centered scrollable size="xl" hide-footer :id="addModal.id" :title="addModal.title" @hide="resetAddModal">
                        <form class="form">
                            <div class="card-body p-0">
                                <div class="form-group row mb-1">
                                    <div class="col-lg-4">
                                        <label>Kode Cabang:</label>
                                        <input type="text" class="form-control form-control-sm" placeholder="Kode Cabang"/>
                                        <!-- <span class="form-text text-danger">Please enter your full name</span> -->
                                    </div>
                                    <div class="col-lg-4">
                                        <label>Nama Cabang:</label>
                                        <input type="text" class="form-control form-control-sm" placeholder="Nama Cabang"/>
                                    </div>
                                    <div class="col-lg-4">
                                        <label>Jenis Transaksi:</label>
                                        <div class="row">
                                            <div class="col-sm-4">
                                                <select class="form-control form-control-sm">
                                                    <option value="">Pilih Jenis Transaksi</option>
                                                    <option value="Insidentil">Insidentil</option>
                                                </select>
                                            </div>
                                            <div class="col-sm-8">
                                                <input type="text" class="form-control form-control-sm" placeholder="Jenis Transaksi"/>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                                <div class="form-group row mb-1">
                                    <div class="col-lg-3">
                                        <label>Tgl OP:</label>
                                        <input type="date" class="form-control form-control-sm" placeholder="Tgl OP"/>
                                    </div>
                                    <div class="col-lg-3">
                                        <label>No OP:</label>
                                        <input type="text" class="form-control form-control-sm" placeholder="No OP"/>
                                    </div>
                                    <div class="col-lg-3">
                                        <label>Tgl Est Serah:</label>
                                        <input type="date" class="form-control form-control-sm" placeholder="Tgl Est Serah"/>
                                    </div>
                                    <div class="col-lg-3">
                                        <label>Mata Uang:</label>
                                        <select class="form-control form-control-sm">
                                            <option value="">Pilih Mata Uang</option>
                                            <option value="Rp">Rp</option>
                                        </select>
                                    </div>
                                </div>
                                <div class="form-group row mb-1">
                                    <div class="col-lg-6">
                                        <label>Kode Supplier:</label>
                                        <input type="text" class="form-control form-control-sm" placeholder="Kode Supplier"/>
                                    </div>
                                    <div class="col-lg-6">
                                        <label>Nama Supplier:</label>
                                        <input type="text" class="form-control form-control-sm" placeholder="Nama Supplier"/>
                                    </div>
                                </div>
                                <div class="form-group row mb-1">
                                    <div class="col-lg-8">
                                        <label>Nomor Persetujuan PP:</label>
                                        <input type="text" class="form-control form-control-sm" placeholder="Nomor Persetujuan PP"/>
                                    </div>
                                    <div class="col-lg-4">
                                        <label>TOP:</label>
                                        <div class="input-group input-group-sm">
                                            <input type="text" class="form-control form-control-sm" placeholder="TOP">
                                            <div class="input-group-append">
                                                <span class="input-group-text">Hari</span>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                                <div class="form-group">
                                    <label for="exampleTextarea">Catatan</label>
                                    <textarea class="form-control form-control-sm" rows="3" placeholder="Catatan"></textarea>
                                </div>
                            </div>
                            <div class="card-footer text-center p-2">
                                <button type="button" class="btn btn-sm btn-primary mr-2">Tambah</button>
                                <button type="button" class="btn btn-sm btn-info mr-2">Ubah</button>
                                <button type="button" class="btn btn-sm btn-danger mr-2">Hapus</button>
                                <button type="button" class="btn btn-sm btn-success mr-2">Cari</button>
                                <button type="button" class="btn btn-sm btn-warning mr-2">Print</button>
                                <button type="button" class="btn btn-sm btn-secondary" @click="$bvModal.hide('add-modal')">Keluar</button>
                            </div>
                        </form>

                        <div>
                            <fieldset>
                                <legend>Daftar Order Pembelian</legend>
                                <b-table striped hover bordered small
                                    :fields="barangfields"
                                    :items="barangs"></b-table>
                            </fieldset>
                        </div>
                    </b-modal>
                </div>
            </div>
            <div class="card-body">
                <form class="form">
                    <div class="card-body p-0">
                        <div class="form-group row mb-1">
                            <div class="col-lg-4">
                                <label>Kode Cabang:</label>
                                <input type="text" class="form-control form-control-sm" placeholder="Kode Cabang"/>
                                <!-- <span class="form-text text-danger">Please enter your full name</span> -->
                            </div>
                            <div class="col-lg-4">
                                <label>Nama Cabang:</label>
                                <input type="text" class="form-control form-control-sm" placeholder="Nama Cabang"/>
                            </div>
                            <div class="col-lg-4">
                                <label>Jenis Transaksi:</label>
                                <div class="row">
                                    <div class="col-sm-4">
                                        <select class="form-control form-control-sm">
                                            <option value="">Pilih Jenis Transaksi</option>
                                            <option value="Insidentil">Insidentil</option>
                                        </select>
                                    </div>
                                    <div class="col-sm-8">
                                        <input type="text" class="form-control form-control-sm" placeholder="Jenis Transaksi"/>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="form-group row mb-1">
                            <div class="col-lg-3">
                                <label>Tgl OP:</label>
                                <input type="date" class="form-control form-control-sm" placeholder="Tgl OP"/>
                            </div>
                            <div class="col-lg-3">
                                <label>No OP:</label>
                                <input type="text" class="form-control form-control-sm" placeholder="No OP"/>
                            </div>
                            <div class="col-lg-3">
                                <label>Tgl Est Serah:</label>
                                <input type="date" class="form-control form-control-sm" placeholder="Tgl Est Serah"/>
                            </div>
                            <div class="col-lg-3">
                                <label>Mata Uang:</label>
                                <select class="form-control form-control-sm">
                                    <option value="">Pilih Mata Uang</option>
                                    <option value="Rp">Rp</option>
                                </select>
                            </div>
                        </div>
                        <div class="form-group row mb-1">
                            <div class="col-lg-6">
                                <label>Kode Supplier:</label>
                                <input type="text" class="form-control form-control-sm" placeholder="Kode Supplier"/>
                            </div>
                            <div class="col-lg-6">
                                <label>Nama Supplier:</label>
                                <input type="text" class="form-control form-control-sm" placeholder="Nama Supplier"/>
                            </div>
                        </div>
                        <div class="form-group row mb-1">
                            <div class="col-lg-8">
                                <label>Nomor Persetujuan PP:</label>
                                <input type="text" class="form-control form-control-sm" placeholder="Nomor Persetujuan PP"/>
                            </div>
                            <div class="col-lg-4">
                                <label>TOP:</label>
                                <div class="input-group input-group-sm">
                                    <input type="text" class="form-control form-control-sm" placeholder="TOP">
                                    <div class="input-group-append">
                                        <span class="input-group-text">Hari</span>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="form-group">
                            <label for="exampleTextarea">Catatan</label>
                            <textarea class="form-control form-control-sm" rows="3" placeholder="Catatan"></textarea>
                        </div>
                    </div>
                    <div class="card-footer text-center p-2">
                        <button type="button" class="btn btn-sm btn-primary mr-2">Tambah</button>
                        <button type="button" class="btn btn-sm btn-info mr-2">Ubah</button>
                        <button type="button" class="btn btn-sm btn-danger mr-2">Hapus</button>
                        <button type="button" class="btn btn-sm btn-success mr-2">Cari</button>
                        <button type="button" class="btn btn-sm btn-warning mr-2">Print</button>
                        <button type="button" class="btn btn-sm btn-secondary" @click="$bvModal.hide('add-modal')">Keluar</button>
                    </div>
                </form>

                <div>
                    <fieldset>
                        <legend>Daftar Order Pembelian</legend>
                        <b-table striped hover bordered small
                            :fields="barangfields"
                            :items="barangs"></b-table>
                    </fieldset>
                </div>

                <!-- <b-row> 
                    <b-col lg="6" md="6" sm="12" class="my-1"></b-col>
                    <b-col lg="6" md="6" sm="12" class="my-1">
                        <b-form-group
                            label=""
                            label-for="filter-input"
                            label-cols-sm="3"
                            label-align-sm="right"
                            label-size="sm"
                            class="mb-1"
                        >
                            <b-input-group size="sm">
                                <b-form-input
                                id="filter-input"
                                v-model="filter"
                                type="search"
                                placeholder="Type to Search"
                                ></b-form-input>

                                <b-input-group-append>
                                    <b-button :disabled="!filter" @click="filter = ''" variant="primary">Clear</b-button>
                                </b-input-group-append>
                            </b-input-group>
                        </b-form-group>
                    </b-col>
                </b-row>

                <b-table
                    :items="items"
                    :fields="fields"
                    :current-page="currentPage"
                    :per-page="perPage"
                    :filter="filter"
                    :filter-included-fields="filterOn"
                    :sort-by.sync="sortBy"
                    :sort-desc.sync="sortDesc"
                    :sort-direction="sortDirection"
                    :busy="isBusy"
                    :sticky-header="stickyHeader"
                    stacked="md"
                    head-variant="dark"
                    outlined
                    show-empty
                    small
                    responsive
                    @filtered="onFiltered"
                    :select-mode="selectMode"
                    ref="selectableTable"
                    selectable
                    @row-selected="onRowSelected"
                >
                    <template #head(selected)>
                        <span v-if="selectedAll" @click="clearSelected"><i class="la la-check-square-o"></i></span>
                        <span v-else @click="selectAllRows"><i class="la la-square-o"></i></span>
                    </template>

                    <template #cell(selected)="{ rowSelected }">
                        <template v-if="rowSelected">
                            <span aria-hidden="true"><i class="la la-check-square-o"></i></span>
                            <span class="sr-only">Selected</span>
                        </template>
                        <template v-else>
                            <span aria-hidden="true"><i class="la la-square-o"></i></span>
                            <span class="sr-only">Not selected</span>
                        </template>
                    </template>

                    <template #cell(name)="row">
                        {{ row.value.first }} {{ row.value.last }}
                    </template>

                    <template #cell(actions)="row">
                        <button class="btn btn-sm btn-clean btn-icon" title="Info details" @click="info(row.item, row.index, $event.target)">
                            <i class="la la-info-circle"></i>
                        </button>
                        <button class="btn btn-sm btn-clean btn-icon" title="Info details" @click="row.toggleDetails">
                            <i v-if="row.detailsShowing" class="la la-eye-slash"></i>
                            <i v-else class="la la-eye"></i>
                        </button>
                    </template>

                    <template #row-details="row">
                        <b-card>
                            <ul>
                                <li v-for="(value, key) in row.item" :key="key">{{ key }}: {{ value }}</li>
                            </ul>
                        </b-card>
                    </template>
                </b-table>

                <b-row>
                    <b-col lg="3" md="3" sm="12">
                        <b-dropdown size="sm" variant="primary">
                            <template #button-content>
                                {{perPage}}
                            </template>
                            <b-dropdown-item-button v-for="item in pageOptions" :key="item" style="width: auto" @click="onChangePage(item)">{{item}}</b-dropdown-item-button>
                        </b-dropdown>
                    </b-col>
                    <b-col lg="9" md="9" sm="12">
                        <b-pagination
                            v-model="currentPage"
                            :total-rows="totalRows"
                            :per-page="perPage"
                            align="right"
                            size="md"
                            class="my-0"
                            ></b-pagination>
                    </b-col>
                </b-row> -->

                <!-- Info modal -->
                <b-modal centered scrollable size="xl" :id="infoModal.id" :title="infoModal.title" ok-only @hide="resetInfoModal">
                    <!-- <pre>{{ infoModal.content }}</pre> -->
                    <form class="form">
                        <div class="card-body p-0">
                            <div class="form-group row mb-1">
                                <div class="col-lg-4">
                                    <label>Kode Gudang:</label>
                                    <input type="text" class="form-control" placeholder="Kode Gudang"/>
                                    <!-- <span class="form-text text-danger">Please enter your full name</span> -->
                                </div>
                                <div class="col-lg-4">
                                    <label>Nama Gudang:</label>
                                    <input type="text" class="form-control" placeholder="Nama Gudang"/>
                                </div>
                                <div class="col-lg-4">
                                    <label>Jenis Transaksi:</label>
                                    <input type="text" class="form-control" placeholder="Jenis Transaksi"/>
                                </div>
                            </div>
                            <div class="form-group row mb-1">
                                <div class="col-lg-4">
                                    <label>Tgl PP:</label>
                                    <input type="date" class="form-control" placeholder="Tgl PP"/>
                                </div>
                                <div class="col-lg-4">
                                    <label>No PP:</label>
                                    <input type="text" class="form-control" placeholder="No PP"/>
                                </div>
                                <div class="col-lg-4">
                                    <label>Kategori Permintaan:</label>
                                    <select class="form-control">
                                        <option value="">Pilih Kategori Permintaan</option>
                                        <option value="Insidentil">Insidentil</option>
                                    </select>
                                </div>
                            </div>
                            <div class="form-group row mb-1">
                                <div class="col-lg-4">
                                    <label>Kode Keperluan:</label>
                                    <input type="text" class="form-control" placeholder="Kode Keperluan"/>
                                </div>
                                <div class="col-lg-4">
                                    <label>Nama Keperluan:</label>
                                    <input type="text" class="form-control" placeholder="Nama Keperluan"/>
                                </div>
                                <div class="col-lg-4">
                                    <label>Sifat Permintaan:</label>
                                    <select class="form-control">
                                        <option value="">Pilih Sifat Permintaan</option>
                                        <option value="Normal">Normal</option>
                                    </select>
                                </div>
                            </div>
                            <div class="form-group row">
                                <div class="col-lg-12">
                                    <label for="exampleTextarea">Catatan</label>
                                    <textarea class="form-control" rows="3" placeholder="Catatan"></textarea>
                                </div>
                            </div>
                        </div>
                        <div class="card-footer text-center p-2">
                            <button type="button" class="btn btn-sm btn-primary mr-2">Tambah</button>
                            <button type="button" class="btn btn-sm btn-info mr-2">Ubah</button>
                            <button type="button" class="btn btn-sm btn-danger mr-2">Hapus</button>
                            <button type="button" class="btn btn-sm btn-success mr-2">Cari</button>
                            <button type="button" class="btn btn-sm btn-warning mr-2">Print</button>
                            <button type="button" class="btn btn-sm btn-secondary" @click="$bvModal.hide('add-modal')">Keluar</button>
                        </div>
                    </form>

                    <div>
                        <b-table striped hover bordered small
                            :fields="barangfields"
                            :items="barangs"></b-table>
                    </div>

                    <div>
                        <fieldset>
                            <legend>Daftar Permintaan Pembelian</legend>
                            <b-table striped hover bordered small
                                :fields="barangfields"
                                :items="barangs"></b-table>
                        </fieldset>
                    </div>
                </b-modal>
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
    .table.b-table > tbody > .table-active, .table.b-table > tbody > .table-active > th, .table.b-table > tbody > .table-active > td{
        background-color: #F3F6F9;
    }

    fieldset{
        min-width: 0;
        padding: 0px 5px;
        margin-bottom: 10px;
        border: 1px solid #ebedf3;
    }

    legend{
        display: block;
        width: auto;
        max-width: 100%;
        margin-bottom: 0px;
        padding: 5px;
        font-size: 14px;
        line-height: inherit;
        white-space: normal;
    }
</style>

<script>
// import KTDefaultDatatable from "@/assets/js/layout/extended/ktdatatable.js";
import { SET_BREADCRUMB } from "@/core/services/store/breadcrumbs.module";

export default {
    data() {
        return {
            form: {
                email: "",
                name: "",
                food: null,
                checked: []
            },
            foods: [
                { text: "Select One", value: null },
                "Carrots",
                "Beans",
                "Tomatoes",
                "Corn"
            ],
            items: [
                { isActive: true, age: 40, name: { first: 'Dickerson', last: 'Macdonald' } },
                { isActive: false, age: 21, name: { first: 'Larsen', last: 'Shaw' } },
                {
                    isActive: false,
                    age: 9,
                    name: { first: 'Mini', last: 'Navarro' }
                },
                { isActive: false, age: 89, name: { first: 'Geneva', last: 'Wilson' } },
                { isActive: true, age: 38, name: { first: 'Jami', last: 'Carney' } },
                { isActive: false, age: 27, name: { first: 'Essie K', last: 'Dunlap' } },
                { isActive: false, age: 21, name: { first: 'Essie U', last: 'Dunlap 1' } },
                { isActive: false, age: 23, name: { first: 'Essie I', last: 'Dunlap 2' } },
                { isActive: false, age: 24, name: { first: 'Essie L', last: 'Dunlap 3' } },
                { isActive: false, age: 23, name: { first: 'Essie K', last: 'Dunlap 4' } },
                { isActive: false, age: 26, name: { first: 'Essie N', last: 'Dunlap 5' } },
                { isActive: false, age: 27, name: { first: 'Essie E', last: 'Dunlap 6' } },
                { isActive: false, age: 21, name: { first: 'Essie D', last: 'Dunlap 6' } },
                { isActive: false, age: 29, name: { first: 'Essie B', last: 'Dunlap 7' } },
                { isActive: true, age: 40, name: { first: 'Thor', last: 'Macdonald' } },
                {
                    isActive: true,
                    age: 87,
                    name: { first: 'Larsen', last: 'Shaw' }
                },
                { isActive: false, age: 26, name: { first: 'Mitzi', last: 'Navarro' } },
                { isActive: false, age: 22, name: { first: 'Genevieve', last: 'Wilson' } },
                { isActive: true, age: 38, name: { first: 'John', last: 'Carney' } },
                { isActive: false, age: 29, name: { first: 'Dick', last: 'Dunlap' } }
            ],
            fields: [
                { key: 'selected', label: '', class: 'text-center' },
                { key: 'name', label: 'Person full name', sortable: true, sortDirection: 'desc' },
                { key: 'age', label: 'Person age', sortable: true, class: 'text-center' },
                {
                    key: 'isActive',
                    label: 'Is Active',
                    formatter: (value) => {
                        return value ? 'Yes' : 'No'
                    },
                    sortable: true,
                    sortByFormatted: true,
                    filterByFormatted: true
                },
                { key: 'actions', label: 'Actions', class: 'text-center' }
            ],
            barangs: [
                { kode_barang: '11223438-9', nama_barang: 'Jasa Pebaikan Kendaraan', jumlah : 10, jumlah_nop : 0, jumlah_op : 10, kode_satuan: 'Pcs', price:1000000, value:1000000},
            ],
            barangfields: [
                { key: 'kode_barang', label: 'Kode Barang' },
                { key: 'nama_barang', label: 'Nama Barang' },
                { key: 'jumlah', label: 'Jumlah (Setuju)', class: 'text-right' },
                { key: 'jumlah_nop', label: 'Jumlah (Belum OP)', class: 'text-right' },
                { key: 'kode_satuan', label: 'Satuan', class: 'text-center' },
                { key: 'jumlah_op', label: 'Jumlah (OP)', class: 'text-right' },
                { key: 'price', label: 'Harga Satuan', class: 'text-right' },
                { key: 'value', label: 'Nilai', class: 'text-right' },
            ],
            stickyHeader : true,
            isBusy: false,
            totalRows: 1,
            currentPage: 1,
            perPage: 10,
            pageOptions: [10, 20],
            sortBy: '',
            sortDesc: false,
            sortDirection: 'asc',
            filter: null,
            filterOn: [],
            infoModal: {
                id: 'info-modal',
                title: '',
                content: ''
            },
            addModal: {
                id: 'add-modal',
                title: '',
                content: ''
            },
            selectMode: 'multi',
            selected: [],
            selectedAll:false,
            url: 'http://ebhr.test/api/employees'
        }
    },
    components: {

    },
    computed: {
      sortOptions() {
        // Create an options list from our fields
        return this.fields
          .filter(f => f.sortable)
          .map(f => {
            return { text: f.label, value: f.key }
          })
      }
    },
    mounted() {
        // KTDefaultDatatable.init("kt_datatable");
        this.$store.dispatch(SET_BREADCRUMB, [
            { title: "Purchase" },
            { title: "Order Pembelian" }
        ]);

        // Set the initial number of items
        this.totalRows = this.items.length
    },
    created () {
        document.title = 'EBS | Order Pembelian';
    },
    methods:{
        showModalAdd(button) {
            this.addModal.title = 'Tambah Order Pembelian'
            this.addModal.content = ''
            this.$root.$emit('bv::show::modal', this.addModal.id, button)
        },
        resetAddModal(){
            
        },
        info(item, index, button) {
            this.infoModal.title = `Row index: ${index}`
            this.infoModal.content = JSON.stringify(item, null, 2)
            this.$root.$emit('bv::show::modal', this.infoModal.id, button)
        },
        resetInfoModal() {
            this.infoModal.title = ''
            this.infoModal.content = ''
        },
        onFiltered(filteredItems) {
            // Trigger pagination to update the number of buttons/pages due to filtering
            this.totalRows = filteredItems.length
            this.currentPage = 1
        },
        onChangePage(page) {
            this.perPage = page
        },
        onRowSelected(items) {
            this.selected = items
        },
        selectAllRows() {
            this.$refs.selectableTable.selectAllRows()
            this.selectedAll = true;
        },
        clearSelected() {
            this.$refs.selectableTable.clearSelected()
            this.selectedAll = false;
        },
    }
};
</script>