---
title: '方法: ポリモーフィック クエリを実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: ad6fd7bf6a23f4cd1591a17b25042fd76ff1d08d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545338"
---
# <a name="how-to-execute-a-polymorphic-query"></a><span data-ttu-id="88b14-102">方法: ポリモーフィック クエリを実行する</span><span class="sxs-lookup"><span data-stu-id="88b14-102">How to: Execute a Polymorphic Query</span></span>

<span data-ttu-id="88b14-103">このトピックでは、[OFTYPE](./language-reference/oftype-entity-sql.md) 演算子を使ってポリモーフィックな [!INCLUDE[esql](../../../../../includes/esql-md.md)] クエリを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="88b14-103">This topic shows how to execute a polymorphic [!INCLUDE[esql](../../../../../includes/esql-md.md)] query using the [OFTYPE](./language-reference/oftype-entity-sql.md) operator.</span></span>

### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="88b14-104">この例のコードを実行するには</span><span class="sxs-lookup"><span data-stu-id="88b14-104">To run the code in this example</span></span>

1. <span data-ttu-id="88b14-105">[School モデル](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100))をプロジェクトに追加し、Entity Framework が使用されるようにプロジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="88b14-105">Add the [School Model](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="88b14-106">詳細については、[Entity Data Model ウィザードを使用する](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88b14-106">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>

2. <span data-ttu-id="88b14-107">アプリケーションのコード ページで、次の `using` ステートメント (Visual Basic の場合は `Imports`) を追加します。</span><span class="sxs-lookup"><span data-stu-id="88b14-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>

    [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
    [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]

3. <span data-ttu-id="88b14-108">概念モデルを変更して、Table-Per-Hierarchy 継承を持つようにします。そのためには、「[チュートリアル:Table-Per-Hierarchy 継承のマッピング](/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100))」で説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="88b14-108">Modify the conceptual model to have a table-per-hierarchy inheritance by following the steps in [Walkthrough: Mapping Inheritance - Table-per-Hierarchy](/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).</span></span>

## <a name="example"></a><span data-ttu-id="88b14-109">例</span><span class="sxs-lookup"><span data-stu-id="88b14-109">Example</span></span>

<span data-ttu-id="88b14-110">次の例では、OFTYPE 演算子を使用し、`OnsiteCourses` のコレクションから `Courses` のコレクションだけを取得して表示します。</span><span class="sxs-lookup"><span data-stu-id="88b14-110">The following example uses an OFTYPE operator to get and display a collection of only `OnsiteCourses` from a collection of `Courses`.</span></span>

[!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
[!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]

## <a name="see-also"></a><span data-ttu-id="88b14-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="88b14-111">See also</span></span>

- [<span data-ttu-id="88b14-112">Entity Framework 用の EntityClient プロバイダー</span><span class="sxs-lookup"><span data-stu-id="88b14-112">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
- [<span data-ttu-id="88b14-113">Entity SQL 言語</span><span class="sxs-lookup"><span data-stu-id="88b14-113">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
