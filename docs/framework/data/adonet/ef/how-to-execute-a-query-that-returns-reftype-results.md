---
title: '方法: RefType 結果を返すクエリを実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dbbfbcd-93f5-4546-9dbf-e5fa290b69fa
ms.openlocfilehash: c9f3b7e19770c89bbb200913bf7fcf44f901ea99
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854576"
---
# <a name="how-to-execute-a-query-that-returns-reftype-results"></a><span data-ttu-id="0bd52-102">方法: RefType 結果を返すクエリを実行する</span><span class="sxs-lookup"><span data-stu-id="0bd52-102">How to: Execute a Query that Returns RefType Results</span></span>
<span data-ttu-id="0bd52-103">このトピックでは、<xref:System.Data.EntityClient.EntityCommand> オブジェクトを使用して概念モデルに対してコマンドを実行する方法と、<xref:System.Data.Metadata.Edm.RefType> を使用して <xref:System.Data.EntityClient.EntityDataReader> の結果を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0bd52-103">This topic shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the <xref:System.Data.Metadata.Edm.RefType> results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="0bd52-104">この例のコードを実行するには</span><span class="sxs-lookup"><span data-stu-id="0bd52-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="0bd52-105">プロジェクトに[AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)を追加し、Entity Framework を使用するようにプロジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="0bd52-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="0bd52-106">詳細については、「[方法 :Entity Data Model ウィザード](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))を使用します。</span><span class="sxs-lookup"><span data-stu-id="0bd52-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="0bd52-107">アプリケーションのコード ページで、次の `using` ステートメント (Visual Basic の場合は `Imports`) を追加します。</span><span class="sxs-lookup"><span data-stu-id="0bd52-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="0bd52-108">例</span><span class="sxs-lookup"><span data-stu-id="0bd52-108">Example</span></span>  
 <span data-ttu-id="0bd52-109">この例は、<xref:System.Data.Metadata.Edm.RefType> の結果を返すクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="0bd52-109">This example executes a query that returns <xref:System.Data.Metadata.Edm.RefType> results.</span></span> <span data-ttu-id="0bd52-110">次のクエリを引数として `ExecuteRefTypeQuery` 関数に渡すと、関数はエンティティへの参照を返します。</span><span class="sxs-lookup"><span data-stu-id="0bd52-110">If you pass the following query as an argument to the `ExecuteRefTypeQuery` function, the function returns a reference to the entity:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#REF2](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref2)]  
  
 <span data-ttu-id="0bd52-111">パラメーター化されたクエリを渡す場合は、次のように、<xref:System.Data.EntityClient.EntityParameter> オブジェクトの <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> プロパティに <xref:System.Data.EntityClient.EntityCommand> オブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="0bd52-111">If you pass a parameterized query, like the following, add the <xref:System.Data.EntityClient.EntityParameter> objects to the <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> property on the <xref:System.Data.EntityClient.EntityCommand> object.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#REF3](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref3)]  
  
 [!code-csharp[DP EntityServices Concepts#eSQLRefTypes](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#esqlreftypes)]
 [!code-vb[DP EntityServices Concepts#eSQLRefTypes](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#esqlreftypes)]  
  
## <a name="see-also"></a><span data-ttu-id="0bd52-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="0bd52-112">See also</span></span>

- [<span data-ttu-id="0bd52-113">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="0bd52-113">Entity SQL Reference</span></span>](./language-reference/entity-sql-reference.md)
- [<span data-ttu-id="0bd52-114">Entity Framework 用の EntityClient プロバイダー</span><span class="sxs-lookup"><span data-stu-id="0bd52-114">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
