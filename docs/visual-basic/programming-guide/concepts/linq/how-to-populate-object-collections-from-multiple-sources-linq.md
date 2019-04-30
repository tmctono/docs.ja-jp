---
title: '方法: 複数のソース (LINQ) (Visual Basic) からオブジェクト コレクションを設定します。'
ms.date: 06/22/2018
ms.assetid: 63062a22-e6a9-42c0-b357-c7c965f58f33
ms.openlocfilehash: 65c7e2c791ba8331416ee2eee292f1e8c4888712
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024327"
---
# <a name="how-to-populate-object-collections-from-multiple-sources-linq-visual-basic"></a><span data-ttu-id="20c72-102">方法: 複数のソース (LINQ) (Visual Basic) からオブジェクト コレクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="20c72-102">How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="20c72-103">この例では、さまざまなソースから一連の新しい型にデータをマージする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="20c72-103">This example shows how to merge data from different sources into a sequence of new types.</span></span>

> [!NOTE]
> <span data-ttu-id="20c72-104">メモリ内データやファイル システム内のデータを、データベース内にあるデータに結合しようとしないでください。</span><span class="sxs-lookup"><span data-stu-id="20c72-104">Don't try to join in-memory data or data in the file system with data that is still in a database.</span></span> <span data-ttu-id="20c72-105">このようなドメイン間結合を行うと、データベース クエリと他の種類のソースとで結合操作の定義方法に違いがあることが原因で、結果が未定義になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="20c72-105">Such cross-domain joins can yield undefined results because of different ways in which join operations might be defined for database queries and other types of sources.</span></span> <span data-ttu-id="20c72-106">また、データベース内に大量のデータが存在すると、こうした操作によってメモリ不足例外が発生するおそれがあります。</span><span class="sxs-lookup"><span data-stu-id="20c72-106">Additionally, there is a risk that such an operation could cause an out-of-memory exception if the amount of data in the database is large enough.</span></span> <span data-ttu-id="20c72-107">データベースのデータをメモリ内データに結合するには、まずデータベース クエリで `ToList` または `ToArray` を呼び出してから、返されたコレクションで結合を実行します。</span><span class="sxs-lookup"><span data-stu-id="20c72-107">To join data from a database to in-memory data, first call `ToList` or `ToArray` on the database query, and then perform the join on the returned collection.</span></span>

## <a name="to-create-the-data-file"></a><span data-ttu-id="20c72-108">データ ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="20c72-108">To create the data file</span></span>

- <span data-ttu-id="20c72-109">names.csv ファイルと scores.csv ファイルをプロジェクト フォルダーにコピーします。このとき、「[方法:異種ファイル (LINQ) (Visual Basic) からコンテンツを結合する](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)します。</span><span class="sxs-lookup"><span data-stu-id="20c72-109">Copy the names.csv and scores.csv files into your project folder, as described in [How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md).</span></span>

## <a name="example"></a><span data-ttu-id="20c72-110">例</span><span class="sxs-lookup"><span data-stu-id="20c72-110">Example</span></span>

<span data-ttu-id="20c72-111">次の例は、2 つのメモリ内文字列コレクションからマージされたデータを、名前付きの型 `Student` を使用して格納する方法を示しています。各コレクションは、.csv 形式のスプレッドシート データをシミュレートしています。</span><span class="sxs-lookup"><span data-stu-id="20c72-111">The following example shows how to use a named type `Student` to store merged data from two in-memory collections of strings that simulate spreadsheet data in .csv format.</span></span> <span data-ttu-id="20c72-112">1 つ目の文字列コレクションは学生の名前と ID を表し、2 つ目のコレクションは学生 ID (最初の列) と 4 つの試験の点数を表しています。</span><span class="sxs-lookup"><span data-stu-id="20c72-112">The first collection of strings represents the student names and IDs, and the second collection represents the student ID (in the first column) and four exam scores.</span></span> <span data-ttu-id="20c72-113">外部キーとして ID が使用されます。</span><span class="sxs-lookup"><span data-stu-id="20c72-113">The ID is used as the foreign key.</span></span>

