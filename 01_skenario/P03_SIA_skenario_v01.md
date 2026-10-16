Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap pengajuan menjalankan validasi KRS yang memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil, sistem menyimpan pengajuan berstatus menunggu persetujuan dosen wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRSdan memberikan catatan keputusan.

| ID Kebutuhan | Deskripsi Kebutuhan                                                        |
|--------------|----------------------------------------------------------------------------|
| SIA-R01      | Mahasiswa dapat melihat jadwal kuliah.                                     |
| SIA-R02      | Admin akademik dapat mengelola jadwal kuliah.                              |
| SIA-R03      | Mahasiswa dapat mengajukan KRS.                                            |
| SIA-R04      | Sistem memvalidasi KRS sebagai bagian dari pengajuan.                      |
| SIA-R05      | Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan. |
| SIA-R06      | Dosen wali dapat memproses persetujuan atau penolakan KRS.                 |

Batas dan asumsi:
• Pengguna telah terautentikasi.
• Data mata kuliah, prasyarat, dan jadwal tersedia.
• Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
• Unduh bukti tidak menjadi syarat keberhasilan pengajuan.
• KRS tersimpan belum berarti disetujui.
• Pembayaran, pengisian nilai, dan implementasi basis data berada di luar tugas.


| Aktor              | Tujuan terhadap sistem                                                   |
|--------------------|---------------------------------------------------------------------------|
| Mahasiswa          | Memilih mata kuliah, mengajukan KRS, dan memilih untuk mengunduh bukti    |
|                    | pengajuan.                                                                |
| Dosen wali         | Menyetujui atau menolak KRS dan memberikan catatan keputusan.             |



| ID       | Nama use case                  | Peran dalam model                         |
|----------|--------------------------------|-------------------------------------------|
| SIA-UC01 | Lihat jadwal kuliah            | Fungsi utama mahasiswa                    |
| SIA-UC02 | Kelola jadwal kuliah           | Fungsi utama admin akademik               |
| SIA-UC03 | Ajukan KRS                     | Fungsi utama mahasiswa                    |
| SIA-UC04 | Validasi KRS                   | Perilaku yang disertakan UC03             |
| SIA-UC05 | Unduh bukti pengajuan KRS      | Tambahan bersyarat pada UC03              |
| SIA-UC06 | Proses keputusan KRS           | Fungsi utama dosen wali                   |

Validasi KRS menjadi bagian dari pengajuan karena sistem harus memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal sebelum pengajuan berhasil disimpan. 
Unduh bukti pengajuan merupakan fungsi tambahan karena mahasiswa dapat memilihnya saat konfirmasi, tetapi pengajuan tetap berhasil tanpa mengunduh bukti.

Tetapkan relasi
**1. SIA-UC03 «include» SIA-UC04**

Sumber: SIA-R03 dan SIA-R04.
Tujuan: Menghubungkan pengajuan KRS dengan proses validasi KRS.
Alasan: Validasi merupakan bagian wajib dari alur pengajuan. Jika validasi gagal, pengajuan belum berhasil tersimpan.

**2. SIA-UC05 «extend» SIA-UC03**

Sumber: SIA-R05.
Tujuan: Menambahkan perilaku unduh bukti secara opsional pada pengajuan KRS.
Extension point: Konfirmasi penyimpanan pengajuan.
Kondisi: [mahasiswa memilih unduh bukti].
Alasan: Pengajuan tetap berhasil tanpa mengunduh bukti.
Catatan: SIA-UC06 mencakup persetujuan atau penolakan KRS beserta catatan keputusan oleh dosen wali. Admin akademik tidak ditambahkan ke proses pengajuan KRS karena perannya dalam skenario ini tidak disebutkan.

