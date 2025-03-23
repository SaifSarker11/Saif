// Tree Pattern Printing
#include<stdio.h>
int main(){
    int n;
    printf("Enter the value of n: ");
    scanf("%d", &n);
    for(int i = 1; i <= n - 1; i++){
        for(int j = 1; j <= n - 1 - i; j++) printf(" ");
        for(int j = 1; j <= 2*i - 1; j++) printf("*");
        printf("\n");
    }
    for(int i = 1; i <= 1; i++){
        for(int j = 1; j <= n - 2*i; j++) printf(" ");
        for(int j = 1; j <= 1; j++) printf("*");
        printf("\n");
    }
    return 0;
}

// Simple Moving Average
#include<stdio.h>
#include<math.h>
double* AvgFilter(double* signal, int slen, int len, double* smoothedSignal){
    int half_length = len / 2;
    double sum[slen];
    for(int i = 0; i < slen; i++){
        sum[i] = 0.0;
    }
    for(int i = 0; i < slen; i++){
        for(int j = -half_length; j <= half_length; j++){
            if(i + j >= 0 && i + j < slen){
                sum[i] += signal[i + j];
            }
        }
        smoothedSignal[i] = sum[i] / (double)len;
    }
    return smoothedSignal;
}
int main(){
    int slength;
    printf("Enter signal length: ");
    scanf("%d", &slength);
    printf("Enter signal: ");
    double signal[slength];
    double smoothedSignal[slength];
    for(int i = 0; i < slength; i++){
        scanf("%lf", &signal[i]);
    }
    int flength;
    printf("Enter filter length: ");
    scanf("%d", &flength);
    double* result_array = AvgFilter(signal, slength, flength, smoothedSignal);
    printf("Smoothed Signal: ");
    for(int i = 0; i < slength; i++){
        printf("%.4lf   ", result_array[i]);
    }
    printf("\n");
    return 0;
}
