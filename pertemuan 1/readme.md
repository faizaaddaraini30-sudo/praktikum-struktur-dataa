Stack (Tumpukan)
Stack adalah struktur data yang bekerja dengan prinsip LIFO (Last In, First Out), yaitu elemen yang terakhir masuk akan menjadi elemen pertama yang diambil. Konsep stack mirip seperti tumpukan piring; piring yang diletakkan paling atas akan diambil lebih dulu.
Di Python, stack dapat dibuat menggunakan list dengan memanfaatkan .append() untuk memasukkan data dan .pop() untuk mengeluarkan data.
Di Python, stack dapat dibuat menggunakan list dengan memanfaatkan `.append()` untuk memasukkan data dan `.pop()` untuk mengeluarkan data.

Penjelasan Kode

1. Membuat Stack Kosong
   

```python
stack = []
```

Bagian ini membuat sebuah list kosong yang akan digunakan sebagai stack.

2. Push (Menambah Elemen)

```python
stack.append('A')
stack.append('B')
stack.append('C')
print("Stack: ", stack)
```

Fungsi .append() menambahkan data ke bagian atas stack.
Elemen dimasukkan secara berurutan: 'A', 'B', dan 'C'.
Hasil sementara: ['A', 'B', 'C'].
 Fungsi `.append()` menambahkan data ke bagian atas stack.
 Elemen dimasukkan secara berurutan: `'A'`, `'B'`, dan `'C'`.
 Hasil sementara: `['A', 'B', 'C']`.

3. Pop (Menghapus Elemen Teratas)

```python
element = stack.pop()
print("Pop: ", element)
```

.pop() menghapus elemen yang terakhir ditambahkan.
Elemen yang keluar adalah 'C'.
 `.pop()` menghapus elemen yang terakhir ditambahkan.
 Elemen yang keluar adalah `'C'`.

4. Peek (Melihat Elemen Teratas)

```python
topElement = stack[-1]
print("Peek: ", topElement)
```

stack[-1] digunakan untuk melihat elemen paling atas tanpa menghapusnya.
Karena 'C' sudah dikeluarkan, elemen teratas sekarang 'B'.
 `stack[-1]` digunakan untuk melihat elemen paling atas tanpa menghapusnya.
 Karena `'C'` sudah dikeluarkan, elemen teratas sekarang `'B'`.

5. isEmpty (Mengecek Apakah Stack Kosong)

```python
isEmpty = not bool(stack)
print("isEmpty: ", isEmpty)
```

bool(stack) bernilai True jika stack masih berisi data.
not bool(stack) bernilai True jika stack kosong.
Karena stack masih berisi ['A', 'B'], hasilnya adalah False.
 `bool(stack)` bernilai True jika stack masih berisi data.
  `not bool(stack)` bernilai True jika stack kosong.
 Karena stack masih berisi `['A', 'B']`, hasilnya adalah False.

6. Size (Jumlah Elemen dalam Stack)
print("Size :", len(stack))

len(stack) menghitung banyaknya elemen yang tersisa.
Hasilnya adalah 2.
```python
print("Size :", len(stack))
```

 `len(stack)` menghitung banyaknya elemen yang tersisa.
  Hasilnya adalah 2.

Output Program
Berikut hasil yang akan muncul saat kode dijalankan:

Output Program :
```
Stack:  ['A', 'B', 'C']
Pop:  C
Peek:  B
isEmpty:  False
Size :  2
```

Kesimpulan :
Kesimpulan
Dari program tersebut dapat disimpulkan bahwa struktur data stack bekerja dengan prinsip LIFO, di mana elemen terakhir yang masuk akan menjadi elemen pertama yang keluar. Operasi dasar seperti push, pop, peek, pengecekan kosong (isEmpty), dan menghitung ukuran (size) dapat dilakukan dengan mudah menggunakan list pada Python. Program ini menunjukkan bagaimana stack dapat digunakan untuk mengelola data secara teratur dan efisien.


@@ -65,47 +85,72 @@ Queue adalah struktur data yang bekerja dengan prinsip FIFO (First In First Out)

Penjelasan Codingan
1. Membuat Queue

```python
queue = []
```

List kosong dibuat sebagai tempat menyimpan data antrian.

2. Enqueue (Menambah Elemen ke Belakang)

```python
queue.append('A')
queue.append('B')
queue.append('C')
print("Queue: ", queue)
```

append() menambah elemen ke bagian akhir antrian, sehingga queue berisi: ['A', 'B', 'C'].
`append()` menambah elemen ke bagian akhir antrian, sehingga queue berisi: `['A', 'B', 'C']`.

3. Dequeue (Menghapus Elemen Pertama)

```python
element = queue.pop(0)
print("Dequeue: ", element)
```

pop(0) menghapus elemen paling depan (FIFO), yaitu 'A'.
`pop(0)` menghapus elemen paling depan (FIFO), yaitu `'A'`.

4. Peek (Melihat Elemen Terdepan)

```python
frontElement = queue[0]
print("Peek: ", frontElement)
```

Menampilkan elemen paling depan tanpa menghapusnya, yaitu 'B'.
Menampilkan elemen paling depan tanpa menghapusnya, yaitu `'B'`.

5. Mengecek Apakah Queue Kosong

```python
isEmpty = not bool(queue)
print("isEmpty: ", isEmpty)
```

Jika queue tidak kosong, hasilnya False.
Jika queue tidak kosong, hasilnya False

6. Mengetahui Jumlah Elemen (Size)

```python
print("Size: ", len(queue))
```

Menghitung elemen yang tersisa, yaitu 2.

Output Program :

Output Program
Berikut output lengkap ketika program dijalankan:

```
Queue:  ['A', 'B', 'C']
Dequeue:  A
Peek:  B
isEmpty:  False
Size:  2
```

Kesimpulan
Dari program ini dapat disimpulkan bahwa queue bekerja dengan cara mengelola data secara berurutan menggunakan prinsip FIFO. Operasi dasar seperti enqueue, dequeue, peek, pengecekan kondisi kosong, dan perhitungan ukuran queue membantu menunjukkan bagaimana antrian memproses data satu per satu dari depan ke belakang. Program ini menggambarkan cara kerja queue secara sederhana namun jelas.


