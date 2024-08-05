#pragma GCC optimize("O3,unroll-loops")
#pragma GCC target("avx2,bmi,bmi2,lzcnt,popcnt")
 
#include <bits/stdc++.h>
#include <set>
using namespace std;

long long dapan(long long a, long long arr[1000000]){
	long long b;
	long long count = 0;
	for(long long i=a;i<b;i++){
		if(arr[i]%2==0){
			count++;
		}
	}
	long long emax = 0;
	for(long long i=0;i<a;i++){
		if(arr[i]%2==0&&arr[i]>emax){
			emax = arr[i];
		}
	}
	long long omax = 0;
	for(long long i=0;i<a;i++){
		if(arr[i]%2==1&&arr[i]>omax){
			omax = arr[i];
		}
	}
	long long sum=0;
    for (long i=0;i<a;i++){
        if (arr[i]%2==0){
            sum += arr[i];
        }
    }
	long long ecount=0;
	for(long i=0;i<a;i++){
		if(arr[i]%2==0){
		ecount++;	
		}
	}
	long long ocount=0;
	for(long long i=0;i<a;i++){
		if(arr[i]%2!=0){
		ocount++;	
		}
	}
	if(ecount==0||ocount==0){
       return 0;
	}
	else{
		long long sum=0;
    for (int i=0;i<a;i++){
        if (arr[i]%2==0){
            sum += arr[i];
        }
    }
    long long countt=0;
    for(long long i=0;i<a;i++)
    	if(arr[i]>omax-emax+sum){
    		if(arr[i]%2==0){
    		countt++;
		}
	}
	return count+countt;
}
	}
	
int main(){
	std::ios::sync_with_stdio(false);
	cin.tie(NULL);
	long long a;
	cin >> a;
	long long ans[a-1];
	for(long long i=0;i<a;i++){
		long long sophantu;
		cin >> sophantu;
		long long arr[sophantu+1];
	for(long long j=0;j<sophantu;j++){
		cin >> arr[j];
		}
		ans[i] = dapan(sophantu,arr); 
	}
	for(long long i=0;i<a;i++){
		cout << ans[i] << endl;
	}
}	
