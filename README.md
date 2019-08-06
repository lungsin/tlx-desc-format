# MarkX Format 

## Basic Text Formatting

### Bold

Format: 

- `**` + `<bold text>` + `**`

Contoh: 

- 
    ```
    MarkX is **really** useful.
    ```
    
    > MarkX is **really** useful.

### Italic

Format: 

- `*` + `<italic text>` + `*`

Contoh: 

- 
    ```
    *MarkX* is really useful.
    ```
    
    > *MarkX* is really useful.
    
### Strikethrough

Format: 

- `~` + `<striketrhrough text>` + `~` 

Contoh: 

- 
    ```
    MarkX ~jelek~ bagus
    ```
    
    > MarkX ~~jelek~~ bagus
    
### Superscript and Subscript

Format Superscript: 

- `_` + `<text>`

Format Subscript: 

- `^` + `<text>`
    
Catatan: `text` tidak boleh mengandung whitespace atau koma, apabila ingin mengikutkan karakter tersebut, anda harus meng escape karakter tersebut.
    
Contoh: 

- 
    ```
    A_i dan A^i
    ```
    
    > A <sub> i</sub> dan A <sup> i </sup>

- 
    ```
    A_ijk dan A^ijk
    ```
    
    > A <sub> ijk </sub> dan A <sup> ijk </sup> 
    
- 
    ```
    A_escape\ spasi
    A^escape\ spasi
    ```
    
    > A <sub> escape spasi </sub> \
    > A <sup> escape spasi </sup>
    
- 
    ```
    A_i,koma
    A^i,koma
    ```
    
    > A <sub> i </sub>,koma\
    > A <sup> i </sup>,koma
    
- 
    ```
    A_i^j
    ```
    
    > A <sub> i </sub> <sup> j </sup>
    
- 
    ```
    A^i_j
    ```
    
    > A <sup> i </sup> <sub> j </sub>
    

### Ketidaksamaan
 
Semua `<=` dan `>=` masing2 akan diubah menjadi `≤` dan `≥`.

### Multilevel bullet points

Contoh:

- 
    ```
    - level 1
        - level 2
            - level 3
    ```
    
    > - level 1
    >   - level 2
    >     - level 3


### Kombinasi 

Semua format diatas dapat dikombinasikan. Contoh: 

- 
    ```
    - ***italic bold***
    - *~italic strikethrough~*
    - **bold A_i^j**
    ```
    
    > - ***italic bold***
    > - *~~italic strikethrough~~*
    > - **bold A<sub>i</sub><sup>j</sup>**
    
## Judul

Judul harus berada baris pertama setiap deskripsi.

Format: 

- satu baris berisi `[` + `<text>` + `]`


Contoh: 
- `Judul`:
    ```
    [Kucing Pak Dengklek]
    ```

    akan diformat menjadi 

    > ## Kucing Pak Dengklek

## General Tag 

Tag ini dapat dipakai untuk membuat section untuk Deskripsi, Format Masukan, Format Keluaran, Format Interaksi, atau Penjelasan.

Format: 

- satu baris dengan format `[` + `<text>` + `]`, 

- diikuti oleh beberapa baris berisi text paragraph. Text paragraph disini dapat mengandung basic format text   seperti **bold**, *italic*, <sup>superscript</sup>, atau <sub> subscript<sub>.

Contoh: 

-  `Deskripsi`:
    ```
    [Deskripsi]

    Pak Dengklek membuka suatu usaha **baru**. 

    Diberikan N buah bilangan, carilah median dari A_1, A_2, ..., A_N.
    ```

    akan diformat menjadi: 

    > ### Deskripsi
    > 
    > Pak Dengklek membuka suatu usaha baru. 
    >
    > Diberikan N buah bilangan, carilah median dari A<sub>1</sub>, A<sub>2</sub>, ..., A<sub>N</sub>.
    
- `Format Keluaran`: 
    ```
    [Format Keluaran]

    Sebuah baris berisi sebuah bilangan bulat yang menyatakan median dari N bilangan tersebut.
    ```

    akan diformat menjadi: 

    > ### Format Keluaran
    > 
    > Sebuah baris berisi sebuah bilangan bulat yang menyatakan median dari N bilangan tersebut.

## Tag yang mengandung test data

Tag ini dapat dipakai untuk membuat section untuk Contoh Masukan, Contoh Keluaran, Contoh Interaksi.

Format: 

- Satu baris dengan format `[` + `<special text>` + `]`, `special text` disini harus lah dalam format: 

    - `Contoh Masukan` atau `Contoh Keluaran` atau `Contoh Interaksi`
    - Diikuti oleh satu atau lebih spasi.
    - Diikuti oleh sebuah bilangan bulat
    
