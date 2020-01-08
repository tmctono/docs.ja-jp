---
title: '方法: 文字列内の文字を照会する (LINQ)'
ms.date: 07/20/2015
ms.assetid: 499ebbe0-746c-4235-9dba-ce722c12b50e
ms.openlocfilehash: 2f306a488610aaa5775210eba3d7312b092545a7
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345522"
---
# <a name="how-to-query-for-characters-in-a-string-linq-visual-basic"></a><span data-ttu-id="6a785-102">方法: 文字列内の文字を照会する (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a785-102">How to: Query for Characters in a String (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="6a785-103"><xref:System.String> クラスはジェネリック <xref:System.Collections.Generic.IEnumerable%601> インターフェイスを実装しているため、任意の文字列を文字のシーケンスとしてクエリできます。</span><span class="sxs-lookup"><span data-stu-id="6a785-103">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="6a785-104">ただし、これは LINQ の一般的な使用方法ではありません。</span><span class="sxs-lookup"><span data-stu-id="6a785-104">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="6a785-105">複雑なパターン一致操作には、<xref:System.Text.RegularExpressions.Regex> クラスを使用してください。</span><span class="sxs-lookup"><span data-stu-id="6a785-105">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>

## <a name="example"></a><span data-ttu-id="6a785-106">使用例</span><span class="sxs-lookup"><span data-stu-id="6a785-106">Example</span></span>

<span data-ttu-id="6a785-107">次の例では、文字列を対象にクエリを実行して、その文字列に含まれる数字の数を特定します。</span><span class="sxs-lookup"><span data-stu-id="6a785-107">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="6a785-108">クエリは、最初に使用された後も "再利用" されます。</span><span class="sxs-lookup"><span data-stu-id="6a785-108">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="6a785-109">これができるのは、クエリ自体には実際の結果が格納されないためです。</span><span class="sxs-lookup"><span data-stu-id="6a785-109">This is possible because the query itself does not store any actual results.</span></span>

```vb
Class QueryAString

    Shared Sub Main()

        ' A string is an IEnumerable data source.
        Dim aString As String = "ABCDE99F-J74-12-89A"

        ' Select only those characters that are numbers
        Dim stringQuery = From ch In aString
                          Where Char.IsDigit(ch)
                          Select ch
        ' Execute the query
        For Each c As Char In stringQuery
            Console.Write(c & " ")
        Next

        ' Call the Count method on the existing query.
        Dim count As Integer = stringQuery.Count()
        Console.WriteLine(System.Environment.NewLine & "Count = " & count)

        ' Select all characters before the first '-'
        Dim stringQuery2 = aString.TakeWhile(Function(c) c <> "-")

        ' Execute the second query
        For Each ch In stringQuery2
            Console.Write(ch)
        Next

        Console.WriteLine(System.Environment.NewLine & "Press any key to exit")
        Console.ReadKey()
    End Sub
End Class
' Output:
' 9 9 7 4 1 2 8 9
' Count = 8
' ABCDE99F
```

## <a name="compile-the-code"></a><span data-ttu-id="6a785-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="6a785-110">Compile the code</span></span>

<span data-ttu-id="6a785-111">System. Linq 名前空間の `Imports` ステートメントを使用して、Visual Basic コンソールアプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="6a785-111">Create a Visual Basic console application project, with an `Imports` statement for the System.Linq namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a785-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a785-112">See also</span></span>

- [<span data-ttu-id="6a785-113">LINQ と文字列 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a785-113">LINQ and Strings (Visual Basic)</span></span>](linq-and-strings.md)
- [<span data-ttu-id="6a785-114">LINQ クエリと正規表現を組み合わせる方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a785-114">How to combine LINQ queries with regular expressions (Visual Basic)</span></span>](how-to-combine-linq-queries-with-regular-expressions.md)
