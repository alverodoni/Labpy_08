# Labpy_08
Nama : Doni Alvero <p>
Nim : 312410663 <p>
Kelas : TI.24.A.5 <p>
Mata Kuliah : Bahasa Pemrograman <p>

# Program Input Nilai
## Diagram Class
![gambar4](https://github.com/user-attachments/assets/e55572ed-5632-4519-8656-e1b36c5d34f8)

## Penjelasan Diagram 
1. Kelas Student:
- Atribut:
   - nim: Menyimpan NIM mahasiswa.
   - nama: Menyimpan nama mahasiswa.
   - tugas: Menyimpan nilai tugas mahasiswa.
   - uts: Menyimpan nilai UTS mahasiswa.
   - uas: Menyimpan nilai UAS mahasiswa.
   - akhir: Menyimpan nilai akhir yang dihitung menggunakan metode calculate_final_grade().
- Metode:
   - __init__: Konstruktor untuk menginisialisasi atribut objek Student.
   - calculate_final_grade: Menghitung dan mengembalikan nilai akhir berdasarkan bobot nilai tugas, UTS, dan UAS.
2. Fungsi-fungsi:
   - display_menu(): Menampilkan menu pilihan.
   - display_students(students: list): Menampilkan daftar mahasiswa beserta nilai-nilainya.
   - find_student_index(students: list, nama: str) -> int: Mencari indeks mahasiswa berdasarkan nama.
   - main(): Fungsi utama yang menjalankan program dengan loop interaksi pengguna.


## Flowchart
![gambar3](https://github.com/user-attachments/assets/97c99967-e140-4fa1-baaa-5e97c955f9d0)


## Program Python
![gambar1](https://github.com/user-attachments/assets/b9d5e0a8-3001-43ff-9f76-3c97de190a2e)
![gambar2](https://github.com/user-attachments/assets/30bbb892-211f-4a6f-ba22-4da80f73cc06)


### Penjelasan Program
1. Kelas Student:
   
        class Student:
            def __init__(self, nim, nama, tugas, uts, uas):
               self.nim = nim
               self.nama = nama
               self.tugas = tugas
               self.uts = uts
               self.uas = uas
               self.akhir = self.calculate_final_grade()
   - Kelas ini menyimpan informasi tentang mahasiswa, seperti NIM, nama, nilai tugas, UTS, dan UAS.
   - Metode calculate_final_grade menghitung nilai akhir mahasiswa berdasarkan bobot yang diberikan (30% tugas, 35% UTS, dan 35% UAS).

2. Fungsi display_menu:

        def display_menu():
            print("\n[(L)ihat, (T)ambah, (U)bah, (H)apus, (K)eluar]: ", end=' ')
   - Fungsi ini menampilkan menu pilihan kepada pengguna dengan opsi untuk melihat, menambah, mengubah, menghapus, atau keluar.
3. Fungsi display_students:

       def display_students(students):
          print("\nDaftar Nilai")
          print("=" * 84)
          print(f"| {'NO':<3} | {'NIM':<10} | {'NAMA':<30} | {'TUGAS':<6} | {'UTS':<4} | {'UAS':<4} | {'AKHIR':<5} |")
          print("=" * 84)
          if not students:
              print(f"| {'TIDAK ADA DATA':^80} |")
          else:
              for i, student in enumerate(students, start=1):
                  print(f"| {i:<3} | {student.nim:<10} | {student.nama:<30} | {student.tugas:<6} | {student.uts:<4} | {student.uas:<4} | {student.akhir:<5} |")
          print("=" * 84)
    - Fungsi ini menampilkan daftar mahasiswa beserta nilai-nilainya dalam format tabel.
4. Fungsi find_student_index:
   
         def find_student_index(students, nama):
             for index, student in enumerate(students):
                 if student.nama == nama:
                     return index
             return None
   - Fungsi ini mencari indeks mahasiswa dalam daftar berdasarkan Nama yang diberikan. Jika ditemukan, mengembalikan indeks tersebut; jika tidak, mengembalikan None.
5. Fungsi main:
   
    
         def main():
             students = []
             while True:
                 display_menu()
                 choice = input().lower()
                 if choice == 't':
                     nim = input("\nNIM: ")
                     nama = input("Nama: ")
                     tugas = int(input("Nilai Tugas: "))
                     uts = int(input("Nilai UTS: "))
                     uas = int(input("Nilai UAS: "))
                     students.append(Student(nim, nama, tugas, uts, uas))
                 elif choice == 'l':
                     display_students(students)
                 elif choice == 'u':
                     display_students(students)
                     nama = input("\nMasukkan nama mahasiswa yang akan diubah: ")
                     index = find_student_index(students, nama)
                     if index is not None:
                         print("Data baru:")
                         nama = input("Nama: ")
                         tugas = int(input("Nilai Tugas: "))
                         uts = int(input("Nilai UTS: "))
                         uas = int(input("Nilai UAS: "))
                         students[index] = Student(nim, nama, tugas, uts, uas)
                     else:
                         print("Mahasiswa dengan nama tersebut tidak ditemukan.")
                 elif choice == 'h':
                     display_students(students)
                     nama = input("\nMasukkan nama mahasiswa yang akan dihapus: ")
                     index = find_student_index(students, nama)
                     if index is not None:
                         del students[index]
                         print("Data mahasiswa berhasil dihapus.")
                     else:
                         print("Mahasiswa dengan nama tersebut tidak ditemukan.")
                 elif choice == 'k':
                     break
                 else:
                     print("Pilihan tidak valid!")
   - Fungsi utama yang menjalankan program.
   - Di dalamnya terdapat loop yang terus berjalan menampilkan menu dan memproses pilihan pengguna:
     - T: Menambah data mahasiswa baru.
     - L: Menampilkan daftar mahasiswa.
     - U: Mengubah data mahasiswa berdasarkan Nama.
     - H: Menghapus data mahasiswa berdasarkan Nama.
     - K: Keluar dari program.
     - 
   ## Hasil Program
  ![gambar5](https://github.com/user-attachments/assets/4f7f7f08-7b5a-4dce-b5e4-f4688167ce92)
  ![gambar6](https://github.com/user-attachments/assets/2b12dca3-040d-4260-be3f-6d0e7bdff86f)




   





