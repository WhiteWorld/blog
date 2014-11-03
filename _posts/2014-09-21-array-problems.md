---
layout: post
title: "线性表相关问题"
description: ""
category: "记录"
tags: [Array, Problem, LeetCode]
---
{% include JB/setup %}


[Remove Duplicates from Sorted Array](https://oj.leetcode.com/problems/remove-duplicates-from-sorted-array/)

{%highlight c++  linenos=table %}
#include <iostream>
using namespace std;

class Solution{
	public:
		int removeDuplicates(int A[], int n){
			if(n==0) return 0;
			int index=0;
			for(int i=1;i<n;i++){
				if(A[i]!=A[index])
					A[++index]=A[i];
			}
			return index+1;
		}

};

int main(){
	Solution s;
	int A[3] = {1, 2, 2};
	cout<<s.removeDuplicates(A, 3)<<endl;
	return 0;
}
{%endhighlight%}



[Remove Duplicates from Sorted Array II ](https://oj.leetcode.com/problems/remove-duplicates-from-sorted-array-ii/)

{%highlight c++  linenos=table %}
#include <iostream>
using namespace std;

class Solution{
	public:
		int removeDuplicates(int A[], int n){
			if(n==0 || n==1 || n==2) return n;
			int index=1;
			for(int i=2;i<n;i++){
				if(A[i]!=A[index-1])
					A[++index]=A[i];
			}
			return index+1;
		}

};

int main(){
	Solution s;
	int A[6] = {1, 1, 1, 2, 2, 3};
	cout<<s.removeDuplicates(A, 6)<<endl;
	return 0;
}
{%endhighlight%}

[Search in Rotated Sorted Array](https://oj.leetcode.com/problems/search-in-rotated-sorted-array/)

{%highlight c++  linenos=table %}
#include <iostream>
using namespace std;
class Solution{
	public:
		int search(int A[], int n, int target){
			int left = 0;
			int right = n;
			while(left < right){
				int mid = left+(right-left)/2;
				if(A[mid]==target)
					return mid;
				if(A[mid] >= A[left]){
					if(A[mid] < target || A[left]>target)
						left = mid+1;
					else if(A[mid]>target && A[left] <= target)
						right = mid;
				}else{
					if(A[mid]<target && target <= A[right-1])
						left = mid+1;
					else {
						right = mid;
					}
				}
			}
			return -1;
		}

};
int main(){
	Solution s;
	int A[] = {4,5,6,7,0,1,2};
	cout<<s.search(A, 7,7)<<endl;
	return 0;
}
{%endhighlight%}


[Search in Rotated Sorted Array II](https://oj.leetcode.com/problems/search-in-rotated-sorted-array-ii/)

{%highlight c++  linenos=table %}
#include <iostream>
using namespace std;

class Solution{
	public:
		bool search(int A[], int n, int target){
			int left = 0;
			int right = n;
			while(left < right){
				int mid = left+(right-left)/2;
				if(A[mid]==target)
					return true;
				if(A[mid]==A[left])
					left++;
				else if(A[mid] > A[left]){
					if(A[mid] < target || A[left]>target)
						left = mid+1;
					else
						right = mid;
				}else{
					if(A[mid]<target && target <= A[right-1])
						left = mid+1;
					else {
						right = mid;
					}
				}
			}
			return false;
		}

};


int main(){
	Solution s;
	int A[] = {4,5,6,7,0,1,2};
	cout<<s.search(A, 7,7)<<endl;
	return 0;
}
{%endhighlight%}

[Median of Two Sorted Arrays ](https://oj.leetcode.com/problems/median-of-two-sorted-arrays/)

{%highlight c++  linenos=table %}
class Solution{
	public:
		double findMedianSortedArrays(int A[], int m, int B[], int n){
			int total = m+n;
			if(total & 0x1)
				return find_kth(A, m, B, n, total/2 + 1);
			else
				return (find_kth(A, m, B, n, total/2)+find_kth(A, m, B, n, total/2+1))/2.0;
		
		}
	private:
		int find_kth(int A[], int m, int B[], int n, int k){
			if(m > n) return find_kth(B, n, A, m);
			if(m == 0) return B[k-1];
			if(k == 1) return min(A[0], B[0]);
			
			int ia = min(k/2, m), ib = k - ia;
			if(A[ia-1] < B[ib-1])
				return find_kth(A+ia, m-ia, B, n, k-ia);
			else if(A[ia-1] > B[ib-1])
				return find_kth(A, m, B+id, m-ib, k-ib);
			else
				return A[ia-1];
		}

};
{%endhighlight%}

