---
title: 文字列が数値を表しているかどうかを確認する方法 - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- numeric strings [C#]
- validating numeric input [C#]
- strings [C#], numeric
ms.assetid: a4e84e10-ea0a-489f-a868-503dded9d85f
ms.openlocfilehash: 15a21a6298f8f0a57e0189554246202b220dd259
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79157066"
---
# <a name="how-to-determine-whether-a-string-represents-a-numeric-value-c-programming-guide"></a><span data-ttu-id="9ed7f-102">文字列が数値を表しているかどうかを確認する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="9ed7f-102">How to determine whether a string represents a numeric value (C# Programming Guide)</span></span>
<span data-ttu-id="9ed7f-103">文字列が指定された数値型の有効な表現であるかどうかを確認するには、静的 `TryParse` メソッドを使用します。このメソッドには、すべてのプリミティブ数値型が実装されており、また <xref:System.DateTime>、<xref:System.Net.IPAddress> などの型も実装されています。</span><span class="sxs-lookup"><span data-stu-id="9ed7f-103">To determine whether a string is a valid representation of a specified numeric type, use the static `TryParse` method that is implemented by all primitive numeric types and also by types such as <xref:System.DateTime> and <xref:System.Net.IPAddress>.</span></span> <span data-ttu-id="9ed7f-104">次の例では、"108" が有効な [int](../../language-reference/builtin-types/integral-numeric-types.md) かどうかを確認する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9ed7f-104">The following example shows how to determine whether "108" is a valid [int](../../language-reference/builtin-types/integral-numeric-types.md).</span></span>  
  
```csharp  
int i = 0;
string s = "108";  
bool result = int.TryParse(s, out i); //i now = 108  
```  
  
 <span data-ttu-id="9ed7f-105">文字列が数値以外の文字、または指定した型で表すには大きすぎる (または小さすぎる) 数値の場合、`TryParse` は false を返し、out パラメーターを 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="9ed7f-105">If the string contains nonnumeric characters or the numeric value is too large or too small for the particular type you have specified, `TryParse` returns false and sets the out parameter to zero.</span></span> <span data-ttu-id="9ed7f-106">それ以外の場合は true を返し、out パラメーターを文字列の数値に設定します。</span><span class="sxs-lookup"><span data-stu-id="9ed7f-106">Otherwise, it returns true and sets the out parameter to the numeric value of the string.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ed7f-107">文字列が数値文字列だけを含んでいても、使用する `TryParse` メソッドの型として有効ではない場合があります。</span><span class="sxs-lookup"><span data-stu-id="9ed7f-107">A string may contain only numeric characters and still not be valid for the type whose `TryParse` method that you use.</span></span> <span data-ttu-id="9ed7f-108">たとえば、"256" は `byte` の有効値ではありませんが、`int` としては有効です。</span><span class="sxs-lookup"><span data-stu-id="9ed7f-108">For example, "256" is not a valid value for `byte` but it is valid for `int`.</span></span> <span data-ttu-id="9ed7f-109">" 98.6" は `int` の有効値ではありませんが、有効な `decimal` です。</span><span class="sxs-lookup"><span data-stu-id="9ed7f-109">"98.6" is not a valid value for `int` but it is a valid `decimal`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ed7f-110">例</span><span class="sxs-lookup"><span data-stu-id="9ed7f-110">Example</span></span>  
 <span data-ttu-id="9ed7f-111">次の例では、`TryParse` 値、`long` 値、および `byte` 値の文字列表現を指定して `decimal` を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9ed7f-111">The following examples show how to use `TryParse` with string representations of `long`, `byte`, and `decimal` values.</span></span>  
  
 [!code-csharp[csProgGuideStrings#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#14)]  
  
## <a name="robust-programming"></a><span data-ttu-id="9ed7f-112">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="9ed7f-112">Robust Programming</span></span>  
 <span data-ttu-id="9ed7f-113">プリミティブ数値型は、`Parse` 静的メソッドも実装します。このメソッドは、文字列が有効な数値でない場合は例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="9ed7f-113">Primitive numeric types also implement the `Parse` static method, which throws an exception if the string is not a valid number.</span></span> <span data-ttu-id="9ed7f-114">一般に、数値が有効でない場合は単に false を返す `TryParse` の方が効率的です。</span><span class="sxs-lookup"><span data-stu-id="9ed7f-114">`TryParse` is generally more efficient because it just returns false if the number is not valid.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="9ed7f-115">.NET Framework のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="9ed7f-115">.NET Framework Security</span></span>  
 <span data-ttu-id="9ed7f-116">テキスト ボックス、コンボ ボックスなどのコントロールからのユーザー入力を検証するには、常に `TryParse` メソッドまたは `Parse` メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="9ed7f-116">Always use the `TryParse` or `Parse` methods to validate user input from controls such as text boxes and combo boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ed7f-117">参照</span><span class="sxs-lookup"><span data-stu-id="9ed7f-117">See also</span></span>

- [<span data-ttu-id="9ed7f-118">バイト配列を int に変換する方法</span><span class="sxs-lookup"><span data-stu-id="9ed7f-118">How to convert a byte array to an int</span></span>](../types/how-to-convert-a-byte-array-to-an-int.md)
- [<span data-ttu-id="9ed7f-119">文字列を数値に変換する方法</span><span class="sxs-lookup"><span data-stu-id="9ed7f-119">How to convert a string to a number</span></span>](../types/how-to-convert-a-string-to-a-number.md)
- [<span data-ttu-id="9ed7f-120">16 進文字列と数値型の間で変換する方法</span><span class="sxs-lookup"><span data-stu-id="9ed7f-120">How to convert between hexadecimal strings and numeric types</span></span>](../types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)
- [<span data-ttu-id="9ed7f-121">数値文字列の解析</span><span class="sxs-lookup"><span data-stu-id="9ed7f-121">Parsing Numeric Strings</span></span>](../../../standard/base-types/parsing-numeric.md)
- [<span data-ttu-id="9ed7f-122">型の書式設定</span><span class="sxs-lookup"><span data-stu-id="9ed7f-122">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
