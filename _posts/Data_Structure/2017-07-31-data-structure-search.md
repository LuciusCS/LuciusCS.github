---
layout: post
title: "查找算法"
description: "插入排序"
type: data_structure
tags: [数据结构]
main: 
modified: 2017-07-31
image:
  feature: abstract-2.jpg
---

### 折半查找

折半查找即二分查找的实现

```c
int BinarySearch(int data[], int search,int length) {
	int end = length-1 ;
	int start = 0;
	int mid = (start + end) / 2;

	while (start<=end)
	{
		if (data[mid] == search)
		{
			return mid;
		}
		else if (data[mid] > search)
		{
			end = mid-1;
			mid = (start + end) / 2;
		}
		else
		{
			start = mid+1;
			mid = (start + end) / 2;
		}

	}
	return -1;

}

```