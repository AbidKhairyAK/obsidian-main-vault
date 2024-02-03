### Catatan ngobrol dengan ilham
- flow ada di fsd
- lketika nggak ngerti nanya ke PM dan BA
- data untuk ditestingnya yang bingung
- BRD belum punya
- di dalam FSD ada specification dan flowchart
- problem ada 2
	- berkaitan dengan flow proses <= udah paham flow utamanya, cuma belum keseluruhan
	- berkaitan dengan jumlah / contoh data untuk melakukan proses pengujian
-  fsd ada banyak, dan versinya ada banyak
- tidak ada akses ke db
- ada 3 menu setiap menu ada beberapa submenu
- pengen resign karena terkait Task, Deadline, dan Data
- test scenario udah ada, tapi test data belum ada
- datanya jika sudah diapprove, sudah tidak bisa diulang, harus buat ulang lagi dari awal
- 20 field 1 sekolah
- tidak bisa mengisi semua data sesuai target


### Pertanyaan ke ibu linda
- data testing
	- belum 100% menguasai posisi QC
	- E2E testing tidak akan dilakukan jika datanya dicari, datanya harus dibikin
	- testingnya tidak mengikuti role yg ada
	- testing pakai administrator, padahal testnya harus pakai entity tertentu
	  
- fungsinya ilham seperti apa secara teknis?
	- qc aplikasi di salah satu customer
	- lagi assign project aplikasi branding di bengkel
	- nyimpan kontrak2 dari bengkel
	  
- project apa yang dipegang oleh ilham?
	- ilham harus memahami flow dari aplikasi
	- UAT script udah diberikan ke ilham
	- UAT script silahkan dikembangkan menjadi negatif test
	  
	- tugas penting ilham
		- ngebaca dokumen fsd dan pahami
		- pelajari UAT script
		- pelajari sisi aplikasi
		- testing
		  
	- project ini enhancement dari aplikasi yg udah ada
	- fitur baru, generate pdf dan penambahan status
	  
	- menyesuaikan konfigurasi ketika testing
		- salesmen type landing diubah ketika testing
		- menyesuaikan konfig 
		  
	- ada pm yg mendampingi
	  
- masalah ilham dari bu linda
	- saran dari dev
		- ilham artikulasinya buruk
		- ilham tuh kalo dikasih tau alasan errornya dia langsung menyimpulkan seolah2 paham, padahal tujuannya agar ilham paham
		- harusnya kalo nggak paham jangan pura2 paham
		- suka menyimpulkan sesuatu yang sebenernya dia nggak paham
		- kalo mas ilham merasa itu udah bug, jangan tanyakan lagi ke dev
		- list dulu pertanyaan sebelum ditanyakan ke developer
		- setim merasa ilham kebanyakan nanya dibandingkan kerjanya
		- komunikasinya udah jelimet
		  
	- ilham nggak bisa menjelaskan secara simple
	- max tanggal 7 sebelum replacement
	  
- apa yg bisa kita komunikasikan ke ilham, yg bagusnya melalui kita?
	- pahami dulu sebelum nanya, jadinya nggak banyak nanya
	- siapapun tidak bisa menolong ilham, jika dia tidak menolong dirinya sendiri
	- tidak bermaksud menjelekkan, tapi membantu agar bisa kerja
	  
- kalau bisa gali lebih banyak tentang teknisnya


### Solusi yang ditawarkan setelah ngobrol dengan ilham
- buat flow bisnis pribadi versi sendiri dijadiin kerjaan kantor
- pembuatan data testing menjadi kerjaan dia
- beri akses ke DB untuk mempersingkat proses testing (contoh inject data prerequisite untuk test yg flownya memerlukan penyelesaian proses yang lain)
- harus dipaksa nyatat, kalo bisa memang integrasi dengan culture kantornya klien