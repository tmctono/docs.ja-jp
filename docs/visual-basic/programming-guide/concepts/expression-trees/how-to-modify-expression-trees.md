---
title: '方法: 式ツリーの変更 (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: d1309fff-28bd-4d8e-a2cf-75725999e8f2
ms.openlocfilehash: ac196b56f178659765437a97a25f46c04f8040fa
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054210"
---
# <a name="how-to-modify-expression-trees-visual-basic"></a><span data-ttu-id="b4361-102">方法: 式ツリーの変更 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4361-102">How to: Modify Expression Trees (Visual Basic)</span></span>

<span data-ttu-id="b4361-103">このトピックでは、式ツリーを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b4361-103">This topic shows you how to modify an expression tree.</span></span> <span data-ttu-id="b4361-104">式ツリーは変更不可であるため、直接変更を加えることができません。</span><span class="sxs-lookup"><span data-stu-id="b4361-104">Expression trees are immutable, which means that they cannot be modified directly.</span></span> <span data-ttu-id="b4361-105">式ツリーを変更するには、既存の式ツリーのコピーを作成する必要があります。コピーを作成する際に、必要な変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="b4361-105">To change an expression tree, you must create a copy of an existing expression tree and when you create the copy, make the required changes.</span></span> <span data-ttu-id="b4361-106"><xref:System.Linq.Expressions.ExpressionVisitor> クラスを使用して、既存の式ツリーを走査し、走査した各ノードをコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="b4361-106">You can use the <xref:System.Linq.Expressions.ExpressionVisitor> class to traverse an existing expression tree and to copy each node that it visits.</span></span>

## <a name="to-modify-an-expression-tree"></a><span data-ttu-id="b4361-107">式ツリーを変更するには</span><span class="sxs-lookup"><span data-stu-id="b4361-107">To modify an expression tree</span></span>

1. <span data-ttu-id="b4361-108">新しい**コンソール アプリケーション** プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b4361-108">Create a new **Console Application** project.</span></span>

2. <span data-ttu-id="b4361-109">名前空間`System.Linq.Expressions`のファイルにステートメントを`Imports`追加します。</span><span class="sxs-lookup"><span data-stu-id="b4361-109">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>

3. <span data-ttu-id="b4361-110">`AndAlsoModifier` クラスをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="b4361-110">Add the `AndAlsoModifier` class to your project.</span></span>

    ```vb
    Public Class AndAlsoModifier
        Inherits ExpressionVisitor

        Public Function Modify(ByVal expr As Expression) As Expression
            Return Visit(expr)
        End Function

        Protected Overrides Function VisitBinary(ByVal b As BinaryExpression) As Expression
            If b.NodeType = ExpressionType.AndAlso Then
                Dim left = Me.Visit(b.Left)
                Dim right = Me.Visit(b.Right)

                ' Make this binary expression an OrElse operation instead
                ' of an AndAlso operation.
                Return Expression.MakeBinary(ExpressionType.OrElse, left, right, _
                                             b.IsLiftedToNull, b.Method)
            End If

            Return MyBase.VisitBinary(b)
        End Function
    End Class
    ```

    <span data-ttu-id="b4361-111">このクラスは、`AND` 条件演算を表す式を変更するための特別なクラスで、<xref:System.Linq.Expressions.ExpressionVisitor> クラスを継承します。</span><span class="sxs-lookup"><span data-stu-id="b4361-111">This class inherits the <xref:System.Linq.Expressions.ExpressionVisitor> class and is specialized to modify expressions that represent conditional `AND` operations.</span></span> <span data-ttu-id="b4361-112">このクラスによって条件 `AND` が条件 `OR` に変更されます。</span><span class="sxs-lookup"><span data-stu-id="b4361-112">It changes these operations from a conditional `AND` to a conditional `OR`.</span></span> <span data-ttu-id="b4361-113">そのために、クラスは基本データ型の <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> メソッドをオーバーライドします。`AND` 条件式は二項式で表されるためです。</span><span class="sxs-lookup"><span data-stu-id="b4361-113">To do this, the class overrides the <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> method of the base type, because conditional `AND` expressions are represented as binary expressions.</span></span> <span data-ttu-id="b4361-114">`VisitBinary` メソッドでは、渡される式が `AND` 条件演算を表す場合、`AND` 条件演算子ではなく `OR` 条件演算子を含む新しい式がコードによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="b4361-114">In the `VisitBinary` method, if the expression that is passed to it represents a conditional `AND` operation, the code constructs a new expression that contains the conditional `OR` operator instead of the conditional `AND` operator.</span></span> <span data-ttu-id="b4361-115">`VisitBinary` に渡される式が `AND` 条件演算を表さない場合は、基底クラスの実装が延期されます。</span><span class="sxs-lookup"><span data-stu-id="b4361-115">If the expression that is passed to `VisitBinary` does not represent a conditional `AND` operation, the method defers to the base class implementation.</span></span> <span data-ttu-id="b4361-116">基底クラスのメソッドによって、渡された式ツリーに似たノードが作成されますが、そのノードのサブツリーは、ビジターによって再帰的に作成される式ツリーに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="b4361-116">The base class methods construct nodes that are like the expression trees that are passed in, but the nodes have their sub trees replaced with the expression trees that are produced recursively by the visitor.</span></span>

4. <span data-ttu-id="b4361-117">名前空間`System.Linq.Expressions`のファイルにステートメントを`Imports`追加します。</span><span class="sxs-lookup"><span data-stu-id="b4361-117">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>

5. <span data-ttu-id="b4361-118">Module1.vb ファイルの`Main`メソッドにコードを追加して式ツリーを作成し、それを変更するメソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="b4361-118">Add code to the `Main` method in the Module1.vb file to create an expression tree and pass it to the method that will modify it.</span></span>

    ```vb
    Dim expr As Expression(Of Func(Of String, Boolean)) = _
        Function(name) name.Length > 10 AndAlso name.StartsWith("G")

    Console.WriteLine(expr)

    Dim modifier As New AndAlsoModifier()
    Dim modifiedExpr = modifier.Modify(CType(expr, Expression))

    Console.WriteLine(modifiedExpr)

    ' This code produces the following output:
    ' name => ((name.Length > 10) && name.StartsWith("G"))
    ' name => ((name.Length > 10) || name.StartsWith("G"))
    ```

    <span data-ttu-id="b4361-119">次のコードは、`AND` 条件演算を含む式を作成し、</span><span class="sxs-lookup"><span data-stu-id="b4361-119">The code creates an expression that contains a conditional `AND` operation.</span></span> <span data-ttu-id="b4361-120">`AndAlsoModifier` クラスのインスタンスを作成して、このクラスの `Modify` メソッドにその式を渡します。</span><span class="sxs-lookup"><span data-stu-id="b4361-120">It then creates an instance of the `AndAlsoModifier` class and passes the expression to the `Modify` method of this class.</span></span> <span data-ttu-id="b4361-121">元の式ツリーと変更された式ツリーの両方が出力され、変更内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4361-121">Both the original and the modified expression trees are outputted to show the change.</span></span>

6. <span data-ttu-id="b4361-122">アプリケーションをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="b4361-122">Compile and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="b4361-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4361-123">See also</span></span>

- [<span data-ttu-id="b4361-124">方法: 式ツリーの実行 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4361-124">How to: Execute Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)
- [<span data-ttu-id="b4361-125">式ツリー (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4361-125">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
