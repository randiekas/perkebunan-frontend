<template>
    <div>
        <p class="subtitle-2">Pilih Form</p>
        <v-row class="mt-6">
			<v-col v-for="(item, index) in items" :key="index" sm="12" md="4">
				<v-card elevation="1" class="border--primary">
					<!-- <v-card-title class="pb-0">
                        
                    </v-card-title> -->
					<v-card-text>
                        <p class="subtitle-2"><v-icon left>{{ item.icon }}</v-icon> {{item.title}}</p>
					</v-card-text>
					
                    <v-card-actions>
						<v-spacer></v-spacer>
						<v-btn color="primary" text :to="`/apps/perusahaan/${id_perusahaan}${item.to}`">
							Buka
							<v-icon right dark>mdi-launch</v-icon>
						</v-btn>
					</v-card-actions> 
				</v-card>
			</v-col>
		</v-row>
    </div>
</template>
<script>
export default {
	props: ['id_perusahaan'],
    data: () => ({
        items: [
			{ title: 'Data Perusahaan', icon: 'mdi-view-dashboard', to:"/perusahaan" },
			{ title: 'Legalitas', icon: 'mdi-file', to:"/legalitas" },
			{ title: 'Lahan Pembibitan', icon: 'mdi-map-marker-multiple', to:"/pembibitan" },
			{ title: 'Penyelesaian HAT', icon: 'mdi-map-check-outline', to:"/penyelesaianhat" },
			{ title: 'Pembukaan Lahan', icon: 'mdi-map-check', to:"/pembukaan" },
			{ title: 'Penanaman Lahan', icon: 'mdi-map-clock', to:"/penanaman" },
			{ title: 'ANKT', icon: 'mdi-format-list-checkbox', to:"/ankt" },
			{ title: 'Lahan Gambut', icon: 'mdi-format-list-numbered', to:"/lahangambut" },
			{ title: 'Embung', icon: 'mdi-format-list-bulleted', to:"/embung" },
			{ title: 'Tenaga Kerja', icon: 'mdi-account-hard-hat', to:"/tenagakerja" },
			{ title: 'Pembangunan Pabrik', icon: 'mdi-hammer-wrench', to:"/pembangunanpabrik" },
			{ title: 'Kendali Kebakaran', icon: 'mdi-fire', to:"/kendalikebakaran" },
			{ title: 'Kendali OPT', icon: 'mdi-tower-fire', to:"/kendaliopt" },
			{ title: 'Sarana Produksi', icon: 'mdi-warehouse', to:"/saranaproduksi" },
			{ title: 'Alat Berat', icon: 'mdi-excavator', to:"/alatberat" },
			{ title: 'Prasarana Sosial', icon: 'mdi-charity', to:"/prasaranasosial" },
			{ title: 'Produksi', icon: 'mdi-hammer', to:"/produksi" },
			{ title: 'Pemasaran', icon: 'mdi-shopping', to:"/pemasaran" },
			{ title: 'Kerjasama Kemitraan', icon: 'mdi-handshake', to:"/kerjasamamitra" },
			{ title: 'Kemitraan Lainnya', icon: 'mdi-handshake-outline', to:"/kemitraanlainnya" },
			{ title: 'CSR', icon: 'mdi-gift', to:"/csr" },
			{ title: 'Permasalahan', icon: 'mdi-folder-alert', to:"/permasalahan" },
			{ title: 'Galeri', icon: 'mdi-image-multiple', to:"/galeri" },
			{ title: 'Konfirmasi Selesai', icon: 'mdi-check-all', to:"/konfirmasi" },
			{ title: 'Cetak Laporan', icon: 'mdi-printer', to:"/cetak" },
			{ title: 'Cetak Serah Terima', icon: 'mdi-printer-check', to:"/serahterima" },
        ],
    }),
}
</script>