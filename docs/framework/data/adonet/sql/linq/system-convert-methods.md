---
title: System.Convert メソッド
ms.date: 03/30/2017
ms.assetid: 3ca6c5b6-ea5d-4ab0-b675-f082135b342c
ms.openlocfilehash: 9836820f2c084a80fcc0a4856f20597716344dfd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61877033"
---
# <a name="systemconvert-methods"></a><span data-ttu-id="0c143-102">System.Convert メソッド</span><span class="sxs-lookup"><span data-stu-id="0c143-102">System.Convert Methods</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="0c143-103">は、次の <xref:System.Convert> メソッドをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0c143-103">does not support the following <xref:System.Convert> methods.</span></span>

- <span data-ttu-id="0c143-104"><xref:System.IFormatProvider> パラメーターを持つ形式。</span><span class="sxs-lookup"><span data-stu-id="0c143-104">Versions with an <xref:System.IFormatProvider> parameter.</span></span>

- <span data-ttu-id="0c143-105">文字配列またはバイト配列を扱うメソッド。</span><span class="sxs-lookup"><span data-stu-id="0c143-105">Methods that involve char arrays or byte arrays:</span></span>

  - <xref:System.Convert.FromBase64CharArray%2A>

  - <xref:System.Convert.ToBase64CharArray%2A>

  - <xref:System.Convert.FromBase64String%2A>

  - <xref:System.Convert.ToBase64String%2A>

- <span data-ttu-id="0c143-106">次のメソッド。</span><span class="sxs-lookup"><span data-stu-id="0c143-106">The following methods:</span></span>

  - <span data-ttu-id="0c143-107">`public static <Type2> To<Type2>(<Type1> value);` (</span><span class="sxs-lookup"><span data-stu-id="0c143-107">`public static <Type2> To<Type2>(<Type1> value);` where</span></span>

    <span data-ttu-id="0c143-108">`Type1` および `Type2` は `sbyte`、`uint`、`ulong`、`ushort` のいずれか)</span><span class="sxs-lookup"><span data-stu-id="0c143-108">`Type1` and `Type2` are each one of `sbyte`, `uint`, `ulong`, or `ushort`.</span></span>

  - <span data-ttu-id="0c143-109">C#: </span><span class="sxs-lookup"><span data-stu-id="0c143-109">C#:</span></span>

    `int To<int type>(string value, int fromBase),`

    `ToString(... value, int toBase)`

  - <span data-ttu-id="0c143-110">Visual Basic: </span><span class="sxs-lookup"><span data-stu-id="0c143-110">Visual Basic:</span></span>

    `Function To(Of [Numeric])(value as String, fromBase As Integer)`

    `As [Numeric], ToString( value As …, toBase As Integer)`

  - <xref:System.Convert.IsDBNull%2A>

  - <xref:System.Convert.GetTypeCode%2A>

  - <xref:System.Convert.ChangeType%2A>

## <a name="see-also"></a><span data-ttu-id="0c143-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c143-111">See also</span></span>

- [<span data-ttu-id="0c143-112">データ型と関数</span><span class="sxs-lookup"><span data-stu-id="0c143-112">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
