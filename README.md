# Apa itu Git dan Github?

## Git

**Git** adalah Version Control System (VCS) atau sistem pengelola versi yang digunakan untuk mencatat setiap perubahan dalam file proyek, terutama digunakan untuk pengembangan perangkat lunak secara kolaboratif.

>💡 Git itu seperti mesin waktu untuk kode kamu.

Fungsi dari git antara lain:
- Manajemen data versi proyek
- Melacak perubahan file secara detail
- Memudahkan kolaborasi tim dalam satu proyek

**Github** layanan cloud berbasis Git yang digunakan untuk menyimpan, mengelola, dan berkolaborasi pada proyek secara online.

Fungsi dari github antara lain:
- Menyimpan data pada cloud
- Kolaborasi via internet (remote)
- Mempublikasikan atau memperkenalkan proyek secara publik 

> 💡 GitHub itu seperti Instagram-nya programmer. Tapi yang di-posting kode

# Bekerja dengan Git

## Installation

kunjungi: [https://git-scm.com](https://git-scm.com/)

## Git book (tutorial)

kunjungi:

- https://git-scm.com/book/id/v2 (Bahasa Indonesia)
- https://git-scm.com/book/en/v2 (English)

## Penggunaan Git

Penggunaan Git dibagi menjadi dua**:** 

- Git Bash: Menggunakan command / console
- Git GUI : Menggunakan tampilan GUI

## Command Git Bash

Penggunaan Git diawali dengan "git" pada console, lalu tambahkan perintah.
Beberapa perintah basic pada Git:

|              |                                                                            |               |                                                                    |                |                                                                                               |
| ------------ | -------------------------------------------------------------------------- | ------------- | ------------------------------------------------------------------ | -------------- | --------------------------------------------------------------------------------------------- |
| `git init`   | Membuat repo kosong atau inisialisasi ulang yang sudah ada                 | `git fetch`   | Mengecek objek dan referensi dari repo lain /  remote              | `git commit`   | Merekam perubahan dari repo                                                                   |
| `git status` | Menampilkan status Working Tree                                            | `git add`     | Menambahkan konten file ke indeks                                  | `git checkout` | Berpindah ke sebuah commit atau branch                                                        |
| `git show`   | Menampilkan berbagai jenis objek                                           | `git rm`      | Menghapus file dari Working Tree dan dari indeks                   | `git branch`   | Membuat daftar atau hapus cabang                                                              |
| `git bisect` | Penggunakan pencarian biner untuk menemukan commit yang memperkenalkan bug | `git mv`      | Memindahkan atau menggganti nama file, direktori, atau symlink     | `git merge`    | Menggabungkan dua atau lebih riwayat pengembangan secara bersamaan                            |
| `git diff`   | Menampilkan perubahan antara commit, commit dan Working Tree, dll          | `git restore` | Memulihkan file Working tree                                       | `git switch`   | Beralih cabang                                                                                |
| `git grep`   | Mencetak garis yang cocok dengan pola                                      | `git clone`   | Mengkloning repositori ke direktori baru                           | `git tag`      | Membuat, mencantumkan, menghapus, atau memverifikasi objek tag yang ditandatangani dengan GPG |
| `git log`    | Menampilkan log commit                                                     | `git push`    | Mengambil dari dan integrasikan dengan repo lain atau cabang lokal | `git reset`    | Menyetel ulang HEAD saat ini ke status yang ditentukan                                        |
| `git config` | Mengatur repo atau opsi global                                             | `git pull`    | Memperbarui referensi jarak jauh bersama dengan objek terkait      | `git rebase`   | Menerapkan kembali commit di atas tip dasar lainnya                                           |

Selengkapnya ketik `git help -a`.

## Tiga Area pada Repo Git

- Working Tree: repo tempat bekerja
- Staging Area: perubahan di dalam repo
- History: ketika repo sudah dicommit

 Staging Area dan Histori tersimpan di folder ".git"

![Area Git](/img/area_git.png)

## Membuat Repo

1. Arahkan direktori pada folder yang ditentukan menggunakan `cd` atau klik kanan pada folder dan klik “git bash”.
2. Lalu ketik `git init` untuk merubah folder menjadi repo.

## Commit

1. Ketik `git add .` untuk menambahkan semua perubahan pada Staging Area.
2. Lalu ketik `git commit -m "(pesan)"`.

Anda juga bisa ketik `git commit -am "(pesan)"` tanpa menggunakan `git add.`. Jika ada conflict, bisa selesaikan dengan code editor.

## Checkout

1. Untuk checkout membutuhkan 5 hash awal pada commit yang dituju dengan cara `git log`.
2. Lalu ketik `git checkout (5 hash)`.
3. Untuk mengembalikan spesifik file ketik `git checkout (5 hash) -- (nama file)`.

Chechkout bisa digunakan untuk berpindah branch dengan `git checkout (nama branch)`.

## Branch

1. Buat branch dengan `git branch (nama branch)`.
2. Ketik `git checkout (nama branch)` untuk berpindah head branch.d Untuk menghapus branch yang sudah dimerge ketik `git branch -d (nama branch)`, akan tetapi branch yang belum dimerge tidak bisa dihapus. Untuk hapus paksa ketik `git branch -D (nama branch)`.

## Merge

1. Chechkout pada branch pada branch utama / current branch.
2. Lalu ketik `git merge (nama branch yang mau dimerge / incoming branch)`.

Pembagian merge ada dua yaitu:

- Fast-forward Merge (branch lain lebih update daripada branch master).
- Three-way Merge (kedua branch lain dan master update).

Contoh pada diagram:

![merge](/img/merge.png)

![merge fast three](/img/merge_fast_three.png)

## Rebase

1. ketik `git rebase master`.

Rebase menjadikan Three-way ke Fast-forward.

![rebase](/img/rebase.png )

## Clone

1. Copy link repo / remote yang akan diclone.
2. Arahkan direktori sesuai pilihan, lalu ketik `git clone (link)`.

Selain menggunakan https juga bisa menggunakan ssh. 

## Push

1. Sebelum push ke origin remote harus dicommit dahulu.
2. Lalu ketik `git push -u origin` untuk awal push.

Memerlukan login akun remote tersebut untuk melakukan push jika kloning menggunakan https.

Setelahnya anda bisa ketik `git push`. 

## Pull

1. Ketik `git pull -u origin`  untuk memperbarui sehingga update seperti remote.

Setelahnya anda bisa ketik `git pull`. 

## Config

- Untuk melihat setting ketik **`git config --list`**
- Parameter `--global` untuk mengubah seluruh setting repo tertentu pada semua repo di device.
- Parameter `--local` hanya mengubah setting repo tertentu pada repo itu sendiri.
- Mengganti akun dengan cara `git config --global user.name "(username)"` dan ketik `git config --local user.email "(email)"`.

## Git Ignore

Sebuah file yang disimpan di repo berfungsi sebagai pengecualian file yang tidak ingin di commit. Contoh penggunaan:

1. Buka file “.gitignore” pada repo.

```cpp
$ git status
[...]
# Untracked files:
[...]
#       Documentation/foo.html
#       Documentation/gitignore.html
#       file.o
#       lib.a
#       src/internal.o
[...]

$ cat Documentation/.gitignore
// ignore generated html files,
*.html
// ignore objects and archives, anywhere in the tree.
*.[oa]
// except foo.html which is maintained by hand
!foo.html

$ git status
[...]
# Untracked files:
[...]
#       Documentation/foo.html
[...]
```

>💡Tips: Gunakan alias untuk mempersingkat command, contoh: `git config --global alias.(alias) "command"`.

# Bekerja dengan Github

## Export dari Device ke Github

1. Pastikan folder sudah menjadi repo.
2. Lalu pada website, buat new repo. Pastikan nama repo Github seperti nama repo device.
3. Jangan checklist README, lalu klik “Creating repository”.
4. Kemudian ketik `git remote add origin (link repo Github)` dan ketik `git push -u origin master`.

## Hosting Web **M**enggunakan Github

1. Pada Github, buat repo baru dan menamakan dengan “(nama repo).github.io”.
2. Lalu export repo device anda ke repo Github untuk dijadikan remote.

Pastikan repo berisi minimal html file pada folder terdepan. Anda juga bisa menambahkan css dan javascript file.

Web hosting ini hanya untuk web statis, yaitu web hanya menampilkan saja dan tidak bisa menambahkan database.

Anda juga bisa menambahkan repo untuk menjadikan Github Pages dengan klik Settings >> Github Pages >> Source >> pilih branch. Anda bisa memilih tema atau tidak.

Karena Penggunaan Github seperti Git hanya saja tampilan Github menggunakan web, jadi tidak perlu dijelaskan.

# Kosa-Kata

| **repo**     | folder project                   | **fork**   | menduplikasi repo orang    |
| ------------ | -------------------------------- | ---------- | -------------------------- |
| **hash**     | penanda unik pada se buah commit | **clone**  | mengambil repo dari remote |
| **commit**   | rekaman / snapshot dari repo     | **remote** | sumber yang memiliki repo  |
| **checkout** | berpindah ke sebuah commit       | **push**   | mengirim commit ke repo    |
| **branch**   | cabang bebas dari sebuah commit  | **pull**   | mengambil commit dari repo |
| **merge**    | menggabungkan branch             | **log**    | histori commit             |

# Referensi

- **Git Web**: [https://git-scm.com/book](https://git-scm.com/book/id/v2)
- **Youtube** (WPU): https://www.youtube.com/@sandhikagalihWPU