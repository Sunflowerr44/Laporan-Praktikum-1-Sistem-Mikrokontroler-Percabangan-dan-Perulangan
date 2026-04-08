## Pertanyaan
4. Buatkan program agar LED menyala tiga LED kanan dan tiga LED kiri secara bergantian dan berikan penjelasan disetiap baris kode nya dalam bentuk README.md!

## Jawaban
Menggunakan 6 LED yang terhubung ke pin digital 2 sampai 7 pada Arduino Uno.  
LED dibagi menjadi dua kelompok:

- 3 LED kiri : pin 2, 3, 4
- 3 LED kanan : pin 5, 6, 7

## Kode Program

```cpp
int timer = 500; // waktu jeda antar pergantian LED

void setup() {
  // inisialisasi semua pin LED sebagai output
  for (int ledPin = 2; ledPin < 8; ledPin++) {
    pinMode(ledPin, OUTPUT);
  }
}

void loop() {
  // menyalakan 3 LED kiri (pin 2, 3, 4)
  for (int ledPin = 2; ledPin <= 4; ledPin++) {
    digitalWrite(ledPin, HIGH);
  }
  delay(timer);

  // mematikan 3 LED kiri
  for (int ledPin = 2; ledPin <= 4; ledPin++) {
    digitalWrite(ledPin, LOW);
  }
  delay(timer);

  // menyalakan 3 LED kanan (pin 5, 6, 7)
  for (int ledPin = 5; ledPin <= 7; ledPin++) {
    digitalWrite(ledPin, HIGH);
  }
  delay(timer);

  // mematikan 3 LED kanan
  for (int ledPin = 5; ledPin <= 7; ledPin++) {
    digitalWrite(ledPin, LOW);
  }
  delay(timer);
}

## Penjelasan Tiap Baris Kode

| No | Baris Kode | Penjelasan |
|----|------------|------------|
| 1 | `int timer = 500;` | Mendeklarasikan variabel `timer` dengan nilai 500 milidetik sebagai waktu jeda antar pergantian nyala LED. Nilai ini menentukan seberapa cepat atau lambat pola LED berganti. |
| 2 | `void setup() {` | Menandai awal fungsi `setup()`, yaitu fungsi yang hanya dijalankan satu kali saat Arduino pertama kali dinyalakan atau di-reset. |
| 3 | `for (int ledPin = 2; ledPin < 8; ledPin++) {` | Membuat perulangan untuk mengakses seluruh pin LED mulai dari pin 2 sampai pin 7 secara berurutan. |
| 4 | `pinMode(ledPin, OUTPUT);` | Mengatur setiap pin yang sedang diproses sebagai output agar dapat digunakan untuk mengirim sinyal HIGH atau LOW ke LED. |
| 5 | `void loop() {` | Menandai awal fungsi `loop()`, yaitu fungsi utama yang dijalankan berulang terus-menerus selama Arduino aktif. |
| 6 | `for (int ledPin = 2; ledPin <= 4; ledPin++) {` | Membuat perulangan untuk memilih tiga LED bagian kiri, yaitu LED yang terhubung pada pin 2, 3, dan 4. |
| 7 | `digitalWrite(ledPin, HIGH);` | Menyalakan LED pada pin yang sedang diproses, sehingga tiga LED kiri akan menyala satu per satu sangat cepat dan tampak menyala bersamaan. |
| 8 | `delay(timer);` | Memberikan jeda selama 500 milidetik agar tiga LED kiri tetap menyala sebelum dimatikan. |
| 9 | `for (int ledPin = 2; ledPin <= 4; ledPin++) {` | Membuat perulangan kembali untuk memproses tiga LED kiri yang akan dimatikan. |
| 10 | `digitalWrite(ledPin, LOW);` | Mematikan LED pada pin 2, 3, dan 4 sehingga kelompok LED kiri padam. |
| 11 | `delay(timer);` | Memberikan jeda setelah tiga LED kiri mati sebelum program berpindah ke kelompok LED kanan. |
| 12 | `for (int ledPin = 5; ledPin <= 7; ledPin++) {` | Membuat perulangan untuk memilih tiga LED bagian kanan, yaitu LED yang terhubung pada pin 5, 6, dan 7. |
| 13 | `digitalWrite(ledPin, HIGH);` | Menyalakan LED pada pin 5, 6, dan 7, sehingga tiga LED kanan tampak menyala secara bersamaan. |
| 14 | `delay(timer);` | Memberikan jeda selama 500 milidetik agar tiga LED kanan tetap menyala sebelum dimatikan. |
| 15 | `for (int ledPin = 5; ledPin <= 7; ledPin++) {` | Membuat perulangan kembali untuk memproses tiga LED kanan yang akan dimatikan. |
| 16 | `digitalWrite(ledPin, LOW);` | Mematikan LED pada pin 5, 6, dan 7 sehingga kelompok LED kanan padam. |
| 17 | `delay(timer);` | Memberikan jeda setelah tiga LED kanan mati sebelum program mengulang kembali dari awal pola nyala. |
