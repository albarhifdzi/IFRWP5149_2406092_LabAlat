Elemen                      SIA-UC03 — Ajukan KRS
Tujuan                      Menghasilkan pengajuan KRS yang tersimpan
Aktor utama                 Mahasiswa
Sumber kebutuhan            SIA-R03 dan SIA-R04
Pemicu                      Mahasiswa memilih fungsi pengajuan KRS
Prasyarat                   Mahasiswa telah terautentikasi; data mata kuliah tersedia
Pascakondisi berhasil       Pengajuan tersimpan dengan status Menunggu persetujuan
Pascakondisi gagal          Tidak ada pengajuan baru yang berhasil tersimpan
Include                     SIA-UC04 — Validasi KRS
Extension point             Konfirmasi Pengajuan
Extend                      SIA-UC05 jika [mahasiswa memilih cetak]