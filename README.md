// NAMA       : Salsabila Nur Aulia Safitri
// NRP        : 5022221005
// Jurusan    : Teknik Elektro

#include <iostream>
#include <cmath>
using namespace std;

#define GRAVITASI 10 //10 m/s^2
#define START_PENGUKURAN 1 //pengukuran dimulai dari 1 meter
#define SUDUT 45 //sudut elevasi tembakan

int mencari_V0(int i, int loss)
{
    /* Tulis fungsi mencari v0 kalian disini */
    i-=loss;
      return i;
}

int speed_dgn_loss(int i)
{
    /* tulis fungsi hitung_loss kalian disini */
    int hitung_loss;
        if(i>=1 && i<=10) {
            hitung_loss=1;
        }
        else if (i>=11 && i<=20){
            hitung_loss=3;
        }
        else if (i>=21 && i<=30){
            hitung_loss=5;
        }
    return hitung_loss;
}

int main() {
    /* tulis kode utama kalian disini */
  int i;
    float jarak, kecepatan_tangensial;
    cin>>i;
    jarak = (pow(mencari_V0 (i, speed_dgn_loss(i)),2)* sin(SUDUT*3.14159*2/180)/GRAVITASI)-START_PENGUKURAN;
    jarak = round (jarak);
    kecepatan_tangensial=sqrt (jarak*GRAVITASI/sin (SUDUT*3.14159*2/180)) + speed_dgn_loss(i);
    cout <<jarak<<" "<< kecepatan_tangensial << endl;
    
      /* input adalah kecepatan tangensial maksimum roller */
      /* std::cin >> input */
  
    
      /* std::cout << jarak << " " << kecepatan tangensial << std::endl */
    return 0;
}
