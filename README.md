# rifqi_dhika_invation
/*
  tabel ASCII
Mencetak nilai byte dalam semua format yang memungkinkan:
* sebagai nilai biner mentah
* sebagai nilai desimal, heksadesimal, oktal, dan biner yang dikodekan ASCII
Untuk informasi lebih lanjut tentang ASCII, lihat http://www.asciitable.com dan http://en.wikipedia.org/wiki/ASCII
Sirkuit: Tidak diperlukan perangkat keras eksternal.
dibuat tahun 2024
oleh Rifqi Dhika Saputra
dimodifikasi 27 Juni 2024
oleh Rifqi Dhika Saputra
Contoh kode ini berada dalam domain publik.
<http://www.zambetti.com>
 */
batalkan  pengaturan () {
  // Inisialisasi serial dan tunggu port terbuka:
  Serial.mulai ( 9600 ) ;
  sementara (!Serial) {
    ; // tunggu port serial tersambung. Hanya diperlukan untuk port USB asli
  }

  // mencetak judul dengan jeda baris akhir
  Serial.println ( " Tabel ASCII ~ Peta Karakter " );
}

// karakter ASCII pertama yang terlihat '!' adalah nomor 33:
int byte ini = 33 ;
// Anda juga dapat menulis karakter ASCII dalam tanda kutip tunggal.
// Misalnya. '!' sama dengan 33, jadi Anda juga bisa menggunakan ini:
// int byte ini = '!';

 lingkaran kosong () {
  // mencetak nilai yang tidak diubah, yaitu versi biner mentah dari
  // byte. Monitor serial menafsirkan semua byte sebagai
  // ASCII, jadi 33, angka pertama, akan muncul sebagai '!'
  Serial.tulis ( thisByte );

  Serial.print ( " , dec: " ) ;
  // mencetak nilai sebagai string sebagai desimal berkode ASCII (basis 10).
  // Desimal adalah format default untuk Serial.print() dan Serial.println(),
  // jadi tidak diperlukan pengubah:
  Serial. cetak (Byte ini);
  // Tapi Anda bisa mendeklarasikan pengubah desimal jika Anda mau.
  // ini juga berfungsi jika Anda menghapus komentarnya:

  // Serial.print(Byte ini, DES);


  Serial.cetak ( " , hex: " ) ;
  // mencetak nilai sebagai string dalam heksadesimal (basis 16):
  Serial. cetak (Byte ini, HEX);

  Serial.cetak ( " , okt: " ) ;
  // mencetak nilai sebagai string dalam oktal (basis 8);
  Serial. cetak (thisByte, OCT);

  Serial. cetak ( " , tempat sampah : " );
  // mencetak nilai sebagai string dalam biner (basis 2)
  // juga mencetak jeda baris akhir:
  Serial. println (Byte ini, BIN);

  // jika karakter terakhir yang terlihat '~' atau 126 dicetak, hentikan:
  if (thisByte == 126 ) {     // Anda juga bisa menggunakan if (thisByte == '~') {
    // Loop ini terus berulang tanpa henti dan tidak melakukan apa pun
    sementara ( benar ) {
      melanjutkan ;
    }
  }
  // lanjutkan ke karakter berikutnya
  byte ini++;
}
