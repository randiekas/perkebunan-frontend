<template>
    <div>
        <Crud
			:crud="crud"/>
    </div>
</template>
<script>
export default {
    props: ['id_perusahaan', 'triwulan'],
    watch:{
        triwulan: function(){
            this.crud.apiData               = `/v1/api/data/perusahaan_pembangunan_pabrik/id_perusahaan/${this.id_perusahaan}?field1=triwulan&value1=${this.triwulan}`
            this.crud.headers[0].default    = this.triwulan
        }
    },
    data(){
        return {
            crud: {
                title: "Pembangunan Pabrik",
                subtitle: "Kelola data Rencana Dan Realisasi Pembangunan Pabrik",
                apiData: `/v1/api/data/perusahaan_pembangunan_pabrik/id_perusahaan/${this.id_perusahaan}?field1=triwulan&value1=${this.triwulan}`,
                apiTambah: `/v1/api/tambah/perusahaan_pembangunan_pabrik?id_perusahaan=${this.id_perusahaan}`,
                apiUbah: `/v1/api/ubah/perusahaan_pembangunan_pabrik`,
                apiHapus: `/v1/api/hapus/perusahaan_pembangunan_pabrik`,

                headers: [ 
                    { 
                        value: "triwulan",
                        default: this.triwulan,
                        type:'hidden',
                        table:false
                    }, 
                    {
                        text: 'Tipe',
                        value: 'tipe',
                        type:'radio',
                        options: [
                            {
                                label: 'Pabrik',
                                value: 'Pabrik',
                            },
                            {
                                label: 'Jenis',
                                value: 'Jenis',
                            },
                        ],
                    }, 
                    {
                        text: 'Uraian',
                        value: 'uraian',
                        info: ['Contoh : Jumlah (Unit), Kapasitas Ijin, Kapasitas Terpasang']
                    }, 
                    {
                        text: 'Rencana',
                        value: 'rencana',
                        type: 'number',
                    }, 
                    {
                        text: 'Realisasi',
                        value: 'realisasi',
                        type: 'number',
                    }, 
                    {
                        text: 'Keterangan',
                        value: 'keterangan',
                        type: 'textarea',
                    }, 
                    {
                        text: 'Aksi',
                        value: 'aksi',
                        form: false
                    }
                ],
            },
            data:[]
        }
    },
}
</script>