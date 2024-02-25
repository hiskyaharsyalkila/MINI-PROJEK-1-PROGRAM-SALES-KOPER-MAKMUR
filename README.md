# MINI-PROJEK-1-PROGRAM-SALES-KOPER-MAKMUR
HISKYA HARSYAL KILA 2309116089

~~~

import uuid

class TokoKoper:
    def __init__(self):
        self.data = {}

    def create_item(self, nama, harga, jumlah, ukuran, warna):
        id = str(uuid.uuid4())
        item = {
            "id": id,
            "nama": nama,
            "harga": harga,
            "jumlah": jumlah,
            "ukuran": ukuran,
            "warna": warna
        }
        self.data[id] = item
        return id

    def read_item(self, id):
        if id in self.data:
            return self.data[id]
        else:
            return None

    def update_item(self, id, nama=None, harga=None, jumlah=None, ukuran=None, warna=None):
        if id in self.data:
            if nama:
                self.data[id]["nama"] = nama
            if harga:
                self.data[id]["harga"] = harga
            if jumlah:
                self.data[id]["jumlah"] = jumlah
            if ukuran:
                self.data[id]["ukuran"] = ukuran
            if warna:
                self.data[id]["warna"] = warna
            return True
        else:
            return False

    def delete_item(self, id):
        if id in self.data:
            del self.data[id]
            return True
        else:
            return False

if __name__ == "__main__":
    toko_koper = TokoKoper()

    # Membuat beberapa item
    lx7 = toko_koper.create_item("Koper Baller", 5500000, 11, "24 inch", "hitam")
    lx9 = toko_koper.create_item("Koper Polo Team", 600000, 9, "20 inch", "silver")
    lx0 = toko_koper.create_item("Koper Roaming", 890000, 14, "20 inch", "biru mudah")
    mx7 = toko_koper.create_item("Koper Lojel", 1500000, 13, "30 inch", "merah mudah")
    mx9 = toko_koper.create_item("Koper Airwheel", 9900000, 17, "24 inch", "putih")
    
    # Membaca item
    print(f"Item dengan ID {lx7}:")
    print(toko_koper.read_item(lx7))
    print(f"Item dengan ID {lx9}:")
    print(toko_koper.read_item(lx9))
    print(f'Item dengan ID {lx0}:')
    print(toko_koper.read_item(lx0))
    print(f'Item dengan ID {mx7}:')
    print(toko_koper.read_item(mx7))
    print(f'Item dengan ID {mx9}:')
    print(toko_koper.read_item(mx9))

    # Memperbarui item
    toko_koper.update_item(lx7, nama="Koper Baller (baru)", harga=5500000, jumlah=11, ukuran="24 inch", warna="hitam")
    print(f"Item dengan ID {lx7} setelah diperbarui:")
    print(toko_koper.read_item(lx7))

    # Menghapus item
    toko_koper.delete_item(lx9)
    print(f"Item dengan ID {lx9} setelah dihapus:")
    print(toko_koper.read_item(lx9))

    # Menampilkan semua item yang tersedia
    print("Semua item yang tersedia:")
    for item in toko_koper.data.values():
        print(item)
~~~
