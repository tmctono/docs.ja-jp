---
title: '方法: EntityConnection の接続文字列を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5bd1a748-3df7-4d0a-a607-14f25e3175e9
ms.openlocfilehash: 33a52b2542a2e312f7fbb8b7ca09a8b85662d2d4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251549"
---
# <a name="how-to-build-an-entityconnection-connection-string"></a><span data-ttu-id="6774d-102">方法: EntityConnection の接続文字列を作成する</span><span class="sxs-lookup"><span data-stu-id="6774d-102">How to: Build an EntityConnection Connection String</span></span>
<span data-ttu-id="6774d-103">このトピックでは、<xref:System.Data.EntityClient.EntityConnection> を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6774d-103">This topic provides an example of how to build an <xref:System.Data.EntityClient.EntityConnection>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="6774d-104">この例のコードを実行するには</span><span class="sxs-lookup"><span data-stu-id="6774d-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="6774d-105">プロジェクトに[AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)を追加し、 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]を使用するようにプロジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="6774d-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="6774d-106">詳細については、「[方法 :Entity Data Model ウィザード](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))を使用します。</span><span class="sxs-lookup"><span data-stu-id="6774d-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="6774d-107">アプリケーションのコード ページで、次の `using` ステートメント (Visual Basic の場合は `Imports`) を追加します。</span><span class="sxs-lookup"><span data-stu-id="6774d-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="6774d-108">例</span><span class="sxs-lookup"><span data-stu-id="6774d-108">Example</span></span>  
 <span data-ttu-id="6774d-109">次の例では、基になるプロバイダーの <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType> を初期化した後、<xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType> オブジェクトを初期化して、このオブジェクトを <xref:System.Data.EntityClient.EntityConnection> のコンストラクターに渡しています。</span><span class="sxs-lookup"><span data-stu-id="6774d-109">The following example initializes the <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType> for the underlying provider, then initializes the <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType> object and passes this object to the constructor of the <xref:System.Data.EntityClient.EntityConnection>.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#buildingconnectionstringwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#buildingconnectionstringwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="6774d-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="6774d-110">See also</span></span>

- <span data-ttu-id="6774d-111">[方法: オブジェクトコンテキストで EntityConnection を使用する](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738461(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6774d-111">[How to: Use EntityConnection with an Object Context](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738461(v=vs.100))</span></span>
- [<span data-ttu-id="6774d-112">Entity Framework 用の EntityClient プロバイダー</span><span class="sxs-lookup"><span data-stu-id="6774d-112">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
