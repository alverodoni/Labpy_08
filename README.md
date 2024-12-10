# Labpy_08
Nama : Doni Alvero <p>
Nim : 312410663 <p>
Kelas : TI.24.A.5 <p>
Mata Kuliah : Bahasa Pemrograman <p>

# Program Input Nilai
## Diagram Class
![gambar6](https://github.com/user-attachments/assets/6dabdf78-daaf-4fe4-aacf-c07231ca0bee)



## Flowchart
![gambar5](https://github.com/user-attachments/assets/1159ed8b-faf9-4217-8d43-70c92b132a09)

## Program Python
![gambar3](https://github.com/user-attachments/assets/b7230ece-628f-4245-ae87-0a79287d69fb)
![gambar4](https://github.com/user-attachments/assets/f9cdff05-123d-44d0-a186-0c56b864327f)

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

  ## Hasil Program
  ![gambar1](https://github.com/user-attachments/assets/c2565624-aa72-4e1d-be00-dc6168627b9c)
  ![gambar2](https://github.com/user-attachments/assets/2b918706-90c6-4389-8e0b-88db35690a11)


   





