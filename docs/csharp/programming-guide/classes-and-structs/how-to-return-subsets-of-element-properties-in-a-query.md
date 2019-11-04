---
title: '方法: クエリで要素のプロパティのサブセットを返す - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
ms.openlocfilehash: 196383731507137bf4309d38d27b36f29b23a06c
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73419300"
---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a><span data-ttu-id="3a4be-102">方法: クエリで要素のプロパティのサブセットを返す (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="3a4be-102">How to: Return Subsets of Element Properties in a Query (C# Programming Guide)</span></span>
<span data-ttu-id="3a4be-103">次の両方の条件に当てはまる場合は、クエリ式に匿名型を使用します。</span><span class="sxs-lookup"><span data-stu-id="3a4be-103">Use an anonymous type in a query expression when both of these conditions apply:</span></span>  
  
- <span data-ttu-id="3a4be-104">各ソース要素のプロパティの一部のみを返したい。</span><span class="sxs-lookup"><span data-stu-id="3a4be-104">You want to return only some of the properties of each source element.</span></span>  
  
- <span data-ttu-id="3a4be-105">クエリを実行したメソッドのスコープ外のクエリ結果を保存する必要がない。</span><span class="sxs-lookup"><span data-stu-id="3a4be-105">You do not have to store the query results outside the scope of the method in which the query is executed.</span></span>  
  
 <span data-ttu-id="3a4be-106">各ソース要素の 1 つのプロパティまたはフィールドのみを返す場合は、`select` 句でドット演算子 (.) を使用します。</span><span class="sxs-lookup"><span data-stu-id="3a4be-106">If you only want to return one property or field from each source element, then you can just use the dot operator in the `select` clause.</span></span> <span data-ttu-id="3a4be-107">たとえば、各 `student` の `ID` のみを返すには、次のように `select` 句を記述します。</span><span class="sxs-lookup"><span data-stu-id="3a4be-107">For example, to return only the `ID` of each `student`, write the `select` clause as follows:</span></span>  
  
```csharp  
select student.ID;  
```  
  
## <a name="example"></a><span data-ttu-id="3a4be-108">例</span><span class="sxs-lookup"><span data-stu-id="3a4be-108">Example</span></span>  
 <span data-ttu-id="3a4be-109">次に、匿名型を使用して、各ソース要素のプロパティのうち、指定した条件に一致するプロパティのみを返す例を示します。</span><span class="sxs-lookup"><span data-stu-id="3a4be-109">The following example shows how to use an anonymous type to return only a subset of the properties of each source element that matches the specified condition.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#31)]  
  
 <span data-ttu-id="3a4be-110">名前を指定しない場合、匿名型にはプロパティのソース要素名が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3a4be-110">Note that the anonymous type uses the source element's names for its properties if no names are specified.</span></span> <span data-ttu-id="3a4be-111">匿名型のプロパティに新しい名前を付けるには、次のように `select` ステートメントを記述します。</span><span class="sxs-lookup"><span data-stu-id="3a4be-111">To give new names to the properties in the anonymous type, write the `select` statement as follows:</span></span>  
  
```csharp  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 <span data-ttu-id="3a4be-112">前の例でこの方法を試すには、`Console.WriteLine` ステートメントも次のように変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a4be-112">If you try this in the previous example, then the `Console.WriteLine` statement must also change:</span></span>  
  
```csharp  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3a4be-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="3a4be-113">Compiling the Code</span></span>  
  
<span data-ttu-id="3a4be-114">このコードを実行するには、クラスをコピーし、System.Linq に `using` ディレクティブを使用した C# コンソール アプリケーションに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="3a4be-114">To run this code, copy and paste the class into a C# console application  with a `using` directive for System.Linq.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3a4be-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a4be-115">See also</span></span>

- [<span data-ttu-id="3a4be-116">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="3a4be-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3a4be-117">匿名型</span><span class="sxs-lookup"><span data-stu-id="3a4be-117">Anonymous Types</span></span>](./anonymous-types.md)
- [<span data-ttu-id="3a4be-118">C# での LINQ</span><span class="sxs-lookup"><span data-stu-id="3a4be-118">LINQ in C#</span></span>](../../linq/index.md)
