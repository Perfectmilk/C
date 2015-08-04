# C
C 
#import <Foundation/Foundation.h>

int main(int argc, const char * argv[]) {
    
    
    //随机10至30之间的随机数 10个 并排序
    /*
    unsigned int rd[10];
//    rd = arc4random()%51+50;
//    printf("%d",rd);
    
    int i = 0;
    while (i < 10) {
        rd[i] = arc4random()%21+10;
        i++;
    }
    
    for (i = 0; i < 9 ; i ++) {
        for (int j = 0; j < 9 - i; j++) {
            if (rd[j+1] > rd[j]) {
                rd[j] = rd[j]^rd[j + 1];
                rd[j + 1] = rd[j]^rd[j + 1];
                rd[j] = rd[j]^rd[j + 1];
            }
        }
    }
    
    for (int m = 0; m < 10 ; m ++) {
        printf("%d\n",rd[m]);
    }
     */
    
    
    // while 循环
//    while (条件表达式) {
//        语句;（循环体）
//    }
    
    //条件表达式的结果： 真 或 假
    
    // 输入10遍我爱你
    /*
    int count = 10;
    while (count) {
        printf("我爱你\n");
        count --;
    }
     */
    
    // 打印 6 到 12之间的数
    /*
    int sum = 6;
    while (sum < 13) {
        printf("%d\n",sum);
        sum ++;
    }
     */
    
    // 打印50 - 10 之间的数
    /*
    int sum_2 = 50;
    while (sum_2 > 9) {
        printf("%d\n",sum_2);
        sum_2 --;
    }
     */

    //打印 7的倍数
    /*
    int sum_3 = 1;
    while (sum_3 < 101) {
        if (sum_3 % 7 == 0) {
            printf("%d\n",sum_3);
        }
        sum_3 ++;
    }
     */
    
    // 1 到 100 之间的 ， 个位是7的数
    /*
    int sum_4 = 1;
    while (sum_4 < 101) {
        if (sum_4 % 10 == 7) {
            printf("%d\n",sum_4);
        }
        sum_4++;
    }
     */
    
    // 1 到 100 之间 ， 十位是7的数
    /*
    int sum_5 = 1;
    while (sum_5 < 101) {
        if (sum_5 / 10 == 7) {
            printf("%d\n",sum_5);
        }
        sum_5 ++;
    }
     */
    
    
    // 计算 1-5 之间的数字的和 1+2+3+4+5
    /*
    int sum = 0;
    int count = 1;
    
    while (count < 6) {
        sum = sum + count;
        count ++;
    }
    printf("%d\n",sum);
     */
    
    
#pragma mark -随机数
    arc4random(); //返回一个无符号的32位整形数字，如果用int接收，int的最高位为符号位，当符号位为1时，得到的就是负数。所以随机数要用%u打印  没有正负
    printf("%u\n",arc4random());
    
    //获取某范围的随机数
    // 1) 获取[0,b] 范围的随机数 , arc4random()%(b + 1), 余数 < 除数
    
    // 输出一个[0,10]之间的随机数
    printf("%u\n",arc4random()%(11));
    
    // 输出一个[20,40]之间的随机数
    printf("%u\n",arc4random()%21 + 20);
    
    // 要求从控制台输入一个数n ， 打印n个[10,20]之间的随机数
    /*
    int n = 0,i = 1;
    printf("请输入要打印随机数的个数:");
    scanf("%d",&n);
    
    while (i <= n) {
        printf("%u\n",arc4random()%11 + 10);
        i ++;
    }
     */
    
    //从控制台输入一个数，产生随机数，输出其中最小的数
    int i = 0;
    int n;
    int s[10] = {0};
    printf("请输入要打印随机数的个数:");
    scanf("%d",&n);
    
    while (i < n) {
        s[i] = arc4random()%21+30;
        i ++;
    }
    
    for (int k = 0; k < n - 1; k ++) {
        for (int m = 0; m < n - 1 -k; m ++) {
            if (s[m+1] > s[m]) {
                s[m] = s[m]^s[m+1];
                s[m+1] = s[m]^s[m+1];
                s[m] = s[m]^s[m+1];
            }
        }
    }
    
    for (int k = 0; k <= n - 1; k ++) {
        printf("%d\n",s[k]);
    }
    return 0;
}
