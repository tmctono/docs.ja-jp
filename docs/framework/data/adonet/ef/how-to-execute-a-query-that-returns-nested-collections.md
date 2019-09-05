---
title: '方法: 入れ子になったコレクションを返すクエリを実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f7f385f3-ffcf-4f3b-af35-de8818938e5f
ms.openlocfilehash: accbf44c20e52fbce5104721b50bc1650d7fd565
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251498"
---
# <a name="how-to-execute-a-query-that-returns-nested-collections"></a><span data-ttu-id="8dca6-102">方法: 入れ子になったコレクションを返すクエリを実行する</span><span class="sxs-lookup"><span data-stu-id="8dca6-102">How to: Execute a Query that Returns Nested Collections</span></span>
<span data-ttu-id="8dca6-103">ここでは、<xref:System.Data.EntityClient.EntityCommand> オブジェクトを使用して概念モデルに対してコマンドを実行する方法、および <xref:System.Data.EntityClient.EntityDataReader> を使用して入れ子になったコレクションの結果を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8dca6-103">This shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the nested collection results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="8dca6-104">この例のコードを実行するには</span><span class="sxs-lookup"><span data-stu-id="8dca6-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="8dca6-105">プロジェクトに[AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)を追加し、 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]を使用するようにプロジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="8dca6-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="8dca6-106">詳細については、「[方法 :Entity Data Model ウィザード](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))を使用します。</span><span class="sxs-lookup"><span data-stu-id="8dca6-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="8dca6-107">アプリケーションのコード ページで、次の `using` ステートメント (Visual Basic の場合は `Imports`) を追加します。</span><span class="sxs-lookup"><span data-stu-id="8dca6-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="8dca6-108">例</span><span class="sxs-lookup"><span data-stu-id="8dca6-108">Example</span></span>  
 <span data-ttu-id="8dca6-109">*入れ子になったコレクション*は、別のコレクション内にあるコレクションです。</span><span class="sxs-lookup"><span data-stu-id="8dca6-109">A *nested collection* is a collection that is inside another collection.</span></span> <span data-ttu-id="8dca6-110">次に示すコードでは、`Contacts` のコレクションと、それぞれの `SalesOrderHeaders` に関連付けられている、`Contact` の入れ子になったコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="8dca6-110">The following code retrieves a collection of `Contacts` and the nested collections of `SalesOrderHeaders` that are associated with each `Contact`.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ReturnNestedCollectionWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#returnnestedcollectionwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ReturnNestedCollectionWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#returnnestedcollectionwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="8dca6-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="8dca6-111">See also</span></span>

- [<span data-ttu-id="8dca6-112">Entity Framework 用の EntityClient プロバイダー</span><span class="sxs-lookup"><span data-stu-id="8dca6-112">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
