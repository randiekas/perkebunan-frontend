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
            this.crud.apiData               = `/v1/api/data/perusahaan_penyelesaian_hat/id_perusahaan/${this.id_perusahaan}?field1=triwulan&value1=${this.triwulan}`
            this.crud.headers[0].default    = this.triwulan
        }
    },
    data(){
        return {
            crud: {
                title: "HAT",
                subtitle: "Penyelesaian Hak Atas Tanah",
                apiData: `/v1/api/data/perusahaan_penyelesaian_hat/id_perusahaan/${this.id_perusahaan}?field1=triwulan&value1=${this.triwulan}`,
                apiTambah: `/v1/api/tambah/perusahaan_penyelesaian_hat?id_perusahaan=${this.id_perusahaan}`,
                apiUbah: `/v1/api/ubah/perusahaan_penyelesaian_hat`,
                apiHapus: `/v1/api/hapus/perusahaan_penyelesaian_hat`,

                headers: [
                    { 
                        value: "triwulan",
                        default: this.triwulan,
                        type:'hidden',
                        table:false
                    }, 
                    {
                        text: 'Proses',
                        value: 'proses',
                        info: ['Contoh : Pembebasan Lahan (dari kawasan hutan)']
                    }, 
                    {
                        text: 'Triwulan Lalu',
                        value: 'triwulan_lalu',
                        type: 'number',
                        info: ['Contoh : satuan dalam HA'],
                    }, 
                    {
                        text: 'Triwulan Ini',
                        value: 'triwulan_ini',
                        type: 'number',
                        info: ['Contoh : satuan dalam HA'],
                    }, 
                    {
                        text: 'S/D Saat ini',
                        value: 'sd_sekarang',
                        type: 'number',
                        info: ['Contoh : satuan dalam HA'],
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