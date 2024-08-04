# contest-B-solution
#pragma GCC optimize("O3,unroll-loops")
#pragma GCC target("avx2,bmi,bmi2,lzcnt,popcnt")
 
#include <bits/stdc++.h>
#include <set>
using namespace std;
 
int main(){
	std::ios::sync_with_stdio(false);
	cin.tie(NULL);
    int n;
	int arr[n];
    cin>>n;
    int count=0;
    for(int i=0;i<n;i++){
    	cin>>arr[i];
	}
	int a=0;
	for(int i=0;i<n;i++){
		if(arr[i]%2==0){
		a++;	
		}
	}
	if(a==n){
		cout<<0;
	}
	int b=0;
	for(int i=0;i<n;i++){
		if(arr[i]%2!=0){
		b++;	
		}
	}
	if(b==n){
		cout<<0;
	}
	for(int i=0;i<n;i++){
		if(arr[i]%2==0)
		count++;
	}
	return 0;
	int omax=arr[0];
    for(int i=0;i<n;i++){
    	if(arr[i]%2!=0){
        if(arr[i]>omax){
            omax=arr[i];
        }
    }
    }
    int emax=arr[0];
    for(int i=0;i<n;i++){
    	if(arr[i]%2==0){
        if(arr[i]>emax){
            emax=arr[i];
        }
    }
    }
    int sum=0;
    for (int i=0;i<n;i++){
        if (arr[i]%2==0){
            sum += arr[i];
        }
    }
    int countt=0;
    for(int i=0;i<n;i++)
    	if(arr[i]>omax-emax+sum){
    		if(arr[i]%2==0){
    		countt++;
		}
	}
	cout<<count+countt;
}
