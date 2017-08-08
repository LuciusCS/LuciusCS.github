---
layout: post
title: "线索化二叉树"
description: ""
type: data_structure
tags: [数据结构]
main: 
finish: true
modified: 2017-08-04

---

使用二叉树作为存储结构时，只能找到结点的左、右孩子的信息，而不能直接得到结点的前驱和后继的信息；

在有n个结点的二叉树中有n+1个空指针，利用这n+1个空指保存前驱和后继的信息；若结点有左子树，则其lChild指向其左孩子，否则指向其前驱；若结点有右子树，则其rChild指向其右孩子，否则指向其后继；为避免结点指向前驱与后继发生混淆，则在结点上增加两个标志域。

{% capture images %}
	/images/DataStructure/threaded_binary_tree.jpg
{% endcapture %}
{% include gallery images=images caption="" cols=1 %}

以这种结点结构构成的二叉链表作为二叉树的存储结构，叫做线索链表，其中指向结点的前驱和后继的指针叫做线索；加上线索的二叉树叫做线索二叉树（Threaded Binary Tree）

根据中序遍历的规律可知，结点的后继应是遍历其右子树时访问的第一个节点，即右子树最左下的结点；在中序线索树中找结点前驱的规律是：若其左标志位‘1’，则左链为线索，指示其前驱，否则遍历左子树最后访问的一个结点(左子树最右下的结点)为其前驱

