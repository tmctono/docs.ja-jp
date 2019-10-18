---
title: '方法: 任意の単語またはフィールドを基準にテキスト データの並べ替えまたはフィルター処理を実行する (LINQ) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 9df137fe-335b-46e0-aecf-ea8a9eddd4e3
ms.openlocfilehash: fa9efc51f72a47acfa32d42fc9ff8e5aadf61721
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524129"
---
# <a name="how-to-sort-or-filter-text-data-by-any-word-or-field-linq-visual-basic"></a><span data-ttu-id="07148-102">方法: 任意の単語またはフィールドを基準にテキスト データの並べ替えまたはフィルター処理を実行する (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07148-102">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="07148-103">次の例では、コンマ区切り値などの構造化されたテキストの行を、行の任意のフィールドで並べ替える方法を示します。</span><span class="sxs-lookup"><span data-stu-id="07148-103">The following example shows how to sort lines of structured text, such as comma-separated values, by any field in the line.</span></span> <span data-ttu-id="07148-104">フィールドは、実行時に動的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="07148-104">The field may be dynamically specified at runtime.</span></span> <span data-ttu-id="07148-105">scores.csv 内のフィールドは、学生の ID 番号と、それに続く 4 つのテストの点を表しているものとします。</span><span class="sxs-lookup"><span data-stu-id="07148-105">Assume that the fields in scores.csv represent a student's ID number, followed by a series of four test scores.</span></span>

### <a name="to-create-a-file-that-contains-data"></a><span data-ttu-id="07148-106">データを含むファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="07148-106">To create a file that contains data</span></span>

<span data-ttu-id="07148-107">トピック「[方法: 異種ファイルのコンテンツを結合する (LINQ) (Visual Basic)」の「方法: コンテンツ](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)をソリューションフォルダーに保存する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07148-107">Copy the scores.csv data from the topic [How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md) and save it to your solution folder.</span></span>

## <a name="example"></a><span data-ttu-id="07148-108">例</span><span class="sxs-lookup"><span data-stu-id="07148-108">Example</span></span>

```vb
Class SortLines

    Shared Sub Main()
        Dim scores As String() = System.IO.File.ReadAllLines("../../../scores.csv")

        ' Change this to any value from 0 to 4
        Dim sortField As Integer = 1

        Console.WriteLine("Sorted highest to lowest by field " & sortField)

        ' Demonstrates how to return query from a method.
        ' The query is executed here.
        For Each str As String In SortQuery(scores, sortField)
            Console.WriteLine(str)
        Next

        ' Keep console window open in debug mode.
        Console.WriteLine("Press any key to exit.")
        Console.ReadKey()

    End Sub

    Shared Function SortQuery(
        ByVal source As IEnumerable(Of String),
        ByVal num As Integer) As IEnumerable(Of String)

        Dim scoreQuery = From line In source
                         Let fields = line.Split(New Char() {","})
                         Order By fields(num) Descending
                         Select line

        Return scoreQuery
    End Function
End Class
' Output:
' Sorted highest to lowest by field 1
' 116, 99, 86, 90, 94
' 120, 99, 82, 81, 79
' 111, 97, 92, 81, 60
' 114, 97, 89, 85, 82
' 121, 96, 85, 91, 60
' 122, 94, 92, 91, 91
' 117, 93, 92, 80, 87
' 118, 92, 90, 83, 78
' 113, 88, 94, 65, 91
' 112, 75, 84, 91, 39
' 119, 68, 79, 88, 92
' 115, 35, 72, 91, 70
```

<span data-ttu-id="07148-109">また、この例では、関数からクエリ変数を返す方法も示しています。</span><span class="sxs-lookup"><span data-stu-id="07148-109">This example also demonstrates how to return a query variable from a Function.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="07148-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="07148-110">Compiling the Code</span></span>

<span data-ttu-id="07148-111">VB.NET コンソールアプリケーションプロジェクトを作成します。このプロジェクトには、名前空間の `Imports` ステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="07148-111">Create a VB.NET console application project, with an `Imports` statement for the System.Linq namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="07148-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="07148-112">See also</span></span>

- [<span data-ttu-id="07148-113">LINQ と文字列 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07148-113">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
