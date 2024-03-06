Resume Alpro
	Chapter 01 : Introduction to Algorithms
Overview: 1.Foundation for the book
                   2.Write your first search algorithm (Binary search)
                   3.Learn about the running time of an algorithm (Big O notation)
	Introduction:
a.	An algorithm is a set of instructions for accomplishing a task
b.	Algorithms chosen in this book (for inclusion)because they’re fast,or they solve interesting problems,or both
c.	The good news is, an implementation of every algorithm in this book is probably available in your favorite language 
d.	But those implementation are useless if you don’t understand the trade offs 
e.	In this books you’ll learns to compare trade offs between different algorithm 

	Simple Search Way :
Simple search way adalah metode paling sederhana, yaitu dengan memasukkan kata kunci (Keywords), baik dari judul, pengarang, atau subjek. Anda dapat memasukkan lebih dari satu kata kunci dalam Simple Search untuk memperluas hasil pencarian.


	A better way to search(Binary search)
Binary Search merupakan sebuah teknik pencarian data dengancara berulang kali membagi separuh dari jumlah data yang dicari sampai sehingga memperkecil lokasi pencarian menjadi satu data. Dengan teknik ini kita akanmembuang setengah dari jumlah data
A.	Langkah Langkah  biner(binary search)
1.Mula diambil posisi awal=1 dan posisi akhir=n.
2. kemudian kita cari posisi data tengah dengan rumus posisi tengah = (posisi awal + posisi akhir) div 2.
3. kemudian data yang dicari dibandingkan dengan data tengah.
4. ulangi langkah 2 sampai data ditemukan, atau tidak ditemukan.
	 B. melakukan pencarian pada data berjumlah besar dengan keadaan terurut serta memiliki iterasi yang lebih efektif 
	Approach for Binary Search
•	Compare the target element with the middle element of the array.
•	If the target element is greater than the middle element, then the search continues in the right half.
•	Else if the target element is less than the middle value, the search continues in the left half.
•	This process is repeated until the middle element is equal to the target element, or the target element is not in the array
•	If the target element is found, its index is returned, else -1 is returned.


 	Code Implementation Binary Search in Java:

package algorithms.searching;
public class BinarySearch {
    public static void main(String[] args) {
        int[] nums = {2, 12, 15, 17, 27, 29, 45};
        int target = 17;
        System.out.println(search(nums, target));
    }

    static int search(int[] nums, int target) {
        int start = 0;
        int end = nums.length - 1;

        while (start <= end) {
            int mid = start + (end - start) / 2;

            if (nums[mid] > target)
                end = mid - 1;
            else if (nums[mid] < target)
                start = mid + 1;
            else
                return mid;
        }
        return -1;
    }
}

 	Binary Search in Python:
def search(nums, target):
    start = 0
    end = len(nums)-1
    while start <= end:
        mid = start + (end-start)//2
        if nums[mid] > target:
            end = mid-1
        elif nums[mid] < target:
            start = mid+1
        else:
            return mid
    return -1
if _name_ == '_main_':
    nums = [2, 12, 15, 17, 27, 29, 45]
    target = 17
    print(search(nums, target))

 	Running Time:
Waktu berjalan kode yang dimodifikasi dengan pencarian biner untuk menemukan peralatan yang hilang umumnya lebih efisien daripada kode asli. Kode asli memiliki kompleksitas waktu O(n), di mana n adalah panjang daftar input. Sebaliknya, pendekatan pencarian biner memiliki kompleksitas waktu O(log n), membuatnya lebih efisien, terutama untuk kumpulan data yang lebih besar.

Pencarian biner membagi kumpulan data menjadi dua dengan setiap iterasi, menghasilkan konvergensi yang lebih cepat ke elemen yang hilang. Efisiensi ini menjadi lebih jelas seiring dengan meningkatnya ukuran daftar input, membuat pencarian biner menjadi pilihan yang disukai ketika berhadapan dengan kumpulan data besar.

•	Simple Search	                                   
100 items -> 100 tebakan	       
4 miliar items -> 4 miliar tebakan	
O (n) -> linear time	                     

•	Binary Search
100 items -> 7 tebakan
4 miliar items -> 32 tebakan
O (log n) -> logaritmic time 2


	Big O Natation 
Big O Notation adalah salah satu konsep penting dalam ilmu komputer dan analisis algoritma yang digunakan untuk mengukur kinerja algoritma dan kompleksitas waktu. Notasi ini membantu kita memperkirakan berapa lama waktu yang dibutuhkan untuk menjalankan suatu algoritma dalam kaitannya dengan ukuran inputnya.
 


