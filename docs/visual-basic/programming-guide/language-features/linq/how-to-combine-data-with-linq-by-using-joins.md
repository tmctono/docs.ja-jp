---
title: '方法: 結合 (Visual Basic) を使用してデータを LINQ を結合します。'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
ms.openlocfilehash: 127e1afa7707f31584e93f3d4b08e865d7fcedf6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775883"
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a><span data-ttu-id="279c9-102">方法: 結合 (Visual Basic) を使用してデータを LINQ を結合します。</span><span class="sxs-lookup"><span data-stu-id="279c9-102">How to: Combine Data with LINQ by Using Joins (Visual Basic)</span></span>
<span data-ttu-id="279c9-103">Visual Basic では、`Join`と`Group Join`コレクション間で共通の値に基づく複数のコレクションの内容を結合するための句をクエリします。</span><span class="sxs-lookup"><span data-stu-id="279c9-103">Visual Basic provides the `Join` and `Group Join` query clauses to enable you to combine the contents of multiple collections based on common values between the collections.</span></span> <span data-ttu-id="279c9-104">これらの値と呼ばれる*キー*値。</span><span class="sxs-lookup"><span data-stu-id="279c9-104">These values are known as *key* values.</span></span> <span data-ttu-id="279c9-105">リレーショナル データベースの概念に慣れている開発者が認識、 `Join` INNER JOIN 句、`Group Join`として、実際には、左外部結合句。</span><span class="sxs-lookup"><span data-stu-id="279c9-105">Developers familiar with relational database concepts will recognize the `Join` clause as an INNER JOIN and the `Group Join` clause as, effectively, a LEFT OUTER JOIN.</span></span>  
  
 <span data-ttu-id="279c9-106">このトピックの例を使用してデータを結合する方法をいくつかを示す、`Join`と`Group Join`クエリ句。</span><span class="sxs-lookup"><span data-stu-id="279c9-106">The examples in this topic demonstrate a few ways to combine data by using the `Join` and `Group Join` query clauses.</span></span>  
  
## <a name="create-a-project-and-add-sample-data"></a><span data-ttu-id="279c9-107">プロジェクトを作成し、サンプル データを追加</span><span class="sxs-lookup"><span data-stu-id="279c9-107">Create a Project and Add Sample Data</span></span>  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a><span data-ttu-id="279c9-108">サンプル データと型を含むプロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="279c9-108">To create a project that contains sample data and types</span></span>  
  
1. <span data-ttu-id="279c9-109">このトピックのサンプルを実行するには、Visual Studio を開き、新しい Visual Basic コンソール アプリケーション プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="279c9-109">To run the samples in this topic, open Visual Studio and add a new Visual Basic Console Application project.</span></span> <span data-ttu-id="279c9-110">Visual Basic で作成された Module1.vb ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="279c9-110">Double-click the Module1.vb file created by Visual Basic.</span></span>  
  
