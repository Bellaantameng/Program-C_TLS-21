/******************************************************************************
                            Program Kasir Manual 
                      Oleh: Bellatrix Gracia Antameng

*******************************************************************************/

#include <iostream>
#include <string>
#include <iomanip>
using namespace std;
int main() 
{
	
	int jumlah_beli, bayar,diskon,jumlah[50], harga[50], sub_tot[50];
	string nama_barang[50];
	float tot;
	
	cout<<"PROGRAM KASIR"<<endl;
	cout<<"---------------------------"<<endl;
	cout<<endl;
	
	//Memasukan jumlah beli (dihitung berdasarkan banyaknya jenis barang yang dibeli)
	cout<<"Jumlah Beli Barang "<<endl;
	cout<<"*Dihitung berdasarkan banyaknya jenis barang yang dibeli"<<endl;
	cout<<"Masukkan Jumlah Beli Barang  : ";
	cin>>jumlah_beli; 
	
	for (int i=0; i<jumlah_beli;i++)
	{
		cout<<endl;
		cout<<"Masukan Barang Ke-"<<i+1<<endl;
		cout<<endl;
	
		//Pengguna input nama barang disimpan pada array nama_barang
		cout<<"Nama-nama Barang "<<endl;
		cout<<"*Apabila nama barang lebih dari 1 kata, gunakan '_' sebagai pengganti spasi"<<endl;
		cout<<"Nama Barang              : ";
		cin>>nama_barang[i];
		
		
		//Pengguna input jumlah disimpan pada array jumlah
		cout<<"Jumlah                   : ";
		cin>>jumlah[i]; 
		
		//Pengguna input harga disimpan pada array harga
		cout<<"Harga                    : ";
		cin>>harga[i]; 
		
		// Menjumlahkan Harga sub total barang
		sub_tot[i]=jumlah[i]*harga[i]; 
		//Menjumlahkan seluruh sub total barang
		tot+=sub_tot[i]; 
	}
	
	cout<<endl;
	cout<<"STRUK BELANJA MINI MARKET ABC"<<endl;
	cout<<"---------------------------------------------------------"<<endl;
	cout<<"No   Barang    Jumlah     Harga     Sub Total"<<endl;
	for (int i=0;i<jumlah_beli;i++){
		cout<<i+1<<setw(8)<<nama_barang[i]<<setw(10)<<jumlah[i]<<setw(12)<<harga[i]<<setw(12)<<sub_tot[i]<<endl; //Menampilkan semua nilai array
	}
	cout<<"---------------------------------------------------------"<<endl;

	//Kondisi untuk menentukan diskon yang didapatkan berdasarkan total belanja
	if (tot>=100000){
		diskon=0.06*tot;
	} else if (tot>=50000){
		diskon=0.04;
	}else if (tot>=25000){
		diskon=0.02;
	}else {
		diskon=0;
	}
	
	//Menampilkan Keterangan
	//Menampilkan jumlah bayar (belum termasuk diskon)
	cout<<"Jumlah Bayar : Rp."<<tot<<endl;
	//Menampilkan diskon
	cout<<"diskon        : Rp."<<diskon<<endl; 
	//Menampilkan total harga yang harus dibayar
	cout<<"Total Bayar  : Rp."<<tot-diskon<<endl;
	// Input dari user untuk jumlah yang dibayar
	cout<<"Bayar        : Rp.";
	cin>>bayar; 
	cout<<"Kembali      : Rp."<<(bayar-(tot-diskon))<<endl; // Menampilkan uang kembali
	
}
