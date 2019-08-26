---
title: '方法: 文字列が数値を表しているかどうかを確認する - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- numeric strings [C#]
- validating numeric input [C#]
- strings [C#], numeric
ms.assetid: a4e84e10-ea0a-489f-a868-503dded9d85f
ms.openlocfilehash: 831f0fc83c8a7066b40d64e4765a312b8b4847bc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921777"
---
# <a name="how-to-determine-whether-a-string-represents-a-numeric-value-c-programming-guide"></a><span data-ttu-id="366c5-102">方法: 文字列が数値を表しているかどうかを確認する (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="366c5-102">How to: Determine Whether a String Represents a Numeric Value (C# Programming Guide)</span></span>
<span data-ttu-id="366c5-103">文字列が指定された数値型の有効な表現であるかどうかを確認するには、静的 `TryParse` メソッドを使用します。このメソッドには、すべてのプリミティブ数値型が実装されており、また <xref:System.DateTime>、<xref:System.Net.IPAddress> などの型も実装されています。</span><span class="sxs-lookup"><span data-stu-id="366c5-103">To determine whether a string is a valid representation of a specified numeric type, use the static `TryParse` method that is implemented by all primitive numeric types and also by types such as <xref:System.DateTime> and <xref:System.Net.IPAddress>.</span></span> <span data-ttu-id="366c5-104">次の例では、"108" が有効な [int](../../language-reference/builtin-types/integral-numeric-types.md) かどうかを確認する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="366c5-104">The following example shows how to determine whether "108" is a valid [int](../../language-reference/builtin-types/integral-numeric-types.md).</span></span>  
  
```  
int i = 0;   
string s = "108";  
bool result = int.TryParse(s, out i); //i now = 108  
```  
  
 <span data-ttu-id="366c5-105">文字列が数値以外の文字、または指定した型で表すには大きすぎる (または小さすぎる) 数値の場合、`TryParse` は false を返し、out パラメーターを 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="366c5-105">If the string contains nonnumeric characters or the numeric value is too large or too small for the particular type you have specified, `TryParse` returns false and sets the out parameter to zero.</span></span> <span data-ttu-id="366c5-106">それ以外の場合は true を返し、out パラメーターを文字列の数値に設定します。</span><span class="sxs-lookup"><span data-stu-id="366c5-106">Otherwise, it returns true and sets the out parameter to the numeric value of the string.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="366c5-107">文字列が数値文字列だけを含んでいても、使用する `TryParse` メソッドの型として有効ではない場合があります。</span><span class="sxs-lookup"><span data-stu-id="366c5-107">A string may contain only numeric characters and still not be valid for the type whose `TryParse` method that you use.</span></span> <span data-ttu-id="366c5-108">たとえば、"256" は `byte` の有効値ではありませんが、`int` としては有効です。</span><span class="sxs-lookup"><span data-stu-id="366c5-108">For example, "256" is not a valid value for `byte` but it is valid for `int`.</span></span> <span data-ttu-id="366c5-109">" 98.6" は `int` の有効値ではありませんが、有効な `decimal` です。</span><span class="sxs-lookup"><span data-stu-id="366c5-109">"98.6" is not a valid value for `int` but it is a valid `decimal`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="366c5-110">例</span><span class="sxs-lookup"><span data-stu-id="366c5-110">Example</span></span>  
 <span data-ttu-id="366c5-111">次の例では、`long` 値、`byte` 値、および `decimal` 値の文字列表現を指定して `TryParse` を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="366c5-111">The following examples show how to use `TryParse` with string representations of `long`, `byte`, and `decimal` values.</span></span>  
  
 [!code-csharp[csProgGuideStrings#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#14)]  
  
## <a name="robust-programming"></a><span data-ttu-id="366c5-112">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="366c5-112">Robust Programming</span></span>  
 <span data-ttu-id="366c5-113">プリミティブ数値型は、`Parse` 静的メソッドも実装します。このメソッドは、文字列が有効な数値でない場合は例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="366c5-113">Primitive numeric types also implement the `Parse` static method, which throws an exception if the string is not a valid number.</span></span> <span data-ttu-id="366c5-114">一般に、数値が有効でない場合は単に false を返す `TryParse` の方が効率的です。</span><span class="sxs-lookup"><span data-stu-id="366c5-114">`TryParse` is generally more efficient because it just returns false if the number is not valid.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="366c5-115">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="366c5-115">.NET Framework Security</span></span>  
 <span data-ttu-id="366c5-116">テキスト ボックス、コンボ ボックスなどのコントロールからのユーザー入力を検証するには、常に `TryParse` メソッドまたは `Parse` メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="366c5-116">Always use the `TryParse` or `Parse` methods to validate user input from controls such as text boxes and combo boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="366c5-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="366c5-117">See also</span></span>

- [<span data-ttu-id="366c5-118">方法: バイト配列を int に変換する</span><span class="sxs-lookup"><span data-stu-id="366c5-118">How to: Convert a byte Array to an int</span></span>](../types/how-to-convert-a-byte-array-to-an-int.md)
- [<span data-ttu-id="366c5-119">方法: 文字列を数値に変換する</span><span class="sxs-lookup"><span data-stu-id="366c5-119">How to: Convert a String to a Number</span></span>](../types/how-to-convert-a-string-to-a-number.md)
- [<span data-ttu-id="366c5-120">方法: 16 進文字列と数値型の間で変換する</span><span class="sxs-lookup"><span data-stu-id="366c5-120">How to: Convert Between Hexadecimal Strings and Numeric Types</span></span>](../types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)
- [<span data-ttu-id="366c5-121">数値文字列の解析</span><span class="sxs-lookup"><span data-stu-id="366c5-121">Parsing Numeric Strings</span></span>](../../../standard/base-types/parsing-numeric.md)
- [<span data-ttu-id="366c5-122">型の書式設定</span><span class="sxs-lookup"><span data-stu-id="366c5-122">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
