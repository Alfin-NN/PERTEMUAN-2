# PERTEMUAN-2
Bank Sampah

Karena 0.2 lebih kecil dari 0.5, kondisi tersebut terpenuhi (true), sehingga status yang tercetak adalah pesan gagal.

Jika ingin statusnya berhasil, ubah nilai input saat memanggil fungsinya menjadi 0.5 atau lebih besar (misal: cetakStatusSetoran(2.0)).

```dart
String cekValidasiSampah(String jenis) {
  if (jenis == "B3") {
    return "Sampah B3 berbahaya, tidak diterima";
  }
  if (jenis == "basah") {
    return "Sampah organik/basah harus dikeringkan dulu";
  }
  if (jenis == "kotor") {
    return "Sampah plastik kotor, bersihkan terlebih dahulu";
  }
  return "Sampah siap ditimbang";
}

void cetakPesanHarga(String jenis) {
  String keterangan = switch (jenis) {
    'plastik' => "Harga Rp3.000 per kg",
    'kertas' => "Harga Rp2.000 per kg",
    'logam' => "Harga Rp7.000 per kg",
    _ => "Jenis sampah tidak terdaftar",
  };
  print(keterangan);
}

void cetakStatusSetoran(double beratKg) {
  String status = "";
  if (beratKg < 0.5) {
    status = "Gagal: Minimal setoran sampah 0.5 kg";
  } else {
    status = "Setoran diterima, siap diproses";
  }
  print(status);
}

void cekPercobaanSetor(int totalSetoran) {
  switch (totalSetoran) {
    case 10:
      print("Selamat! Anda mendapatkan bonus poin nasabah teladan");
    case 5:
    case 6:
    case 7:
    case 8:
    case 9:
      print("Peringatan: Hampir mencapai batas bonus harian");
    default:
      print("Setoran berhasil dicatat");
  }
}

void main() {
  print("Sistem Bank Sampah");
  print(cekValidasiSampah("kotor"));
  cetakPesanHarga('plastik');
  cetakStatusSetoran(0.2);
  cekPercobaanSetor(10);
}
