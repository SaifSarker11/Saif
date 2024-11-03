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
