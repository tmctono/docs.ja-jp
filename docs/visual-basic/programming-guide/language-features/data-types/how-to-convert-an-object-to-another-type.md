---
title: '方法: オブジェクトを別の型に変換する'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: 6d16e0eafc3fa9233037abe0c92dcb1945ca8da9
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75341580"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a><span data-ttu-id="d9093-102">方法: Visual Basic でオブジェクトを別の型に変換する</span><span class="sxs-lookup"><span data-stu-id="d9093-102">How to: Convert an Object to Another Type in Visual Basic</span></span>
<span data-ttu-id="d9093-103">`Object` 変数を別のデータ型に変換するには、 [CType 関数](../../../../visual-basic/language-reference/functions/ctype-function.md)などの変換キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9093-103">You convert an `Object` variable to another data type by using a conversion keyword such as [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9093-104">使用例</span><span class="sxs-lookup"><span data-stu-id="d9093-104">Example</span></span>  
 <span data-ttu-id="d9093-105">次の例では、`Object` 変数を `Integer` と `String`に変換します。</span><span class="sxs-lookup"><span data-stu-id="d9093-105">The following example converts an `Object` variable to an `Integer` and a `String`.</span></span>  
  
```vb  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 <span data-ttu-id="d9093-106">`Object` 変数の内容が特定のデータ型であることがわかっている場合は、変数をそのデータ型に変換することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d9093-106">If you know that the contents of an `Object` variable are of a particular data type, it is better to convert the variable to that data type.</span></span> <span data-ttu-id="d9093-107">`Object` 変数を引き続き使用する場合は、*ボックス*化とボックス化*解除*(値型の場合) または*遅延バインディング*(参照型の場合) のいずれかが発生します。</span><span class="sxs-lookup"><span data-stu-id="d9093-107">If you continue to use the `Object` variable, you incur either *boxing* and *unboxing* (for a value type) or *late binding* (for a reference type).</span></span> <span data-ttu-id="d9093-108">これらの操作はすべて、追加の実行時間がかかり、パフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="d9093-108">These operations all take extra execution time and make your performance slower.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="d9093-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="d9093-109">Compile the code</span></span>  
 <span data-ttu-id="d9093-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d9093-110">This example requires:</span></span>  
  
- <span data-ttu-id="d9093-111"><xref:System?displayProperty=nameWithType> 名前空間への参照</span><span class="sxs-lookup"><span data-stu-id="d9093-111">A reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9093-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9093-112">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="d9093-113">Visual Basic における型変換</span><span class="sxs-lookup"><span data-stu-id="d9093-113">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="d9093-114">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="d9093-114">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="d9093-115">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="d9093-115">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="d9093-116">文字列とその他の型との変換</span><span class="sxs-lookup"><span data-stu-id="d9093-116">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="d9093-117">配列変換</span><span class="sxs-lookup"><span data-stu-id="d9093-117">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [<span data-ttu-id="d9093-118">構造体</span><span class="sxs-lookup"><span data-stu-id="d9093-118">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="d9093-119">データの種類</span><span class="sxs-lookup"><span data-stu-id="d9093-119">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="d9093-120">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="d9093-120">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