Big O Notation menggambarkan kinerja suatu algoritma dengan cara memperkirakan jumlah operasi yang diperlukan oleh algoritma untuk menyelesaikan suatu masalah dalam kaitannya dengan ukuran masukan (input). Notasi ini memberikan batasan atas (upper bound) kinerja algoritma dalam hal waktu eksekusi atau penggunaan memori.

	Algorithm running times grow at different rates:

Waktu berjalan dari sebuah algoritma tergantung pada jumlah iterasi yang harus dilakukan, atau berapa kali algoritma dijalankan sebelum sampai ke output akhir dan yang diinginkan.

Sebagai contoh, Diberikan satu set susunan bilangan bulat yang diurutkan, kita diminta untuk memberikan algoritma dengan pemeriksaan apakah angka x ada dalam susunan atau tidak. Lalu ada 2 algoritma yang paling umum digunakan untuk ini:

PENCARIAN LINEAR: Ini secara linier mencari setiap elemen dari array dari awal memeriksa nilai indeks array dengan x. Iterasi ini berlanjut sampai angka x tidak ditemukan. Jadi, kompleksitas waktu kasus terburuk adalah O(n) di mana n adalah jumlah elemen array. Yang berarti, jika komputer membutuhkan C detik untuk menjalankan satu pernyataan, maka dalam kasus terburuk waktu berjalan akan

N

.

C
Waktu berjalan dari sebuah algoritma tergantung pada jumlah iterasi yang harus dilakukan, atau berapa kali algoritma dijalankan sebelum sampai ke output akhir dan yang diinginkan.

Sebagai contoh, Diberikan satu set susunan bilangan bulat yang diurutkan, kita diminta untuk memberikan algoritma dengan pemeriksaan apakah angka x ada dalam susunan atau tidak. Lalu ada 2 algoritma yang paling umum digunakan untuk ini:

Detik.

PENCARIAN BINER: Dalam hal ini, susunan dipecah menjadi 3 bagian, satu bagian kiri, satu bagian kanan dan elemen tengah. Elemen tengah diperiksa dengan x dan jika ditemukan sama menampilkan outputnya. Jika x lebih kecil dari elemen tengah maka algoritma memeriksa bagian kiri dari array dengan cara yang sama. Jika x lebih besar dari bagian tengah, maka ia memeriksa bagian yang tepat. Dalam kasus ini kompleksitas waktu kasus terburuk adalah O(lg n). Dengan asumsi bahwa komputer membutuhkan waktu C detik untuk mengeksekusi satu pernyataan, total waktu berjalan dalam kasus ini untuk kasus terburuk adalah

C

.

Saya

G

(

N

)
Detik.
jadi, dalam dua kasus ini, untuk sejumlah input, jumlah iterasi dalam pencarian Biner akan selalu kurang dari jumlah iterasi dalam pencarian Linear. Oleh karena itu, waktu berjalan dari algoritma pencarian biner akan memakan waktu lebih sedikit daripada algoritma pencarian linier,


kesimpulan:
Misalkan kita memiliki sebuah array dengan panjang 'n' dan ingin mencari apakah suatu angka tertentu terdapat di dalamnya. Berikut adalah beberapa contoh kompleksitas waktu yang berbeda:
1.	Linear Search (Pencarian Linear):
o	Kompleksitas waktu: O(n)
o	Algoritma ini melakukan pencarian satu per satu dari awal array hingga menemukan elemen yang dicari atau mencapai akhir array.
2.	Binary Search (Pencarian Biner):
o	Kompleksitas waktu: O(log n)
o	Algoritma ini membagi array menjadi dua bagian dan mencari elemen di tengahnya. Dengan setiap iterasi, setengah dari array dieliminasi.
3.	Bubble Sort:
o	Kompleksitas waktu: O(n^2)
o	Algoritma ini membandingkan pasangan-pasangan elemen secara berurutan dan menukar mereka jika diperlukan, menghasilkan array yang terurut secara berurutan.
4.	Merge Sort: 
o	Kompleksitas waktu: O(n log n)
*Simple Search  cocok untuk data kecil atau tidak terurut.
- *Binary Search* efisien pada data terurut, tetapi persyaratan pengurutan bisa menjadi pembatas.
- *Big O Notation* membantu membandingkan kinerja algoritma secara abstrak dan memberikan indikasi pertumbuhan waktu algoritma seiring dengan pertambahan ukuran inputnya.