```vb
Imports System.Collections.Generic
Imports System.Linq

Class Student
    Public FirstName As String
    Public LastName As String
    Public ID As Integer
    Public ExamScores As List(Of Integer)
End Class

Class PopulateCollection

    Shared Sub Main()

        ' Merge content from spreadsheets into a list of Student objects.

        ' These data files are defined in How to: Join Content from
        ' Dissimilar Files (LINQ).

        ' Each line of names.csv consists of a last name, a first name, and an
        ' ID number, separated by commas. For example, Omelchenko,Svetlana,111
        Dim names As String() = System.IO.File.ReadAllLines("../../../names.csv")

        ' Each line of scores.csv consists of an ID number and four test
        ' scores, separated by commas. For example, 111, 97, 92, 81, 60
        Dim scores As String() = System.IO.File.ReadAllLines("../../../scores.csv")

        ' The following query merges the content of two dissimilar spreadsheets
        ' based on common ID values.
        ' Multiple From clauses are used instead of a Join clause
        ' in order to store the results of scoreLine.Split.
        ' Note the dynamic creation of a list of integers for the
        ' ExamScores member. The first item is skipped in the split string
        ' because it is the student ID, not an exam score.
        Dim queryNamesScores = From nameLine In names
                          Let splitName = nameLine.Split(New Char() {","})
                          From scoreLine In scores
                          Let splitScoreLine = scoreLine.Split(New Char() {","})
                          Where Convert.ToInt32(splitName(2)) = Convert.ToInt32(splitScoreLine(0))
                          Select New Student() With {
                               .FirstName = splitName(1), .LastName = splitName(0), .ID = splitName(2),
                               .ExamScores = (From scoreAsText In splitScoreLine Skip 1
                                             Select Convert.ToInt32(scoreAsText)).ToList()}

        ' Optional. Store the query results for faster access in future
        ' queries. This could be useful with very large data files.
        Dim students As List(Of Student) = queryNamesScores.ToList()

        ' Display each student's name and exam score average.
        For Each s In students
            Console.WriteLine("The average score of " & s.FirstName & " " &
                              s.LastName & " is " & s.ExamScores.Average())
        Next

        ' Keep console window open in debug mode.
        Console.WriteLine("Press any key to exit.")
        Console.ReadKey()
    End Sub
End Class

' Output:
' The average score of Svetlana Omelchenko is 82.5
' The average score of Claire O'Donnell is 72.25
' The average score of Sven Mortensen is 84.5
' The average score of Cesar Garcia is 88.25
' The average score of Debra Garcia is 67
' The average score of Fadi Fakhouri is 92.25
' The average score of Hanying Feng is 88
' The average score of Hugo Garcia is 85.75
' The average score of Lance Tucker is 81.75
' The average score of Terry Adams is 85.25
' The average score of Eugene Zabokritski is 83
' The average score of Michael Tucker is 92
```

<span data-ttu-id="20c72-114">[Select 句](../../../../visual-basic/language-reference/queries/select-clause.md)句では、オブジェクト初期化子はそれぞれの新しいインスタンスを作成するために使用`Student`2 つのソースからデータを使用してオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="20c72-114">In the [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md) clause, an object initializer is used to instantiate each new `Student` object by using the data from the two sources.</span></span>

<span data-ttu-id="20c72-115">クエリの結果を格納する必要がない場合は、名前付きの型よりも匿名型の方が便利です。</span><span class="sxs-lookup"><span data-stu-id="20c72-115">If you don't have to store the results of a query, anonymous types can be more convenient than named types.</span></span> <span data-ttu-id="20c72-116">クエリが実行されたメソッドの外部にクエリ結果を渡す場合は、名前付きの型が必要になります。</span><span class="sxs-lookup"><span data-stu-id="20c72-116">Named types are required if you pass the query results outside the method in which the query is executed.</span></span> <span data-ttu-id="20c72-117">次の例では、前の例と同じタスクを実行しますが、名前付きの型ではなく匿名型が使用します。</span><span class="sxs-lookup"><span data-stu-id="20c72-117">The following example performs the same task as the previous example, but uses anonymous types instead of named types:</span></span>

```vb
' Merge the data by using an anonymous type.
' Note the dynamic creation of a list of integers for the
' ExamScores member. We skip 1 because the first string
' in the array is the student ID, not an exam score.
Dim queryNamesScores2 =
    From nameLine In names
    Let splitName = nameLine.Split(New Char() {","})
    From scoreLine In scores
    Let splitScoreLine = scoreLine.Split(New Char() {","})
    Where Convert.ToInt32(splitName(2)) = Convert.ToInt32(splitScoreLine(0))
    Select New With
           {.Last = splitName(0),
            .First = splitName(1),
            .ExamScores = (From scoreAsText In splitScoreLine Skip 1
                           Select Convert.ToInt32(scoreAsText)).ToList()}

' Display each student's name and exam score average.
For Each s In queryNamesScores2
    Console.WriteLine("The average score of " & s.First & " " &
                      s.Last & " is " & s.ExamScores.Average())
Next
```

## <a name="compiling-the-code"></a><span data-ttu-id="20c72-118">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="20c72-118">Compiling the code</span></span>

<span data-ttu-id="20c72-119">次のいずれかのオプションを対象とするプロジェクトを作成してコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="20c72-119">Create and compile a project that targets one of the following options:</span></span>

- <span data-ttu-id="20c72-120">System.Core.dll の参照を含む .NET Framework バージョン 3.5。</span><span class="sxs-lookup"><span data-stu-id="20c72-120">.NET Framework version 3.5 with a reference to System.Core.dll.</span></span>
- <span data-ttu-id="20c72-121">.NET Framework バージョン 4.0 以降</span><span class="sxs-lookup"><span data-stu-id="20c72-121">.NET Framework version 4.0 or higher.</span></span>
- <span data-ttu-id="20c72-122">.NET Core バージョン 1.0 以降。</span><span class="sxs-lookup"><span data-stu-id="20c72-122">.NET Core version 1.0 or higher.</span></span>

## <a name="see-also"></a><span data-ttu-id="20c72-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="20c72-123">See also</span></span>

- [<span data-ttu-id="20c72-124">LINQ と文字列 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20c72-124">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
