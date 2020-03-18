---
title: クエリでラムダ式を使用する方法 - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], in LINQ
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
ms.openlocfilehash: 92bdbf842c5c30b2f32e06f622f3e08f3c7a878f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75711962"
---
# <a name="how-to-use-lambda-expressions-in-a-query-c-programming-guide"></a><span data-ttu-id="13261-102">クエリでラムダ式を使用する方法 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="13261-102">How to use lambda expressions in a query (C# Programming Guide)</span></span>
<span data-ttu-id="13261-103">クエリ構文でラムダ式を直接使うことはありませんが、メソッドの呼び出しで使い、クエリ式はメソッドの呼び出しを含むことができます。</span><span class="sxs-lookup"><span data-stu-id="13261-103">You do not use lambda expressions directly in query syntax, but you do use them in method calls, and query expressions can contain method calls.</span></span> <span data-ttu-id="13261-104">実際、一部のクエリ操作はメソッド構文でのみ表現できます。</span><span class="sxs-lookup"><span data-stu-id="13261-104">In fact, some query operations can only be expressed in method syntax.</span></span> <span data-ttu-id="13261-105">クエリ構文とメソッド構文の違いについて詳しくは、「[LINQ でのクエリ構文とメソッド構文](../concepts/linq/query-syntax-and-method-syntax-in-linq.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="13261-105">For more information about the difference between query syntax and method syntax, see [Query Syntax and Method Syntax in LINQ](../concepts/linq/query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="13261-106">例</span><span class="sxs-lookup"><span data-stu-id="13261-106">Example</span></span>  
 <span data-ttu-id="13261-107">次の例を見ると、<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> 標準クエリ演算子を使用することにより、メソッド ベースのクエリでラムダ式を使用する方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="13261-107">The following example demonstrates how to use a lambda expression in a method-based query by using the <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> standard query operator.</span></span> <span data-ttu-id="13261-108">この例の <xref:System.Linq.Enumerable.Where%2A> メソッドにはデリゲート型 <xref:System.Func%602> の入力パラメーターがあり、そのデリゲートは入力として整数を受け取ってブール値を返すことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="13261-108">Note that the <xref:System.Linq.Enumerable.Where%2A> method in this example has an input parameter of the delegate type <xref:System.Func%602> and that delegate takes an integer as input and returns a Boolean.</span></span> <span data-ttu-id="13261-109">ラムダ式は、そのデリゲートに変換できます。</span><span class="sxs-lookup"><span data-stu-id="13261-109">The lambda expression can be converted to that delegate.</span></span> <span data-ttu-id="13261-110">これが [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] メソッドを使用する <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType> のクエリであったなら、パラメーターの型は `Expression<Func<int,bool>>` になりますが、ラムダ式の表現はまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="13261-110">If this were a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query that used the <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType> method, the parameter type would be an `Expression<Func<int,bool>>` but the lambda expression would look exactly the same.</span></span> <span data-ttu-id="13261-111">式の型の詳細については、<xref:System.Linq.Expressions.Expression?displayProperty=nameWithType> に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="13261-111">For more information on the Expression type, see <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csrefLINQHowTos.cs#1)]  
  
## <a name="example"></a><span data-ttu-id="13261-112">例</span><span class="sxs-lookup"><span data-stu-id="13261-112">Example</span></span>  
 <span data-ttu-id="13261-113">次の例では、クエリ式のメソッド呼び出しでラムダ式を使う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="13261-113">The following example demonstrates how to use a lambda expression in a method call of a query expression.</span></span> <span data-ttu-id="13261-114"><xref:System.Linq.Enumerable.Sum%2A> 標準クエリ演算子はクエリ構文を使って呼び出すことができないため、ラムダが必要です。</span><span class="sxs-lookup"><span data-stu-id="13261-114">The lambda is necessary because the <xref:System.Linq.Enumerable.Sum%2A> standard query operator cannot be invoked by using query syntax.</span></span>  
  
 <span data-ttu-id="13261-115">このクエリは最初に、`GradeLevel` 列挙型で定義されている成績レベルに従って、学生をグループ分けします。</span><span class="sxs-lookup"><span data-stu-id="13261-115">The query first groups the students according to their grade level, as defined in the `GradeLevel` enum.</span></span> <span data-ttu-id="13261-116">その後、各グループについて、各学生の合計点数を追加します。</span><span class="sxs-lookup"><span data-stu-id="13261-116">Then for each group it adds the total scores for each student.</span></span> <span data-ttu-id="13261-117">これには、2 つの `Sum` 演算が必要です。</span><span class="sxs-lookup"><span data-stu-id="13261-117">This requires two `Sum` operations.</span></span> <span data-ttu-id="13261-118">内側の `Sum` は各学生の合計点数を計算し、外側の `Sum` はグループ内のすべての学生の集計中の合計を保持します。</span><span class="sxs-lookup"><span data-stu-id="13261-118">The inner `Sum` calculates the total score for each student, and the outer `Sum` keeps a running, combined total for all students in the group.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csrefLINQHowTos.cs#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="13261-119">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="13261-119">Compiling the Code</span></span>  
 <span data-ttu-id="13261-120">このコードを実行するには、メソッドをコピーして、「`StudentClass`オブジェクトのコレクションにクエリを実行する[」で提供されている ](../../linq/query-a-collection-of-objects.md) に貼り付けた後、`Main` メソッドからそれを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="13261-120">To run this code, copy and paste the method into the `StudentClass` that is provided in [Query a collection of objects](../../linq/query-a-collection-of-objects.md) and call it from the `Main` method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="13261-121">参照</span><span class="sxs-lookup"><span data-stu-id="13261-121">See also</span></span>

- [<span data-ttu-id="13261-122">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="13261-122">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="13261-123">式ツリー (C#)</span><span class="sxs-lookup"><span data-stu-id="13261-123">Expression Trees (C#)</span></span>](../concepts/expression-trees/index.md)
