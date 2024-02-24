from prettytable

# Data user dan admin
user_data = {"Sawung": {"pasSword": "Akusukakamu", "saldo": 9000}}
admin_data = {"Admin": {"password": "AraAra"}}

# Data Miniatur
Miniatur_data = {
    "Miniatur robot manusia": {"harga": 800, "deskripsi": "Miniatur Robot dari karakter film Robocop"},
    "Miniatur Dewa petir Thor": {"harga": 700, "deskripsi": "Ini Dia, karakter yang berhasil bikin mokad kakek thanos"},
    "Miniatur Hulk": {"harga": 900, "deskripsi": "I can't lead a mission when the people i'm leading have mission of their own"}
}

# Fungsi login user
def user_login():
    username = input("Masukkan username: ")
    password = input("Masukkan password: ")
    if username in user_data and user_data[username]["password"] == password:
        return username
    else:
        print("Login gagal. Username atau password salah.")
        return None

# Fungsi login admin
def admin_login():
    username = input("Masukkan username admin: ")
    password = input("Masukkan password admin: ")
    if username in admin_data and admin_data[username]["password"] == password:
        return username
    else:
        print("Login admin gagal. Username atau password salah.")
        return None

# Fungsi top up saldo
def top_up_balance(username):
    try:
        amount = int(input("Masukkan jumlah saldo yang ingin ditambahkan: "))
        user_data[username]["saldo"] += amount
        print(f"Saldo Anda sekarang: {user_data[username]['saldo']}")
    except ValueError:
        print("Jumlah saldo harus berupa angka.")

# Fungsi tampilan menu untuk admin
def admin_menu():
    while True:
        print("\nMenu Admin:")
        print("1. Tambah")
        print("2. Lihat")
        print("3. Keluar")
        choice = input("Pilih menu: ")
        if choice == "1":
            break
        else:
            print("Pilihan tidak valid.")

# Program utama
while True:
    print("\nSelamat datang di Toko miniatur")
    print("1. Login User")
    print("2. Login Admin")
    print("3. Keluar")
    choice = input("Pilih menu: ")
    if choice == "1":
        username = user_login()
        if username:
            (username)
    elif choice == "2":
        admin_username = admin_login()
        if admin_username:
            admin_menu()
    elif choice == "3":
        break
    else:
        print("Pilihan tidak valid.")