2. <span data-ttu-id="279c9-111">このトピックで使用中のサンプル、`Person`と`Pet`型と、次のコード例からのデータ。</span><span class="sxs-lookup"><span data-stu-id="279c9-111">The samples in this topic use the `Person` and `Pet` types and data from the following code example.</span></span> <span data-ttu-id="279c9-112">既定値にこのコードをコピー `Module1` Visual Basic で作成されたモジュール。</span><span class="sxs-lookup"><span data-stu-id="279c9-112">Copy this code into the default `Module1` module created by Visual Basic.</span></span>  
  
     [!code-vb[VbLINQHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#1)]  
    [!code-vb[VbLINQHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#2)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="279c9-113">Join 句を使用して内部結合を実行します。</span><span class="sxs-lookup"><span data-stu-id="279c9-113">Perform an Inner Join by Using the Join Clause</span></span>  
 <span data-ttu-id="279c9-114">INNER JOIN によって 2 つのコレクションからデータを結合します。</span><span class="sxs-lookup"><span data-stu-id="279c9-114">An INNER JOIN combines data from two collections.</span></span> <span data-ttu-id="279c9-115">指定されたキー値に一致する対象のアイテムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="279c9-115">Items for which the specified key values match are included.</span></span> <span data-ttu-id="279c9-116">その他のコレクションの一致する項目がありません。 いずれかのコレクションからすべての項目が除外されます。</span><span class="sxs-lookup"><span data-stu-id="279c9-116">Any items from either collection that do not have a matching item in the other collection are excluded.</span></span>  
  
 <span data-ttu-id="279c9-117">Visual basic で LINQ は内部結合を実行するための 2 つのオプションを提供します。 暗黙の結合と明示的な結合します。</span><span class="sxs-lookup"><span data-stu-id="279c9-117">In Visual Basic, LINQ provides two options for performing an INNER JOIN: an implicit join and an explicit join.</span></span>  
  
 <span data-ttu-id="279c9-118">暗黙の結合結合するコレクションの指定、`From`句に一致するキー フィールドを指定して、`Where`句。</span><span class="sxs-lookup"><span data-stu-id="279c9-118">An implicit join specifies the collections to be joined in a `From` clause and identifies the matching key fields in a `Where` clause.</span></span> <span data-ttu-id="279c9-119">Visual Basic は、暗黙的に指定されたキー フィールドに基づいて 2 つのコレクションを結合します。</span><span class="sxs-lookup"><span data-stu-id="279c9-119">Visual Basic implicitly joins the two collections based on the specified key fields.</span></span>  
  
 <span data-ttu-id="279c9-120">使用して、明示的な結合を指定することができます、`Join`句には、どのキー フィールドの結合に使用する場合。</span><span class="sxs-lookup"><span data-stu-id="279c9-120">You can specify an explicit join by using the `Join` clause when you want to be specific about which key fields to use in the join.</span></span> <span data-ttu-id="279c9-121">ここで、`Where`句は、クエリ結果をフィルター処理も使用できます。</span><span class="sxs-lookup"><span data-stu-id="279c9-121">In this case, a `Where` clause can still be used to filter the query results.</span></span>  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="279c9-122">Join 句を使用して内部結合を実行するには</span><span class="sxs-lookup"><span data-stu-id="279c9-122">To perform an Inner Join by using the Join clause</span></span>  
  
1. <span data-ttu-id="279c9-123">次のコードを追加、`Module1`両方暗黙的および明示的な内部結合の例を参照するプロジェクトのモジュール。</span><span class="sxs-lookup"><span data-stu-id="279c9-123">Add the following code to the `Module1` module in your project to see examples of both an implicit and explicit inner join.</span></span>  
  
     [!code-vb[VbLINQHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#4)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="279c9-124">Group Join 句を使用して、左外部結合を実行します。</span><span class="sxs-lookup"><span data-stu-id="279c9-124">Perform a Left Outer Join by Using the Group Join Clause</span></span>  
 <span data-ttu-id="279c9-125">左外部結合には、結合および結合の右側にあるコレクションからの値が一致するのみの左側にあるコレクションからすべての項目が含まれています。</span><span class="sxs-lookup"><span data-stu-id="279c9-125">A LEFT OUTER JOIN includes all the items from the left-side collection of the join and only matching values from the right-side collection of the join.</span></span> <span data-ttu-id="279c9-126">左側のコレクションに一致する項目がない結合の右側にあるコレクションからすべての項目は、クエリ結果から除外されます。</span><span class="sxs-lookup"><span data-stu-id="279c9-126">Any items from the right-side collection of the join that do not have a matching item in the left-side collection are excluded from the query result.</span></span>  
  
 <span data-ttu-id="279c9-127">`Group Join`句実行実際には、左外部結合します。</span><span class="sxs-lookup"><span data-stu-id="279c9-127">The `Group Join` clause performs, in effect, a LEFT OUTER JOIN.</span></span> <span data-ttu-id="279c9-128">LEFT OUTER JOIN と通常呼ばれるものとどのような違い、`Group Join`される句を返します、`Group Join`左側にあるコレクション内の各項目の結合の右側にあるコレクションから句のグループの結果。</span><span class="sxs-lookup"><span data-stu-id="279c9-128">The difference between what is typically known as a LEFT OUTER JOIN and what the `Group Join` clause returns is that the `Group Join` clause groups results from the right-side collection of the join for each item in the left-side collection.</span></span> <span data-ttu-id="279c9-129">リレーショナル データベースでは、LEFT OUTER JOIN は、クエリ内の各項目の結果の結果グループに属していないには結合の両方のコレクションから一致する項目が含まれていますを返します。</span><span class="sxs-lookup"><span data-stu-id="279c9-129">In a relational database, a LEFT OUTER JOIN returns an ungrouped result in which each item in the query result contains matching items from both collections in the join.</span></span> <span data-ttu-id="279c9-130">この場合、結合の左側にあるコレクションからアイテムは、右側にあるコレクションからの一致項目ごとに繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="279c9-130">In this case, the items from the left-side collection of the join are repeated for each matching item from the right-side collection.</span></span> <span data-ttu-id="279c9-131">これがどのように、次の手順を完了すると表示されます。</span><span class="sxs-lookup"><span data-stu-id="279c9-131">You will see what this looks like when you complete the next procedure.</span></span>  
  
 <span data-ttu-id="279c9-132">結果を取得することができます、`Group Join`項目それぞれグループ化されたクエリの結果を返すクエリを拡張することによって、グループに属していない結果としてクエリ。</span><span class="sxs-lookup"><span data-stu-id="279c9-132">You can retrieve the results of a `Group Join` query as an ungrouped result by extending your query to return an item for each grouped query result.</span></span> <span data-ttu-id="279c9-133">これを実現するをクエリすることを確認する必要がある、`DefaultIfEmpty`グループ化されたコレクションのメソッド。</span><span class="sxs-lookup"><span data-stu-id="279c9-133">To accomplish this, you have to ensure that you query on the `DefaultIfEmpty` method of the grouped collection.</span></span> <span data-ttu-id="279c9-134">これにより、結合の左側にあるコレクションの項目が右側にあるコレクションから一致する結果がない場合でも、クエリ結果に含まれるまだ。</span><span class="sxs-lookup"><span data-stu-id="279c9-134">This ensures that items from the left-side collection of the join are still included in the query result even if they have no matching results from the right-side collection.</span></span> <span data-ttu-id="279c9-135">結合の右側にあるコレクションに一致する値がない場合は、既定の結果値を提供するクエリにコードを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="279c9-135">You can add code to your query to provide a default result value when there is no matching value from the right-side collection of the join.</span></span>  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="279c9-136">Group Join 句を使用して左外部結合を実行するには</span><span class="sxs-lookup"><span data-stu-id="279c9-136">To perform a Left Outer Join by using the Group Join clause</span></span>  
  
1. <span data-ttu-id="279c9-137">次のコードを追加、`Module1`モジュールで、プロジェクトをグループ化された左外部結合とグループに属していないの左外部結合の両方の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="279c9-137">Add the following code to the `Module1` module in your project to see examples of both a grouped left outer join and an ungrouped left outer join.</span></span>  
  
     [!code-vb[VbLINQHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#3)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="279c9-138">複合キーを使用して、結合を実行します。</span><span class="sxs-lookup"><span data-stu-id="279c9-138">Perform a Join by Using a Composite Key</span></span>  
 <span data-ttu-id="279c9-139">使用することができます、`And`キーワード、`Join`または`Group Join`句に一致するときに使用する複数のキー フィールドを識別するためには、結合するコレクションの値します。</span><span class="sxs-lookup"><span data-stu-id="279c9-139">You can use the `And` keyword in a `Join` or `Group Join` clause to identify multiple key fields to use when matching values from the collections being joined.</span></span> <span data-ttu-id="279c9-140">`And`キーワードは、すべての指定に参加している項目のキー フィールドに一致する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="279c9-140">The `And` keyword specifies that all specified key fields must match for items to be joined.</span></span>  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="279c9-141">複合キーを使用して、結合を実行するには</span><span class="sxs-lookup"><span data-stu-id="279c9-141">To perform a Join by using a composite key</span></span>  
  
1. <span data-ttu-id="279c9-142">次のコードを追加、`Module1`複合キーを使用する結合の例を参照するプロジェクトのモジュール。</span><span class="sxs-lookup"><span data-stu-id="279c9-142">Add the following code to the `Module1` module in your project to see examples of a join that uses a composite key.</span></span>  
  
     [!code-vb[VbLINQHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#5)]  
  
## <a name="run-the-code"></a><span data-ttu-id="279c9-143">コードを実行します</span><span class="sxs-lookup"><span data-stu-id="279c9-143">Run the Code</span></span>  
  
#### <a name="to-add-code-to-run-the-examples"></a><span data-ttu-id="279c9-144">例を実行するコードを追加するには</span><span class="sxs-lookup"><span data-stu-id="279c9-144">To add code to run the examples</span></span>  
  
1. <span data-ttu-id="279c9-145">置換、`Sub Main`で、`Module1`このトピックの例を実行する次のコードで、プロジェクトのモジュール。</span><span class="sxs-lookup"><span data-stu-id="279c9-145">Replace the `Sub Main` in the `Module1` module in your project with the following code to run the examples in this topic.</span></span>  
  
     [!code-vb[VbLINQHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#6)]  
  
2. <span data-ttu-id="279c9-146">F5 キーを押して、例を実行します。</span><span class="sxs-lookup"><span data-stu-id="279c9-146">Press F5 to run the examples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="279c9-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="279c9-147">See also</span></span>

- [<span data-ttu-id="279c9-148">LINQ</span><span class="sxs-lookup"><span data-stu-id="279c9-148">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="279c9-149">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="279c9-149">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="279c9-150">Join 句</span><span class="sxs-lookup"><span data-stu-id="279c9-150">Join Clause</span></span>](../../../../visual-basic/language-reference/queries/join-clause.md)
- [<span data-ttu-id="279c9-151">Group Join 句</span><span class="sxs-lookup"><span data-stu-id="279c9-151">Group Join Clause</span></span>](../../../../visual-basic/language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="279c9-152">From 句</span><span class="sxs-lookup"><span data-stu-id="279c9-152">From Clause</span></span>](../../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="279c9-153">Where 句</span><span class="sxs-lookup"><span data-stu-id="279c9-153">Where Clause</span></span>](../../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="279c9-154">クエリ</span><span class="sxs-lookup"><span data-stu-id="279c9-154">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="279c9-155">LINQ によるデータ変換 (C#)</span><span class="sxs-lookup"><span data-stu-id="279c9-155">Data Transformations with LINQ (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)
