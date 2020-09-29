---
title: LINQ を使用して ArrayList にクエリを実行する方法 (C#)
description: この例では、LINQ を使用して、C# の ArrayList に対してクエリを実行します。 範囲変数の型を宣言して、オブジェクトの型をコレクションに反映させる必要があります。
ms.date: 07/20/2015
ms.assetid: 2bfb471c-6e9a-4e60-bd83-4a1778abde11
ms.openlocfilehash: 278c05cfc864ee4f53e1215a2acb739efd87f8b1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91154003"
---
# <a name="how-to-query-an-arraylist-with-linq-c"></a><span data-ttu-id="93fc0-104">LINQ を使用して ArrayList にクエリを実行する方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="93fc0-104">How to query an ArrayList with LINQ (C#)</span></span>

<span data-ttu-id="93fc0-105">LINQ を使用して <xref:System.Collections.ArrayList> などの非ジェネリックの <xref:System.Collections.IEnumerable> コレクションをクエリする場合、範囲変数の型を明示的に宣言して、オブジェクトの特定の型をコレクションに反映させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="93fc0-105">When using LINQ to query non-generic <xref:System.Collections.IEnumerable> collections such as <xref:System.Collections.ArrayList>, you must explicitly declare the type of the range variable to reflect the specific type of the objects in the collection.</span></span> <span data-ttu-id="93fc0-106">たとえば、`Student` オブジェクトの <xref:System.Collections.ArrayList> がある場合、[from 句](../../../language-reference/keywords/from-clause.md)は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="93fc0-106">For example, if you have an <xref:System.Collections.ArrayList> of `Student` objects, your [from clause](../../../language-reference/keywords/from-clause.md) should look like this:</span></span>  
  
```csharp
var query = from Student s in arrList  
//...
```  
  
 <span data-ttu-id="93fc0-107">範囲変数の型を指定することで、<xref:System.Collections.ArrayList> 内の各項目を `Student` にキャストします。</span><span class="sxs-lookup"><span data-stu-id="93fc0-107">By specifying the type of the range variable, you are casting each item in the <xref:System.Collections.ArrayList> to a `Student`.</span></span>  
  
 <span data-ttu-id="93fc0-108">明示的に型指定された範囲変数をクエリ式で使用すると、<xref:System.Linq.Enumerable.Cast%2A> メソッドを呼び出した場合と同じ結果を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="93fc0-108">The use of an explicitly typed range variable in a query expression is equivalent to calling the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="93fc0-109">指定したキャストを実行できない場合、<xref:System.Linq.Enumerable.Cast%2A> は例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="93fc0-109"><xref:System.Linq.Enumerable.Cast%2A> throws an exception if the specified cast cannot be performed.</span></span> <span data-ttu-id="93fc0-110"><xref:System.Linq.Enumerable.Cast%2A> および <xref:System.Linq.Enumerable.OfType%2A> は、非ジェネリックの <xref:System.Collections.IEnumerable> 型で動作する、2 つの標準クエリ演算子メソッドです。</span><span class="sxs-lookup"><span data-stu-id="93fc0-110"><xref:System.Linq.Enumerable.Cast%2A> and <xref:System.Linq.Enumerable.OfType%2A> are the two Standard Query Operator methods that operate on non-generic <xref:System.Collections.IEnumerable> types.</span></span> <span data-ttu-id="93fc0-111">詳細については、「[LINQ クエリ操作での型の関係](./type-relationships-in-linq-query-operations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93fc0-111">For more information, see [Type Relationships in LINQ Query Operations](./type-relationships-in-linq-query-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="93fc0-112">例</span><span class="sxs-lookup"><span data-stu-id="93fc0-112">Example</span></span>  

 <span data-ttu-id="93fc0-113">次の例では、<xref:System.Collections.ArrayList> に対して単純なクエリを実行しています。</span><span class="sxs-lookup"><span data-stu-id="93fc0-113">The following example shows a simple query over an <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="93fc0-114">この例では、コードが <xref:System.Collections.ArrayList.Add%2A> メソッドを呼び出すときにオブジェクト初期化子を使用していますが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="93fc0-114">Note that this example uses object initializers when the code calls the <xref:System.Collections.ArrayList.Add%2A> method, but this is not a requirement.</span></span>  
  
```csharp  
using System;  
using System.Collections;  
using System.Linq;  
  
namespace NonGenericLINQ  
{  
    public class Student  
    {  
        public string FirstName { get; set; }  
        public string LastName { get; set; }  
        public int[] Scores { get; set; }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ArrayList arrList = new ArrayList();  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Svetlana", LastName = "Omelchenko", Scores = new int[] { 98, 92, 81, 60 }  
                    });  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Claire", LastName = "O’Donnell", Scores = new int[] { 75, 84, 91, 39 }  
                    });  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Sven", LastName = "Mortensen", Scores = new int[] { 88, 94, 65, 91 }  
                    });  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Cesar", LastName = "Garcia", Scores = new int[] { 97, 89, 85, 82 }  
                    });  
  
            var query = from Student student in arrList  
                        where student.Scores[0] > 95  
                        select student;  
  
            foreach (Student s in query)  
                Console.WriteLine(s.LastName + ": " + s.Scores[0]);  
  
            // Keep the console window open in debug mode.  
            Console.WriteLine("Press any key to exit.");  
            Console.ReadKey();  
        }  
    }  
}  
/* Output:
    Omelchenko: 98  
    Garcia: 97  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="93fc0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="93fc0-115">See also</span></span>

- [<span data-ttu-id="93fc0-116">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="93fc0-116">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
