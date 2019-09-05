---
title: '方法: EntityCommand を使用してパラメーター化 Entity SQL クエリを実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e93fea43-7e03-4d7d-9fee-2517b8b88cba
ms.openlocfilehash: addda1a18ab325971b823d0131338a7bb824ad5c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251541"
---
# <a name="how-to-execute-a-parameterized-entity-sql-query-using-entitycommand"></a><span data-ttu-id="ccfa2-102">方法: EntityCommand を使用してパラメーター化 Entity SQL クエリを実行する</span><span class="sxs-lookup"><span data-stu-id="ccfa2-102">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>
<span data-ttu-id="ccfa2-103">このトピックでは、 [!INCLUDE[esql](../../../../../includes/esql-md.md)] <xref:System.Data.EntityClient.EntityCommand>オブジェクトを使用してパラメーターを持つクエリを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ccfa2-103">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that has parameters by using an <xref:System.Data.EntityClient.EntityCommand> object.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="ccfa2-104">この例のコードを実行するには</span><span class="sxs-lookup"><span data-stu-id="ccfa2-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="ccfa2-105">プロジェクトに[AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)を追加し、 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]を使用するようにプロジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="ccfa2-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="ccfa2-106">詳細については、「[方法 :Entity Data Model ウィザード](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))を使用します。</span><span class="sxs-lookup"><span data-stu-id="ccfa2-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="ccfa2-107">アプリケーションのコード ページで、次の `using` ステートメント (Visual Basic の場合は `Imports`) を追加します。</span><span class="sxs-lookup"><span data-stu-id="ccfa2-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="ccfa2-108">例</span><span class="sxs-lookup"><span data-stu-id="ccfa2-108">Example</span></span>  
 <span data-ttu-id="ccfa2-109">次の例では、2 つのパラメーターを持つクエリ文字列を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ccfa2-109">The following example shows how to construct a query string with two parameters.</span></span> <span data-ttu-id="ccfa2-110">次に、<xref:System.Data.EntityClient.EntityCommand> を作成した後、2 つのパラメーターを <xref:System.Data.EntityClient.EntityParameter> の <xref:System.Data.EntityClient.EntityCommand> コレクションに追加し、`Contact` アイテムのコレクションに対して反復処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="ccfa2-110">It then creates an <xref:System.Data.EntityClient.EntityCommand>, adds two parameters to the <xref:System.Data.EntityClient.EntityParameter> collection of that <xref:System.Data.EntityClient.EntityCommand>, and iterates through the collection of `Contact` items.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#parameterizedquerywithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#parameterizedquerywithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="ccfa2-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="ccfa2-111">See also</span></span>

- <span data-ttu-id="ccfa2-112">[方法: パラメーター化されたクエリの実行](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ccfa2-112">[How to: Execute a Parameterized Query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span></span>
- [<span data-ttu-id="ccfa2-113">Entity SQL 言語</span><span class="sxs-lookup"><span data-stu-id="ccfa2-113">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
