---
title: 对数组使用 foreach - C# 编程指南
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: bb121b0f5d990ef6e596b34a45606e2abde6811a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705673"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a>对数组使用 foreach（C# 编程指南）

[foreach](../../language-reference/keywords/foreach-in.md) 语句提供一种简单、明了的方法来循环访问数组的元素。

对于单维数组，`foreach` 语句以递增索引顺序处理元素（从索引 0 开始并以索引 `Length - 1` 结束）：

 [!code-csharp[csProgGuideArrays#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#28)]

对于多维数组，遍历元素的方式为：首先增加最右边维度的索引，然后是它左边的一个维度，以此类推，向左遍历元素：

 [!code-csharp[csProgGuideArrays#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#29)]

但对于多维数组，使用嵌套的 [for](../../language-reference/keywords/for.md) 循环可以更好地控制处理数组元素的顺序。

## <a name="see-also"></a>另请参阅

- <xref:System.Array>
- [C# 编程指南](../index.md)
- [数组](index.md)
- [一维数组](single-dimensional-arrays.md)
- [多维数组](multidimensional-arrays.md)
- [交错数组](jagged-arrays.md)
