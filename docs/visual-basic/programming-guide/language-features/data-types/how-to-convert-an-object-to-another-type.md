---
title: '方法: オブジェクトを別の型に変換する'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: cdb78bc66867ce27076d7b7e42de6a2880cb3a8c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393962"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a><span data-ttu-id="5f7a9-102">方法: Visual Basic でオブジェクトを別の型に変換する</span><span class="sxs-lookup"><span data-stu-id="5f7a9-102">How to: Convert an Object to Another Type in Visual Basic</span></span>
<span data-ttu-id="5f7a9-103">[CType 関数](../../../language-reference/functions/ctype-function.md)などの変換キーワードを使用して、`Object` 変数を別のデータ型に変換します。</span><span class="sxs-lookup"><span data-stu-id="5f7a9-103">You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../language-reference/functions/ctype-function.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f7a9-104">例</span><span class="sxs-lookup"><span data-stu-id="5f7a9-104">Example</span></span>  
 <span data-ttu-id="5f7a9-105">次の例では、`Object` 変数を `Integer` と `String` に変換します。</span><span class="sxs-lookup"><span data-stu-id="5f7a9-105">The following example converts an `Object` variable to an `Integer` and a `String`.</span></span>  
  
```vb  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 <span data-ttu-id="5f7a9-106">`Object` 変数の内容が特定のデータ型であることがわかっている場合は、変数をそのデータ型に変換することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5f7a9-106">If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type.</span></span> <span data-ttu-id="5f7a9-107">`Object` 変数を引き続き使用すると、"*ボックス化*" と "*ボックス化解除*" (値型の場合) または "*遅延バインディング*" (参照型の場合) のいずれかが発生します。</span><span class="sxs-lookup"><span data-stu-id="5f7a9-107">If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type).</span></span> <span data-ttu-id="5f7a9-108">これらの処理にはすべて追加の実行時間がかかり、パフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="5f7a9-108">These operations all take extra execution time and make your performance slower.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="5f7a9-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="5f7a9-109">Compile the code</span></span>  
 <span data-ttu-id="5f7a9-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5f7a9-110">This example requires:</span></span>  
  
- <span data-ttu-id="5f7a9-111"><xref:System?displayProperty=nameWithType> 名前空間への参照</span><span class="sxs-lookup"><span data-stu-id="5f7a9-111">A reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f7a9-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f7a9-112">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="5f7a9-113">Visual Basic における型変換</span><span class="sxs-lookup"><span data-stu-id="5f7a9-113">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="5f7a9-114">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="5f7a9-114">Widening and Narrowing Conversions</span></span>](widening-and-narrowing-conversions.md)
- [<span data-ttu-id="5f7a9-115">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="5f7a9-115">Implicit and Explicit Conversions</span></span>](implicit-and-explicit-conversions.md)
- [<span data-ttu-id="5f7a9-116">文字列とその他の型との変換</span><span class="sxs-lookup"><span data-stu-id="5f7a9-116">Conversions Between Strings and Other Types</span></span>](conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="5f7a9-117">配列変換</span><span class="sxs-lookup"><span data-stu-id="5f7a9-117">Array Conversions</span></span>](array-conversions.md)
- [<span data-ttu-id="5f7a9-118">構造体</span><span class="sxs-lookup"><span data-stu-id="5f7a9-118">Structures</span></span>](structures.md)
- [<span data-ttu-id="5f7a9-119">データの種類</span><span class="sxs-lookup"><span data-stu-id="5f7a9-119">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="5f7a9-120">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="5f7a9-120">Type Conversion Functions</span></span>](../../../language-reference/functions/type-conversion-functions.md)
