# **ESP8266 OTA**

## Persyaratan

- [Visual Studio Code](https://code.visualstudio.com/) Sebagai Code Editor
- [Ekstensi PlatformIO](https://platformio.org/install/ide?install=vscode) Sebagai Firmware Project Management
- [Minimum System ESP8266](https://github.com/B401-Robotics/wortel-firmware/tree/d97f6dfef85b5bb57e3d870195ed629ec6796cab/hardware) Sebagai Minimum System
- [Basic C/C++ Programming](https://www.geeksforgeeks.org/cpp-programming-basics/) Sebagai ilmu dasar pemrograman

## Pemrograman

Silahkan mengubah program sesuai dengan `Comment Block` yang telah disediakan pada [Source Code](https://github.com/B401-Robotics/wortel-firmware/blob/d97f6dfef85b5bb57e3d870195ed629ec6796cab/firmware/src/main.cpp)

Contoh penggunaan program yang benar

```
/* USER CODE BEGIN 1 */
pinMode(2, OUTPUT);
/* USER CODE END 1 */

/* USER CODE BEGIN 4 */
digitalWrite(2, HIGH);
/* USER CODE END 4 */
```

Contoh penggunaan program yang salah (Program diletakkan diluar `Comment Block`)

```
/* USER CODE BEGIN 1 */
pinMode(2, OUTPUT);
/* USER CODE END 1 */
pinMode(3, OUTPUT);
```

## Upload

1. Silahkan ubah ssid nama kelompok terlebih dahulu yang terletak pada definisi `AP_SSID`

```
#define AP_SSID "Kelompok_6969"
```

2. Compile program menggunakan PlatformIO (`Ctrl` + `Alt` + `B`)
3. Masuk ke Bootloader ESP32 dengan menggunakan Timing diaragam sebagai berikut: `(Kedua tombol di pull-up)`  
   ![Timing Diagram](../images/Timing_diagram1.jpeg)

   ```
   Cara melakukannya dengan menahan tombol boot dan menekan satu kali tombol reset.
   ```

4. Upload program menggunakan PlatformIO ( `Ctrl` + `Alt` + `U` )
5. Jika led yang terletak pada pojok board (dekat IC ESP8266) masih belum berkedip, maka silahkan tekan tombol reset sekali saja

## Wiring ESP dengan USB-TTL

![Wiring](../images/wiring.png)

## Upload OTA

1. Masuk ke web OTA
2. Klik tombol "Select File"
3. Silahkan pilih firmware.bin yang terletak pada ${direktori project anda}/.pio/build/[board]/firmware.bin
4. Tunggu sampai sukses

## Cara mengubah warna led RGB

Value yang bisa diubah terletak pada:

```
uint8_t led_color_rgb[3] = {0, 0, 0};
```

Bisa diubah menjadi

```
uint8_t led_color_rgb[3] = {69, 69, 69};
```

Jangan lupa untuk memanggil fungsi `set_led_color()` seperti yang telah anda kerjakan di Tugas Pendahuluan
