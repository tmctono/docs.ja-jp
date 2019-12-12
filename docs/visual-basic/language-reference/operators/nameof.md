---
title: Visual Basic の NameOf 演算子
description: Visual Basic での参照演算子の使用方法について説明します。
ms.date: 10/27/2019
helpviewer_keywords:
- NameOf operator [Visual Basic]
ms.openlocfilehash: 8416bb1a1715c1c37b62cac6a9e0b427a9c72547
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73041353"
---
# <a name="nameof-operator---visual-basic"></a><span data-ttu-id="2114a-103">Visual Basic の NameOf 演算子</span><span class="sxs-lookup"><span data-stu-id="2114a-103">NameOf operator - Visual Basic</span></span>

<span data-ttu-id="2114a-104">`NameOf` 演算子を使うと、変数、型、またはメンバーの名前を文字列定数として取得できます。</span><span class="sxs-lookup"><span data-stu-id="2114a-104">The `NameOf` operator obtains the name of a variable, type, or member as the string constant:</span></span>

```vb
Console.WriteLine(NameOf(System.Collections.Generic))  ' output: Generic
Console.WriteLine(NameOf(List(Of Integer)))  ' output: List
Console.WriteLine(NameOf(List(Of Integer).Count))  ' output: Count
Console.WriteLine(NameOf(List(Of Integer).Add))  ' output: Add

Dim numbers As New List(Of Integer) From { 1, 2, 3 }
Console.WriteLine(NameOf(numbers))  ' output: numbers
Console.WriteLine(NameOf(numbers.Count))  ' output: Count
Console.WriteLine(NameOf(numbers.Add))  ' output: Add
```

<span data-ttu-id="2114a-105">前の例で示されているように、型と名前空間の場合、生成される名前は通常[完全修飾](~/_csharplang/spec/basic-concepts.md#fully-qualified-names)ではありません。</span><span class="sxs-lookup"><span data-stu-id="2114a-105">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="2114a-106">`NameOf` 演算子はコンパイル時に評価され、実行時には影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="2114a-106">The `NameOf` operator is evaluated at compile time, and has no effect at run time.</span></span>

<span data-ttu-id="2114a-107">`NameOf` 演算子を使って、引数をチェックするコードを保守しやすくすることができます。</span><span class="sxs-lookup"><span data-stu-id="2114a-107">You can use the `NameOf` operator to make the argument-checking code more maintainable:</span></span>

```vb
Private _name As String

Public Property Name As String
    Get
        Return _name
    End Get
    Set
        If value Is Nothing Then
            Throw New ArgumentNullException(NameOf(value), $"{NameOf(name)} cannot be null.")
        End If
    End Set
End Property
```

<span data-ttu-id="2114a-108">`NameOf` 演算子は Visual Basic 14 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="2114a-108">The `NameOf` operator is available in Visual Basic 14 and later.</span></span>

## <a name="see-also"></a><span data-ttu-id="2114a-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="2114a-109">See also</span></span>

- [<span data-ttu-id="2114a-110">Visual Basic の言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="2114a-110">Visual Basic Language Reference</span></span>](../index.md)
- [<span data-ttu-id="2114a-111">演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2114a-111">Operators (Visual Basic)</span></span>](index.md)
