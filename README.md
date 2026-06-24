import time
import os
import random

def bersihkan_layar():
    os.system('cls' if os.name == 'nt' else 'clear')

def animasi_loading_bar():
    for i in range(101):
        bersihkan_layar()
        print("\n" * 2)
        print("      [ MEMULAI SISTEM CHAT AFIF ]")
        print("      =============================")
        jarak = i // 5
        bar = "█" * jarak + "-" * (20 - jarak)
        print(f"      [{bar}] {i}%")
        print("      =============================")
        if i < 30: time.sleep(0.02)
        elif i < 70: time.sleep(0.01)
        else: time.sleep(0.03)
    time.sleep(0.5)

def screen_perkenalan():
    bersihkan_layar()
    print("=========================================")
    print("          🤖 INTRODUCING CHAT AFIF       ")
    print("=========================================")
    print(" Halo! Saya Chat Afif, asisten pintar")
    print(" yang dirancang khusus untuk Pydroid 3.")
    print("\n Saya bisa membantumu dalam banyak hal:")
    print(" 📜 Belajar Sejarah Dunia & Indonesia")
    print(" 📚 Membantu Menyelesaikan PR & Tugas")
    print(" 🔢 Menghitung Cepat (Kalkulator)")
    print(" 📝 Menilai Lirik Lagu Secara Jujur")
    print(" 📅 Mencatat Agenda Harian (Daily)")
    print("=========================================")
    print("  Ketik perintah langsung seperti di Google!")
    print("=========================================")
    input("\n Tekan [ENTER] untuk menyalakan asisten...")

def animasi_afif(pesan, status="🟢 Chat Afif"):
    bersihkan_layar()
    print("=" * 45)
    print(f" {status}")
    print("=" * 45)
    for karakter in pesan:
        print(karakter, end='', flush=True)
        time.sleep(0.015)
    print("\n" + "=" * 45)

def asisten_sejarah(perintah):
    if "majapahit" in perintah:
        return "Kerajaan Majapahit adalah kerajaan Hindu-Buddha terbesar di Indonesia yang berpusat di Jawa Timur, runtuh sekitar abad ke-16. Tokoh terkenalnya adalah Raja Hayam Wuruk dan Patih Gajah Mada dengan Sumpah Palapa."
    elif "proklamasi" in perintah or "merdeka" in perintah:
        return "Indonesia memproklamasikan kemerdekaannya pada tanggal 17 Agustus 1945 oleh Ir. Soekarno dan Drs. Mohammad Hatta di Jalan Pegangsaan Timur No. 56, Jakarta setelah Jepang menyerah kepada Sekutu."
    elif "dunia kedua" in perintah or "pede 2" in perintah or "perang dunia 2" in perintah:
        return "Perang Dunia II berlangsung dari tahun 1939 sampai 1945. Melibatkan Blok Poros (Jerman, Italia, Jepang) melawan Blok Sekutu (AS, Inggris, Uni Soviet, Prancis). Berakhir setelah bom atom dijatuhkan di Hiroshima dan Nagasaki."
    else:
        return "Maaf, data sejarah spesifik itu belum ada di memori offline saya. Coba tanya tentang: 'Majapahit', 'Proklamasi Kemerdekaan', atau 'Perang Dunia 2'."

