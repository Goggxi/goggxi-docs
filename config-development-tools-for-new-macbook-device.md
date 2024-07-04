# Flutter Config

Untuk mengelola berbagai versi Flutter di macOS, Anda bisa menggunakan alat bernama `fvm` (Flutter Version Management). FVM memudahkan pengelolaan beberapa versi Flutter dan pengalihan antar versi sesuai kebutuhan proyek. Berikut adalah langkah-langkah untuk menginstal dan menggunakan `fvm`:

### Langkah 1: Instalasi FVM

1. **Instalasi Homebrew** (jika belum terinstal):
   Jika Anda belum menginstal Homebrew, Anda bisa mengikuti langkah-langkah berikut untuk menginstalnya:
   ```sh
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. **Instalasi FVM**:
   Buka Terminal dan jalankan perintah berikut untuk menginstal `fvm` menggunakan Homebrew:
   ```sh
   brew tap leoafarias/fvm
   brew install fvm
   ```

### Langkah 2: Menginstal Versi Flutter dengan FVM

1. **Menginstal Versi Flutter**:
   Anda bisa menginstal berbagai versi Flutter menggunakan perintah berikut:
   ```sh
   fvm install <version>
   ```
   Contoh:
   ```sh
   fvm install 2.0.6
   fvm install 2.2.3
   ```

2. **Menentukan Versi Flutter untuk Proyek**:
   Untuk menggunakan versi Flutter tertentu di proyek Anda, pindah ke direktori proyek dan jalankan perintah berikut:
   ```sh
   cd path/to/your/project
   fvm use <version>
   ```
   Contoh:
   ```sh
   fvm use 2.2.3
   ```

3. **Menetapkan Versi Default Flutter**:
   Jika Anda ingin menetapkan versi Flutter default untuk sistem Anda, Anda bisa menggunakan perintah berikut:
   ```sh
   fvm global <version>
   ```
   Contoh:
   ```sh
   fvm global 2.2.3
   ```

### Langkah 3: Menjalankan Perintah Flutter dengan FVM

Setelah mengatur FVM untuk proyek Anda, Anda harus menggunakan `fvm flutter` sebagai ganti `flutter` untuk menjalankan perintah Flutter. Contoh:
```sh
fvm flutter doctor
fvm flutter run
fvm flutter build apk
```

### Langkah 4: Menambahkan FVM ke PATH

Untuk membuat FVM lebih mudah digunakan, Anda bisa menambahkan FVM ke PATH. Tambahkan baris berikut ke file `~/.zshrc` atau `~/.bash_profile` Anda:
```sh
export PATH="$PATH:$HOME/.pub-cache/bin"
```
Lalu, jalankan perintah berikut untuk memuat ulang file konfigurasi shell:
```sh
source ~/.zshrc
# atau
source ~/.bash_profile
```

Sekarang Anda sudah siap mengelola berbagai versi Flutter di macOS menggunakan FVM. Ini memudahkan Anda untuk bekerja dengan berbagai proyek yang membutuhkan versi Flutter yang berbeda.

```sh
# Instal FVM
brew tap leoafarias/fvm
brew install fvm

# Cek versi FVM
fvm --version

# Daftar versi Flutter yang tersedia
fvm releases

# Instal versi Flutter tertentu
fvm install 3.10.0
fvm install 2.12.0

# Atur versi Flutter untuk proyek
cd path/to/your/project
fvm use 3.10.0

# Atur versi Flutter default untuk sistem
fvm global 3.10.0

# Jalankan perintah Flutter dengan FVM
fvm flutter doctor
fvm flutter run
```

# Java JDK Config

Untuk mengelola dan menginstal banyak versi Java di macOS, Anda dapat menggunakan alat seperti SDKMAN! atau Homebrew. Berikut adalah langkah-langkah untuk kedua metode tersebut:

### Menggunakan SDKMAN!

SDKMAN! adalah alat yang sangat berguna untuk mengelola beberapa versi SDK, termasuk Java. Berikut adalah langkah-langkahnya:

1. **Instal SDKMAN!**:
   Buka Terminal dan jalankan perintah berikut:
   ```sh
   curl -s "https://get.sdkman.io" | bash
   source "$HOME/.sdkman/bin/sdkman-init.sh"
   ```

2. **Instal beberapa versi Java**:
   Setelah SDKMAN! terinstal, Anda dapat menginstal berbagai versi Java dengan perintah berikut:
   ```sh
   sdk install java 8.0.292-open
   sdk install java 11.0.11-open
   sdk install java 16.0.1-open
   ```
   Ubah versi sesuai kebutuhan Anda.

3. **Mengatur versi Java yang aktif**:
   Untuk mengatur versi Java yang aktif, gunakan perintah berikut:
   ```sh
   sdk use java 11.0.11-open
   ```

4. **Menetapkan versi Java default**:
   Untuk menetapkan versi Java default, gunakan perintah berikut:
   ```sh
   sdk default java 11.0.11-open
   ```

### Menggunakan Homebrew

Homebrew juga dapat digunakan untuk mengelola beberapa versi Java, tetapi dengan pendekatan yang sedikit berbeda. Berikut adalah langkah-langkahnya:

1. **Instal Homebrew** (jika belum terinstal):
   Buka Terminal dan jalankan perintah berikut:
   ```sh
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. **Tambahkan repository AdoptOpenJDK**:
   Tambahkan repository AdoptOpenJDK ke Homebrew:
   ```sh
   brew tap AdoptOpenJDK/openjdk
   ```

