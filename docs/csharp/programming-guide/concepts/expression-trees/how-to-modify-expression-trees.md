---
title: 式ツリーを変更する方法 (C#)
description: 既存の式ツリーのコピーを作成し、必要な変更を加えて式ツリーを変更する方法について説明します。
ms.date: 07/20/2015
ms.assetid: 9b0cd8c2-457e-4833-9e36-31e79545f442
ms.openlocfilehash: 01176f489794a0f4ca29d229d29507fdba0fd5a8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167692"
---
# <a name="how-to-modify-expression-trees-c"></a><span data-ttu-id="a0f5b-103">式ツリーを変更する方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="a0f5b-103">How to modify expression trees (C#)</span></span>

<span data-ttu-id="a0f5b-104">このトピックでは、式ツリーを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0f5b-104">This topic shows you how to modify an expression tree.</span></span> <span data-ttu-id="a0f5b-105">式ツリーは変更不可であるため、直接変更を加えることができません。</span><span class="sxs-lookup"><span data-stu-id="a0f5b-105">Expression trees are immutable, which means that they cannot be modified directly.</span></span> <span data-ttu-id="a0f5b-106">式ツリーを変更するには、既存の式ツリーのコピーを作成する必要があります。コピーを作成する際に、必要な変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="a0f5b-106">To change an expression tree, you must create a copy of an existing expression tree and when you create the copy, make the required changes.</span></span> <span data-ttu-id="a0f5b-107"><xref:System.Linq.Expressions.ExpressionVisitor> クラスを使用して、既存の式ツリーを走査し、走査した各ノードをコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="a0f5b-107">You can use the <xref:System.Linq.Expressions.ExpressionVisitor> class to traverse an existing expression tree and to copy each node that it visits.</span></span>  
  
### <a name="to-modify-an-expression-tree"></a><span data-ttu-id="a0f5b-108">式ツリーを変更するには</span><span class="sxs-lookup"><span data-stu-id="a0f5b-108">To modify an expression tree</span></span>  
  
1. <span data-ttu-id="a0f5b-109">新しい**コンソール アプリケーション** プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0f5b-109">Create a new **Console Application** project.</span></span>  
  
2. <span data-ttu-id="a0f5b-110">ファイルに `System.Linq.Expressions` 名前空間の `using` ディレクティブを 追加します。</span><span class="sxs-lookup"><span data-stu-id="a0f5b-110">Add a `using` directive to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
3. <span data-ttu-id="a0f5b-111">`AndAlsoModifier` クラスをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="a0f5b-111">Add the `AndAlsoModifier` class to your project.</span></span>  
  
    ```csharp  
    public class AndAlsoModifier : ExpressionVisitor  
    {  
        public Expression Modify(Expression expression)  
        {  
            return Visit(expression);  
        }  
  
        protected override Expression VisitBinary(BinaryExpression b)  
        {  
            if (b.NodeType == ExpressionType.AndAlso)  
            {  
                Expression left = this.Visit(b.Left);  
                Expression right = this.Visit(b.Right);  
  
                // Make this binary expression an OrElse operation instead of an AndAlso operation.  
                return Expression.MakeBinary(ExpressionType.OrElse, left, right, b.IsLiftedToNull, b.Method);  
            }  
  
            return base.VisitBinary(b);  
        }  
    }  
    ```  
  
     <span data-ttu-id="a0f5b-112">このクラスは、`AND` 条件演算を表す式を変更するための特別なクラスで、<xref:System.Linq.Expressions.ExpressionVisitor> クラスを継承します。</span><span class="sxs-lookup"><span data-stu-id="a0f5b-112">This class inherits the <xref:System.Linq.Expressions.ExpressionVisitor> class and is specialized to modify expressions that represent conditional `AND` operations.</span></span> <span data-ttu-id="a0f5b-113">このクラスによって条件 `AND` が条件 `OR` に変更されます。</span><span class="sxs-lookup"><span data-stu-id="a0f5b-113">It changes these operations from a conditional `AND` to a conditional `OR`.</span></span> <span data-ttu-id="a0f5b-114">そのために、クラスは基本データ型の <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> メソッドをオーバーライドします。`AND` 条件式は二項式で表されるためです。</span><span class="sxs-lookup"><span data-stu-id="a0f5b-114">To do this, the class overrides the <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> method of the base type, because conditional `AND` expressions are represented as binary expressions.</span></span> <span data-ttu-id="a0f5b-115">`VisitBinary` メソッドでは、渡される式が `AND` 条件演算を表す場合、`AND` 条件演算子ではなく `OR` 条件演算子を含む新しい式がコードによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="a0f5b-115">In the `VisitBinary` method, if the expression that is passed to it represents a conditional `AND` operation, the code constructs a new expression that contains the conditional `OR` operator instead of the conditional `AND` operator.</span></span> <span data-ttu-id="a0f5b-116">`VisitBinary` に渡される式が `AND` 条件演算を表さない場合は、基底クラスの実装が延期されます。</span><span class="sxs-lookup"><span data-stu-id="a0f5b-116">If the expression that is passed to `VisitBinary` does not represent a conditional `AND` operation, the method defers to the base class implementation.</span></span> <span data-ttu-id="a0f5b-117">基底クラスのメソッドによって、渡された式ツリーに似たノードが作成されますが、そのノードのサブツリーは、ビジターによって再帰的に作成される式ツリーに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="a0f5b-117">The base class methods construct nodes that are like the expression trees that are passed in, but the nodes have their sub trees replaced with the expression trees that are produced recursively by the visitor.</span></span>  
  
4. <span data-ttu-id="a0f5b-118">ファイルに `System.Linq.Expressions` 名前空間の `using` ディレクティブを 追加します。</span><span class="sxs-lookup"><span data-stu-id="a0f5b-118">Add a `using` directive to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
5. <span data-ttu-id="a0f5b-119">式ツリーを作成し、それをメソッドに渡して変更するコードを、Program.cs ファイルの `Main` メソッドに追加します。</span><span class="sxs-lookup"><span data-stu-id="a0f5b-119">Add code to the `Main` method in the Program.cs file to create an expression tree and pass it to the method that will modify it.</span></span>  
  
    ```csharp  
    Expression<Func<string, bool>> expr = name => name.Length > 10 && name.StartsWith("G");  
    Console.WriteLine(expr);  
  
    AndAlsoModifier treeModifier = new AndAlsoModifier();  
    Expression modifiedExpr = treeModifier.Modify((Expression) expr);  
  
    Console.WriteLine(modifiedExpr);  
  
    /*  This code produces the following output:  
  
        name => ((name.Length > 10) && name.StartsWith("G"))  
        name => ((name.Length > 10) || name.StartsWith("G"))  
    */  
    ```  
  
     <span data-ttu-id="a0f5b-120">次のコードは、`AND` 条件演算を含む式を作成し、</span><span class="sxs-lookup"><span data-stu-id="a0f5b-120">The code creates an expression that contains a conditional `AND` operation.</span></span> <span data-ttu-id="a0f5b-121">`AndAlsoModifier` クラスのインスタンスを作成して、このクラスの `Modify` メソッドにその式を渡します。</span><span class="sxs-lookup"><span data-stu-id="a0f5b-121">It then creates an instance of the `AndAlsoModifier` class and passes the expression to the `Modify` method of this class.</span></span> <span data-ttu-id="a0f5b-122">元の式ツリーと変更された式ツリーの両方が出力され、変更内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0f5b-122">Both the original and the modified expression trees are outputted to show the change.</span></span>  
  
6. <span data-ttu-id="a0f5b-123">アプリケーションをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="a0f5b-123">Compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0f5b-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0f5b-124">See also</span></span>

- [<span data-ttu-id="a0f5b-125">式ツリーを実行する方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="a0f5b-125">How to execute expression trees (C#)</span></span>](./how-to-execute-expression-trees.md)
- [<span data-ttu-id="a0f5b-126">式ツリー (C#)</span><span class="sxs-lookup"><span data-stu-id="a0f5b-126">Expression Trees (C#)</span></span>](./index.md)