def asisten_pr():
    while True:
        animasi_afif("Selamat datang di Pusat Tugas. Pilih rumus yang ingin diselesaikan:", "📚 Menu PR Sekolah")
        print("1. Luas Persegi\n2. Luas Segitiga\n3. Pythagoras (Cari Sisi Miring)\n4. Kecepatan (Fisika: v = s / t)\n5. Teori Biologi & Sains\n6. Kembali ke Menu Utama")
        pilih = input("\nPilih menu (1-6): ")
        
        if pilih == '1':
            try:
                s = float(input("Masukkan panjang sisi (cm): "))
                animasi_afif(f"Rumus: Luas = sisi x sisi\nHasil: {s} x {s} = {s*s} cm²", "📚 Solusi Luas Persegi")
            except ValueError: print("Input harus angka!")
            input("\nTekan Enter...")
        elif pilih == '2':
            try:
                a = float(input("Masukkan panjang alas (cm): "))
                t = float(input("Masukkan tinggi segitiga (cm): "))
                animasi_afif(f"Rumus: Luas = 0.5 x alas x tinggi\nHasil: 0.5 x {a} x {t} = {0.5*a*t} cm²", "📚 Solusi Luas Segitiga")
            except ValueError: print("Input harus angka!")
            input("\nTekan Enter...")
        elif pilih == '3':
            try:
                a = float(input("Masukkan sisi tegak A: "))
                b = float(input("Masukkan sisi datar B: "))
                c = (a**2 + b**2)**0.5
                animasi_afif(f"Rumus: C = Akar(A² + B²)\nHasil: Akar({a}² + {b}²) = {c}", "📚 Solusi Pythagoras")
            except ValueError: print("Input harus angka!")
            input("\nTekan Enter...")
        elif pilih == '4':
            try:
                s = float(input("Masukkan jarak tempuh (meter): "))
                t = float(input("Masukkan waktu tempuh (sekon): "))
                if t == 0:
                    animasi_afif("Waktu tidak boleh 0!", "🔴 Error")
                else:
                    animasi_afif(f"Rumus: v = s / t\nHasil: {s} / {t} = {s/t} m/s", "📚 Solusi Kecepatan Fisika")
            except ValueError: print("Input harus angka!")
            input("\nTekan Enter...")
        elif pilih == '5':
            animasi_afif("Ketik topik sains yang ingin kamu pelajari (Fotosintesis / Gravitasi):", "📚 Teori Sains")
            tanya = input("Topik: ").lower()
            if "fotosintesis" in tanya:
                animasi_afif("Fotosintesis adalah proses tumbuhan hijau memasak makanan menggunakan air, CO2, dan bantuan cahaya matahari untuk menghasilkan glukosa dan oksigen.", "📚 Fotosintesis")
            elif "gravitasi" in tanya:
                animasi_afif("Gaya Gravitasi Bumi adalah gaya tarik bumi yang menyebabkan benda jatuh ke bawah. Nilai standarnya adalah 9.8 m/s² atau dibulatkan menjadi 10 m/s².", "📚 Gravitasi")
            else:
                animasi_afif("Teori tersebut belum tersedia secara offline.", "🟡 Chat Afif")
            input("\nTekan Enter...")
        elif pilih == '6':
            break

def tambah(x, y): return x + y
def kurang(x, y): return x - y
def kali(x, y): return x * y
def bagi(x, y): return x / y if y != 0 else "Error: Pembagian dengan nol!"

def menu_kalkulator():
    while True:
        animasi_afif("Mode kalkulator aktif. Mau hitung apa?", "🔢 Kalkulator")
        print("1. Penjumlahan (+)\n2. Pengurangan (-)\n3. Perkalian (*)\n4. Pembagian (/)\n5. Kembali")
        pilihan = input("\nPilih menu (1-5): ")
        if pilihan == '5': break
        if pilihan in ('1', '2', '3', '4'):
            try:
                num1 = float(input("Angka pertama: "))
                num2 = float(input("Angka kedua: "))
            except ValueError:
                animasi_afif("Input harus berupa angka!", "🔴 Error")
                time.sleep(1.5)
                continue
            if pilihan == '1': hasil = tambah(num1, num2)
            elif pilihan == '2': hasil = kurang(num1, num2)
            elif pilihan == '3': hasil = kali(num1, num2)
            elif pilihan == '4': hasil = bagi(num1, num2)
            animasi_afif(f"Hasil perhitungan Anda:\n>>> {hasil}", "🔢 Kalkulator")
            input("\nTekan Enter untuk lanjut...")

def nilai_lirik(lirik):
    if not lirik.strip(): return 0, "Kosong."
    kata_kata = lirik.lower().split()
    total_kata = len(kata_kata)
    kata_unik = len(set(kata_kata))
    rasio = kata_unik / total_kata if total_kata > 0 else 0
    skor = 5
    if total_kata < 15: skor -= 2
    elif total_kata > 100: skor += 1
    if rasio < 0.4: skor -= 2
    elif rasio > 0.7: skor += 2
    skor_akhir = max(1, min(10, skor))
    if skor_akhir >= 8: return skor_akhir, "🔥 Keren dan puitis!"
    elif skor_akhir >= 5: return skor_akhir, "🤔 Lumayan standar pop."
    else: return skor_akhir, "💀 Perlu rombak total."

