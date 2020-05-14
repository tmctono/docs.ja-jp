---
title: 型パラメーターのデータ型を、これらの引数から推論することはできません
ms.date: 07/20/2015
f1_keywords:
- bc36644
- bc36647
- vbc36647
- vbc36644
helpviewer_keywords:
- BC36644
- BC36647
ms.assetid: 0e0050f2-2039-4311-b260-f0ebfde84189
ms.openlocfilehash: 97b03874489473482554078958c7bfd29d87c095
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523993"
---
# <a name="data-types-of-the-type-parameters-cannot-be-inferred-from-these-arguments"></a><span data-ttu-id="d63a0-102">型パラメーターのデータ型を、これらの引数から推論することはできません</span><span class="sxs-lookup"><span data-stu-id="d63a0-102">Data type(s) of the type parameter(s) cannot be inferred from these arguments</span></span>

<span data-ttu-id="d63a0-103">型パラメーターのデータ型を、これらの引数から推論することはできません。</span><span class="sxs-lookup"><span data-stu-id="d63a0-103">Data type(s) of the type parameter(s) cannot be inferred from these arguments.</span></span> <span data-ttu-id="d63a0-104">データ型を明示的に指定すると、このエラーが修正される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d63a0-104">Specifying the data type(s) explicitly might correct this error.</span></span>

<span data-ttu-id="d63a0-105">このエラーは、オーバーロードの解決法が失敗したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d63a0-105">This error occurs when overload resolution has failed.</span></span> <span data-ttu-id="d63a0-106">これは、特定のオーバーロード候補が削除された理由を示す従属メッセージとして発生します。</span><span class="sxs-lookup"><span data-stu-id="d63a0-106">It occurs as a subordinate message that states why a particular overload candidate has been eliminated.</span></span> <span data-ttu-id="d63a0-107">エラー メッセージには、コンパイラが型の推定を使用して、型パラメーターのデータ型を検索できないことが説明されます。</span><span class="sxs-lookup"><span data-stu-id="d63a0-107">The error message explains that the compiler cannot use type inference to find data types for the type parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="d63a0-108">引数の指定がオプションではない場合 (たとえば、クエリ式内のクエリ演算子など)、エラー メッセージの 2 つ目の文は表示されません。</span><span class="sxs-lookup"><span data-stu-id="d63a0-108">When specifying arguments is not an option (for example, for query operators in query expressions), the error message appears without the second sentence.</span></span>

<span data-ttu-id="d63a0-109">次のコードはエラーを示しています。</span><span class="sxs-lookup"><span data-stu-id="d63a0-109">The following code demonstrates the error.</span></span>

```vb
Module Module1

    Sub Main()

        '' Not Valid.
        'OverloadedGenericMethod("Hello", "World")

    End Sub

    Sub OverloadedGenericMethod(Of T)(ByVal x As String,
                                      ByVal y As InterfaceExample(Of T))
    End Sub

    Sub OverloadedGenericMethod(Of T, R)(ByVal x As T,
                                         ByVal y As InterfaceExample(Of R))
    End Sub

End Module

Interface InterfaceExample(Of T)
End Interface
```

<span data-ttu-id="d63a0-110">**エラー ID:** BC36647 と BC36644</span><span class="sxs-lookup"><span data-stu-id="d63a0-110">**Error ID:** BC36647 and BC36644</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d63a0-111">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="d63a0-111">To correct this error</span></span>

<span data-ttu-id="d63a0-112">型の推定に依存せずに、型パラメーターまたはパラメーターのデータ型を指定できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d63a0-112">You may be able to specify a data type for the type parameter or parameters instead of relying on type inference.</span></span>

## <a name="see-also"></a><span data-ttu-id="d63a0-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="d63a0-113">See also</span></span>

- [<span data-ttu-id="d63a0-114">厳密でないデリゲート変換</span><span class="sxs-lookup"><span data-stu-id="d63a0-114">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="d63a0-115">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d63a0-115">Generic Procedures in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)
- [<span data-ttu-id="d63a0-116">Visual Basic における型変換</span><span class="sxs-lookup"><span data-stu-id="d63a0-116">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
