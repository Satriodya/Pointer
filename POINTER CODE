#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_LENGTH 2024
#define MIN_LENGTH 1945

void kurangDariDibutuhkan(int *panjangTeks){
    printf("Panjang teks kurang dari yang ditentukan, harap perbarui teks Anda\n");
    printf("Panjang Sebelumnya: %d\n", *panjangTeks);
    *panjangTeks = MIN_LENGTH;
}

void samaDenganDibutuhkan(int *panjangTeks){
    printf("Terima kasih, panjang teks Anda sudah sesuai\n");
}

void lebihDariDibutuhkan(int *panjangTeks){
    printf("Teks Anda terlalu panjang, harap kurangi teksnya\n");
    printf("Panjang Sebelumnya: %d\n", *panjangTeks);
    *panjangTeks = MIN_LENGTH;
}

int periksaKebutuhanPanjang(char* teks){
    int panjang = strlen(teks);
    if (panjang < MIN_LENGTH)
        return 0;
    else if (panjang == MIN_LENGTH)
        return 1;
    else
        return 2;
}

int main() {
    int panjangTeks, pilihan;
    FILE *fptr = NULL;
    char teks[MAX_LENGTH];

    fptr = fopen("file.txt", "r");

    if(fptr == NULL){
        printf("Error: Tidak dapat membuka file\n");
        exit(1);
    }

    fgets(teks, MAX_LENGTH, fptr);

    fclose(fptr);

    pilihan = periksaKebutuhanPanjang(teks);

    void (*fungsi[3])(int *) = {kurangDariDibutuhkan, samaDenganDibutuhkan, lebihDariDibutuhkan};
    fungsi[pilihan](&panjangTeks);

    printf("\nPanjang Telah Diperbarui Menjadi %d", panjangTeks);

    return 0;
}