def menu_juri_lirik():
    bersihkan_layar()
    print("=== [ MODE JURI LIRIK ] ===")
    print("Ketik lirik lagu Anda. Tulis 'SELESAI' di baris baru untuk mengakhiri:\n")
    baris_lirik = []
    while True:
        baris = input()
        if baris.strip().upper() == "SELESAI": break
        baris_lirik.append(baris)
    skor, hasil = nilai_lirik(" ".join(baris_lirik))
    animasi_afif(f"Hasil Evaluasi:\nSkor: {skor}/10\nKesimpulan: {hasil}", "📝 Juri Lirik")
    input("\nTekan Enter untuk kembali...")

def main():
    animasi_loading_bar()
    screen_perkenalan()
    catatan_daily = []
    
    while True:
        bersihkan_layar()
        print("=========================================")
        print("        🔍 INTERFACE CHAT AFIF 🔍       ")
        print("=========================================")
        print(" KETIK PERINTAH LANGSUNG UNTUK BERTANYA! ")
        print(" Contoh perintah:")
        print(" • 'sejarah' (buka belajar sejarah)")
        print(" • 'pr' atau 'tugas' (bantuan PR sekolah)")
        print(" • 'kalkulator' (buka aplikasi hitung)")
        print(" • 'lirik' (buka juri lirik lagu)")
        print(" • 'daily' (catat aktivitas harian)")
        print(" • 'keluar' (untuk mematikan sistem)")
        print("=========================================")
        
        perintah_user = input("\nTanya Chat Afif: ").strip().lower()
        
        if not perintah_user:
            continue
            
        if "kalkulator" in perintah_user or "hitung" in perintah_user:
            menu_kalkulator()
            
        elif "lirik" in perintah_user or "lagu" in perintah_user:
            menu_juri_lirik()
            
        elif "sejarah" in perintah_user:
            animasi_afif("Mode Belajar Sejarah Aktif!\nSilakan ketik apa yang ingin kamu ketahui (contoh: Majapahit / Proklamasi / Perang Dunia 2):", "📜 Sejarah")
            tanya_sejarah = input("\nTopik Sejarah: ").lower()
            jawaban = asisten_sejarah(tanya_sejarah)
            animasi_afif(jawaban, "📜 Jawaban Sejarah")
            input("\nTekan Enter untuk kembali...")
            
        elif "pr" in perintah_user or "tugas" in perintah_user or "rumah" in perintah_user:
            asisten_pr()
            
        elif "daily" in perintah_user or "catat" in perintah_user or "harian" in perintah_user:
            while True:
                animasi_afif("Mode Catatan Daily Aktif!", "📅 Daily Note")
                print("1. Tambah Catatan Baru\n2. Lihat Semua Catatan\n3. Kembali ke Menu Utama")
                pilih_daily = input("\nPilih (1-3): ")
                if pilih_daily == '3': 
                    break
                elif pilih_daily == '1':
                    isi_nota = input("Tulis aktivitas/jadwal hari ini: ")
                    catatan_daily.append(f"• {isi_nota} (Dicatat pukul {time.strftime('%H:%M')})")
                    animasi_afif("Catatan harian berhasil disimpan!", "📅 Sukses")
                    time.sleep(1.5)
                elif pilih_daily == '2':
                    if not catatan_daily:
                        animasi_afif("Belum ada catatan harian untuk hari ini.", "📅 Daily Note")
                    else:
                        tabel_catatan = "\n".join(catatan_daily)
                        animasi_afif(f"Berikut catatan harianmu:\n\n{tabel_catatan}", "📅 Daftar Agenda")
                    input("\nTekan Enter untuk melanjutkan...")
                    
        elif "keluar" in perintah_user or "exit" in perintah_user:
            animasi_afif("Sistem Chat Afif dimatikan. Sampai jumpa kembali!", "🟢 Chat Afif")
            time.sleep(2)
            bersihkan_layar()
            break
            
        else:
            animasi_afif("Maaf, perintah tidak dikenali. Ketik kata kunci seperti 'sejarah', 'pr', 'kalkulator', 'lirik', atau 'daily'.", "🟡 Chat Afif")
            time.sleep(2.5)

if __name__ == "__main__":
    main()

