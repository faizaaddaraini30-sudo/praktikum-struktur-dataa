#  **Penjelasan Kode Linked List Per Fungsi**

## 1. **Class Node**

```python
class Node:
    def __init__(self, data=None, pointer=None):
        self.data = data
        self.next = pointer
```

### Fungsi:

* **Node** adalah elemen dasar linked list.
* Setiap node menyimpan:

  * `data` → nilai yang disimpan
  * `next` → pointer ke node berikutnya

Contoh: `Node("apel")`
akan membuat node berisi kata "apel" dan pointer `next = None`.


# 2. **Class LinkedList**

```python
class LinkedList:
    def __init__(self):
        self.head = None
```

### Fungsi:

* `head` menyimpan node pertama dalam linked list.
* Saat objek LinkedList baru dibuat, list masih kosong (`head = None`).


## 3. **insert_at_first(data)**

```python
def insert_at_first(self, data):
    node = Node(data, self.head)
    self.head = node
```

### Fungsi:

* Menambahkan node baru **di posisi awal (head)**.
* Node baru akan menunjuk ke head lama.
* Head diperbarui ke node baru.


## 4. **insert_at_last(data)**

```python
def insert_at_last(self, data):
    if self.head is None:
        self.head = Node(data)
    else:
        node_sekarang = self.head
        while node_sekarang.next:
            node_sekarang = node_sekarang.next
        node = Node(data)
        node_sekarang.next = node
```

### Fungsi:

* Menambahkan data di **bagian akhir**.
* Jika list kosong → langsung buat head.
* Jika tidak kosong → loop sampai node terakhir → sambungkan node baru.


## 5. **insert_at(index, data)**

```python
def insert_at(self, index, data):
    if index < 0 or index > self.length() - 1:
        print("index tidak valid")
    elif index == 0:
        self.insert_at_first(data)
    else:
        urutan = 0
        node_sekarang = self.head
        while urutan < index - 1:
            urutan += 1
            node_sekarang = node_sekarang.next
        node = Node(data, node_sekarang.next)
        node_sekarang.next = node
```

### Fungsi:

* Menyisipkan node di **posisi tertentu**.
* Validasi index.
* Jika index 0 → pakai insert_at_first.
* Jika index lain → cari posisi sebelum index → sisipkan node.


## 6. **remove_first()**

```python
def remove_first(self):
    if self.head is None:
        print("tidak ada data yang bisa dihapus")
    else:
        self.head = self.head.next
```

### Fungsi:

* Menghapus node paling depan.
* Head dipindahkan ke node berikutnya.


## 7. **remove_last()**

```python
def remove_last(self):
    if self.head is None:
        print("tidak ada data yang bisa dihapus")
    elif self.head.next is None:
        self.head = None
    else:
        node_sebelumnya = None
        node_sekarang = self.head

        while node_sekarang.next:
            node_sebelumnya = node_sekarang
            node_sekarang = node_sekarang.next

        node_sebelumnya.next = None
```

### Fungsi:

* Menghapus node terakhir.
* Tiga kasus:

  1. List kosong
  2. Hanya ada 1 node
  3. Lebih dari 1 node → cari node terakhir dan node sebelumnya → putuskan koneksi


## 8. **remove_at(index)**

```python
def remove_at(self, index):
    if index < 0 or index >= self.length():
        print("index tidak valid")
    elif index == 0:
        self.remove_first()
    else:
        urutan = 0
        node_sekarang = self.head
        while urutan < index - 1:
            node_sekarang = node_sekarang.next
            urutan += 1

        node_sekarang.next = node_sekarang.next.next
```

### Fungsi:

* Menghapus node pada index tertentu.
* Validasi index.
* Jika index 0 → hapus head.
* Jika bukan → cari posisi sebelum index → lompat pointer untuk melewatkan node target.


## 9. **print()**

```python
def print(self):
    if self.head is None:
        print("data kosong")
    else:
        text_print = ""
        node_sekarang = self.head
        while node_sekarang:
            text_print += str(node_sekarang.data) + " -> "
            node_sekarang = node_sekarang.next
        print(text_print)
```

### Fungsi:

* Menampilkan seluruh elemen linked list.
* Format cetak:
  `data1 -> data2 -> data3 ->`


## 10. **length()**

```python
def length(self):
    urutan = 0
    data_sekarang = self.head
    while data_sekarang:
        data_sekarang = data_sekarang.next
        urutan += 1
    return urutan
```

### Fungsi:

* Menghitung jumlah node dalam linked list menggunakan perulangan.


#  **UJI COBA PROGRAM**

```python
LL = LinkedList()

LL.insert_at_first("jeruk")
LL.insert_at_first("mangga") 
LL.insert_at_first("manggis")
LL.insert_at_last("apel")
LL.insert_at(2, "anggur")
```

List setelah insert:
`manggis -> mangga -> anggur -> jeruk -> apel ->`

### Remove:

```python
LL.remove_first()   # hapus manggis
LL.remove_last()    # hapus apel
LL.remove_at(1)     # hapus anggur (index mulai dari 0)
```

List akhir:
`mangga -> jeruk ->`

Output:

```
mangga -> jeruk ->
2
```