3. **Instal beberapa versi Java**:
   Instal berbagai versi Java dengan perintah berikut:
   ```sh
   brew install --cask adoptopenjdk8
   brew install --cask adoptopenjdk11
   brew install --cask adoptopenjdk16
   ```

4. **Mengatur JAVA_HOME untuk setiap versi**:
   Anda perlu mengatur variabel lingkungan `JAVA_HOME` untuk setiap versi. Tambahkan perintah berikut ke file `~/.zshrc` atau `~/.bash_profile`:
   ```sh
   export JAVA_HOME_8=$(/usr/libexec/java_home -v 1.8)
   export JAVA_HOME_11=$(/usr/libexec/java_home -v 11)
   export JAVA_HOME_16=$(/usr/libexec/java_home -v 16)
   ```

   Untuk mengubah versi Java yang aktif, jalankan perintah berikut di Terminal:
   ```sh
   export JAVA_HOME=$JAVA_HOME_11
   ```

   Atau untuk permanen, tambahkan `export JAVA_HOME=$JAVA_HOME_11` ke file `~/.zshrc` atau `~/.bash_profile`.

Dengan menggunakan salah satu dari kedua metode ini, Anda dapat dengan mudah menginstal dan mengelola beberapa versi Java di macOS.

Untuk memastikan bahwa Anda telah menambahkan tap `AdoptOpenJDK/openjdk` dengan benar dan melihat daftar versi OpenJDK yang tersedia, Anda bisa menjalankan beberapa perintah di Terminal. Berikut adalah langkah-langkahnya:

### Langkah 1: Tambahkan Tap AdoptOpenJDK

Jalankan perintah berikut untuk menambahkan tap `AdoptOpenJDK/openjdk`:
```sh
brew tap AdoptOpenJDK/openjdk
```

### Langkah 2: Cek Daftar Versi OpenJDK yang Tersedia

Setelah menambahkan tap, Anda dapat melihat daftar versi OpenJDK yang tersedia dengan perintah berikut:
```sh
brew search adoptopenjdk
```

### Langkah 3: Instalasi Versi OpenJDK

Anda dapat menginstal versi yang diinginkan dari daftar yang tersedia. Contoh perintah untuk menginstal berbagai versi OpenJDK adalah:
```sh
brew install --cask adoptopenjdk8
brew install --cask adoptopenjdk11
brew install --cask adoptopenjdk16
```

### Langkah 4: Verifikasi Instalasi

Setelah menginstal versi OpenJDK yang diinginkan, Anda dapat memverifikasi instalasinya dengan menjalankan perintah berikut:
```sh
java -version
```
Pastikan Anda menjalankan perintah di atas setelah mengatur `JAVA_HOME` untuk versi yang diinstal. Anda bisa melakukan ini dengan perintah:
```sh
export JAVA_HOME=$(/usr/libexec/java_home -v 11)
```
Gantilah `11` dengan versi yang Anda inginkan.

### Contoh Implementasi:

1. Tambahkan tap `AdoptOpenJDK/openjdk`:
   ```sh
   brew tap AdoptOpenJDK/openjdk
   ```

2. Cek daftar versi OpenJDK yang tersedia:
   ```sh
   brew search adoptopenjdk
   ```

3. Instal versi OpenJDK yang diinginkan:
   ```sh
   brew install --cask adoptopenjdk8
   brew install --cask adoptopenjdk11
   ```

4. Set `JAVA_HOME` untuk versi yang diinginkan (misalnya, OpenJDK 11):
   ```sh
   export JAVA_HOME=$(/usr/libexec/java_home -v 11)
   ```

5. Verifikasi versi Java yang diinstal:
   ```sh
   java -version
   ```

Dengan langkah-langkah ini, Anda bisa mengelola dan menggunakan berbagai versi OpenJDK di macOS menggunakan Homebrew.
