---
title: 方法:文字列内の文字をクエリする (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: 727a1be7-dbec-4ab8-b414-bc2d56feb6ff
ms.openlocfilehash: 1212ebcf264aab756eca1acb81ae617c2218a065
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69592892"
---
# <a name="how-to-query-for-characters-in-a-string-linq-c"></a><span data-ttu-id="ca88e-102">方法:文字列内の文字をクエリする (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="ca88e-102">How to: Query for Characters in a String (LINQ) (C#)</span></span>
<span data-ttu-id="ca88e-103"><xref:System.String> クラスはジェネリック <xref:System.Collections.Generic.IEnumerable%601> インターフェイスを実装しているため、任意の文字列を文字のシーケンスとしてクエリできます。</span><span class="sxs-lookup"><span data-stu-id="ca88e-103">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="ca88e-104">ただし、これは LINQ の一般的な使用方法ではありません。</span><span class="sxs-lookup"><span data-stu-id="ca88e-104">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="ca88e-105">複雑なパターン一致操作には、<xref:System.Text.RegularExpressions.Regex> クラスを使用してください。</span><span class="sxs-lookup"><span data-stu-id="ca88e-105">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca88e-106">例</span><span class="sxs-lookup"><span data-stu-id="ca88e-106">Example</span></span>  
 <span data-ttu-id="ca88e-107">次の例では、文字列を対象にクエリを実行して、その文字列に含まれる数字の数を特定します。</span><span class="sxs-lookup"><span data-stu-id="ca88e-107">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="ca88e-108">クエリは、最初に使用された後も "再利用" されます。</span><span class="sxs-lookup"><span data-stu-id="ca88e-108">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="ca88e-109">これができるのは、クエリ自体には実際の結果が格納されないためです。</span><span class="sxs-lookup"><span data-stu-id="ca88e-109">This is possible because the query itself does not store any actual results.</span></span>  
  
```csharp  
class QueryAString  
{  
    static void Main()  
    {  
        string aString = "ABCDE99F-J74-12-89A";  
  
        // Select only those characters that are numbers  
        IEnumerable<char> stringQuery =  
          from ch in aString  
          where Char.IsDigit(ch)  
          select ch;  
  
        // Execute the query  
        foreach (char c in stringQuery)  
            Console.Write(c + " ");  
  
        // Call the Count method on the existing query.  
        int count = stringQuery.Count();  
        Console.WriteLine("Count = {0}", count);  
  
        // Select all characters before the first '-'  
        IEnumerable<char> stringQuery2 = aString.TakeWhile(c => c != '-');  
  
        // Execute the second query  
        foreach (char c in stringQuery2)  
            Console.Write(c);  
  
        Console.WriteLine(System.Environment.NewLine + "Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
  Output: 9 9 7 4 1 2 8 9  
  Count = 8  
  ABCDE99F  
*/  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ca88e-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="ca88e-110">Compiling the Code</span></span>  
 <span data-ttu-id="ca88e-111">System.Linq 名前空間と System.IO 名前空間に `using` ディレクティブを使用して、C# コンソール アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca88e-111">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca88e-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca88e-112">See also</span></span>

- [<span data-ttu-id="ca88e-113">LINQ と文字列 (C#)</span><span class="sxs-lookup"><span data-stu-id="ca88e-113">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="ca88e-114">方法: LINQ クエリと正規表現を組み合わせる (C#)</span><span class="sxs-lookup"><span data-stu-id="ca88e-114">How to: Combine LINQ Queries with Regular Expressions (C#)</span></span>](./how-to-combine-linq-queries-with-regular-expressions.md)
