#include<bits/stdc++.h>
using namespace std;
#define ll long long
const int N = 2e5+5;

int a[5] = {0,2,4,6,8};
int main(){
    ios::sync_with_stdio(false);
    cin.tie(nullptr);
    ll n;
    cin >> n;
    ll num = n;
    ll cnt = 0;
    string v;
    if(n <= 5){
        cout << a[n-1];
        return 0;
    }
    while(n > 0){
        v[cnt++] = n % 5 + '0';
        n /= 5; 
    }
    ll sum = 0;
    for(int i = 0;i < cnt;i++){
        if(v[i] == '0'){
            if(i == 0){
                v[i] = '5';
            }
            else{
                v[i] = '4';
            }
        }
        else{
            if(i == 0)break;
            else{
                int temp = v[i] - '0';
                temp -= 1;
                v[i] = temp + '0';
                break;
            } 
        }
    }
    for(int i = cnt - 1;i >= 0;i--){
        if(i > 0){
           sum = sum * 10 + a[v[i]-'0'];
        }
        else{
            sum = sum * 10 + a[(v[i]-'0')-1];
        }
    }
    cout << sum;
    return 0;
}