- Diikuti oleh beberapa section yang menyatakan test data, tiap section dipisahkan oleh sebuah baris kosong.  Formalnya, tiap section terdiri dari: 
    - Beberapa baris, yang mana tiap barisnya dapat diawali dengan indentasi. Indentasi disini berguna untuk `Contoh Interaksi` (untuk lebih detailnya, lihat Contoh dibawah).
    - Diakhiri oleh sebuah baris kosong.
 
    Section disini akan 

Contoh: 
- `Contoh Masukan`: 
    ```
    [Contoh Masukan 1]
    
    5
    1 2 3 4 5

    ```

    akan diformat menjadi: 

    > ### Contoh Masukan 1
    > 
    > ```
    > 5
    > 1 2 3 4 5
    > ```
    
- `Contoh Interaksi`: 
    ```
    [Contoh Interaksi 1]
    
        5
        1 2 3 4 5
    1
        5
    2
    3
        3
    ```
    
    akan diformat menjadi: 
    
    > ### Contoh Interaksi 1
    > | Keluaran Program Anda | Keluaran Program Juri  |
    > |----|----|
    > |    | 5  | 
    > |    | 1 2 3 4 5  |
    > | 1  |   |
    > |    | 5 |
    > | 2  |   |
    > | 3  |   |
    > |    | 3 |
    
    

## Tag Subsoal 

TODO

## Text URL 

Disini URL perlu didefinisikan disebuah metadata. Anda dapat mendefinisikan metadata link dengan memasukan snippet dengan format sebagai berikut: 

```
@links: 
<label 1>: <url path 1>
<label 2>: <url path 2>
```

Label hanya boleh mengandung karakter alfanumerik.
Anda dapat meletakan metadata ini dimanapun manapun (diawal, ditengah, atau diakhir file). 

Selanjutnya, anda dapat menginsert text ber-link dengan format: 

`[` + `<url text>` + `]@` + `<label>`

Contoh: 

- 
    ```
    Klik [disini]@linkGoogle untuk menuju Google.
    Klik [disini]@linkYoutube untuk menuju Youtube.
    Klik [disini]@linkRelatif untuk menuju link relatif.
    
    @links:
    linkGoogle: https://www.google.com
    linkYoutube: https://www.youtube.com
    linkRelatif: /contoh.txt
    ```
    
    > Klik <a href="https://www.google.com"> disini </a> untuk menuju Google.\
    > Klik <a href="https://www.youtube.com"> disini </a> untuk menuju Youtube.\
    > Klik <a href="https://www.google.com"> disini </a> untuk menuju link relatif.

## Gambar

URL dari gambar yang akan dimasukkan perlu didefinisikan disebuah metadata. Anda dapat mendefinisikan metadata gambar dengan memasukan snippet dengan format sebagai berikut:

```
@images: 
<label 1>: <url gambar 1>
<label 2>: <url gambar 2>
``` 

Label hanya boleh mengandung karakter alfanumerik.
Anda dapat meletakan metadata ini dimanapun manapun (diawal, ditengah, atau diakhir file). 

Selanjutnya, anda dapat menginsert text ber-link dengan salah satu format berikut:

- Apabila gambar berada di TLX, maka gambar2 akan selalu diletakkan di link relatif `/render/<nama file gambar>`. Anda dapat menggunakan format: 

    - `@<nama file gambar>`

    Contoh: 
    
    - 
        ```
        @catur.jpg
        ```
        
        akan menampilkan gambar di relatif link `/render/catur.jpg`
        
        > <img src="/render/catur.jpg">
        
- Apabila gambar berada di luar relatif path `/render/`, anda dapat memasukan gambar yang sudah didefinisikan di metadata dengan format sebagai berikut: 
    
    - `@<label gambar>`, atau
    
    - `[alt text gambar]@<label gambar>`
    
    Contoh: 
    
    - 
        ```
        gambar dadu: 
        @dadu
        
        gambar kucing dengan alt text (hover ke gambar): 
        [gambar dicopy dari google]@kucing
        
        @images: 
        dadu: /render/other/dadu.jpg
        kucing: https://i.ytimg.com/vi/V015SjjbYXE/maxresdefault.jpg
        ```
        
        > gambar dadu: \
        > <img src="/render/other/dadu.jpg">\
        > \
        > gambar kucing dengan alt text (hover ke gambar): 
        > <img src="https://i.ytimg.com/vi/V015SjjbYXE/maxresdefault.jpg" title="gambar dicopy dari google">
        
Catatan: 

Apabila terdapat label yang sama di `@links` dan `@images` maka apabila gambar yang ditampilkan diklik, anda akan diarahkan ke link yang didefinisikan di `@links`.
        
