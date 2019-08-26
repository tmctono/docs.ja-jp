---
title: 中間結果の具体化 (C#)
ms.date: 07/20/2015
ms.assetid: 7922d38f-5044-41cf-8e17-7173d6553a5e
ms.openlocfilehash: 273cd68b9714287f259e763c9b7c534aac1931e6
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69592133"
---
# <a name="intermediate-materialization-c"></a><span data-ttu-id="0cc85-102">中間結果の具体化 (C#)</span><span class="sxs-lookup"><span data-stu-id="0cc85-102">Intermediate Materialization (C#)</span></span>
<span data-ttu-id="0cc85-103">不注意なユーザーは、クエリ内でコレクションを早期に具体化して、アプリケーションのメモリおよびパフォーマンスのプロファイルを大幅に変更してしまうことがあります。</span><span class="sxs-lookup"><span data-stu-id="0cc85-103">If you are not careful, in some situations you can drastically alter the memory and performance profile of your application by causing premature materialization of collections in your queries.</span></span> <span data-ttu-id="0cc85-104">一部の標準クエリ演算子では、単一の要素を生成する前に、ソース コレクションを具体化する場合があります。</span><span class="sxs-lookup"><span data-stu-id="0cc85-104">Some standard query operators cause materialization of their source collection before yielding a single element.</span></span> <span data-ttu-id="0cc85-105">たとえば、<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> は最初にソース コレクション全体を反復処理し、次にすべての項目を並べ替えて、最後に最初の項目を生成します。</span><span class="sxs-lookup"><span data-stu-id="0cc85-105">For example, <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> first iterates through its entire source collection, then sorts all items, and then finally yields the first item.</span></span> <span data-ttu-id="0cc85-106">これは、順序付けられたコレクションの最初の項目の取得が高コストであることを意味しています。これ以降の各項目の取得は高コストではありません。</span><span class="sxs-lookup"><span data-stu-id="0cc85-106">This means that it is expensive to get the first item of an ordered collection; each item thereafter is not expensive.</span></span> <span data-ttu-id="0cc85-107">このクエリ演算子は他の方法では処理を実行できないため、これは処理方法として適切なものです。</span><span class="sxs-lookup"><span data-stu-id="0cc85-107">This makes sense: It would be impossible for that query operator to do otherwise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0cc85-108">例</span><span class="sxs-lookup"><span data-stu-id="0cc85-108">Example</span></span>  
 <span data-ttu-id="0cc85-109">この例では、前の例を変更します。</span><span class="sxs-lookup"><span data-stu-id="0cc85-109">This example alters the previous example.</span></span> <span data-ttu-id="0cc85-110">`AppendString` メソッドは、ソースを反復処理する前に、<xref:System.Linq.Enumerable.ToList%2A> ‚ðŒÄ‚Ño‚µ‚Ü‚·B</span><span class="sxs-lookup"><span data-stu-id="0cc85-110">The `AppendString` method calls <xref:System.Linq.Enumerable.ToList%2A> before iterating through the source.</span></span> <span data-ttu-id="0cc85-111">これにより、具体化が行われます。</span><span class="sxs-lookup"><span data-stu-id="0cc85-111">This causes materialization.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source >{0}<", str);  
            yield return str.ToUpper();  
        }  
    }  
  
    public static IEnumerable<string>  
      AppendString(this IEnumerable<string> source, string stringToAppend)  
    {  
        // the following statement materializes the source collection in a List<T>  
        // before iterating through it  
        foreach (string str in source.ToList())  
        {  
            Console.WriteLine("AppendString: source >{0}<", str);  
            yield return str + stringToAppend;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        IEnumerable<string> q1 =  
            from s in stringArray.ConvertCollectionToUpperCase()  
            select s;  
  
        IEnumerable<string> q2 =  
            from s in q1.AppendString("!!!")  
            select s;  
  
        foreach (string str in q2)  
        {  
            Console.WriteLine("Main: str >{0}<", str);  
            Console.WriteLine();  
        }  
    }  
}  
```  
  
 <span data-ttu-id="0cc85-112">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="0cc85-112">This example produces the following output:</span></span>  
  
```  
ToUpper: source >abc<  
ToUpper: source >def<  
ToUpper: source >ghi<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 <span data-ttu-id="0cc85-113">この例では、<xref:System.Linq.Enumerable.ToList%2A> の呼び出しにより、`AppendString` が、最初の項目を生成する前にソース全体を列挙することがわかります。</span><span class="sxs-lookup"><span data-stu-id="0cc85-113">In this example, you can see that the call to <xref:System.Linq.Enumerable.ToList%2A> causes `AppendString` to enumerate its entire source before yielding the first item.</span></span> <span data-ttu-id="0cc85-114">ソースが大きな配列である場合は、これによってアプリケーションのメモリ プロファイルが大幅に変更されます。</span><span class="sxs-lookup"><span data-stu-id="0cc85-114">If the source were a large array, this would significantly alter the memory profile of the application.</span></span>  
  
 <span data-ttu-id="0cc85-115">標準クエリ演算子も連結することができます。</span><span class="sxs-lookup"><span data-stu-id="0cc85-115">Standard query operators can also be chained together.</span></span> <span data-ttu-id="0cc85-116">これについては、このチュートリアルの最後のトピックで説明します。</span><span class="sxs-lookup"><span data-stu-id="0cc85-116">The final topic in this tutorial illustrates this.</span></span>  
  
- [<span data-ttu-id="0cc85-117">標準クエリ演算子の連結 (C#)</span><span class="sxs-lookup"><span data-stu-id="0cc85-117">Chaining Standard Query Operators Together (C#)</span></span>](./chaining-standard-query-operators-together.md)  
  
## <a name="see-also"></a><span data-ttu-id="0cc85-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="0cc85-118">See also</span></span>

- [<span data-ttu-id="0cc85-119">チュートリアル:クエリの連結 (C#)</span><span class="sxs-lookup"><span data-stu-id="0cc85-119">Tutorial: Chaining Queries Together (C#)</span></span>](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
