---
title: '方法: EntityCommand を使用してパラメーター化されたストアド プロシージャを実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4f5639bf-bb7f-4982-bb1d-c7caa4348888
ms.openlocfilehash: a2196be1a5fb6b9c676542ab5bcc74b1824df9cc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251521"
---
# <a name="how-to-execute-a-parameterized-stored-procedure-using-entitycommand"></a><span data-ttu-id="a3f42-102">方法: EntityCommand を使用してパラメーター化されたストアド プロシージャを実行する</span><span class="sxs-lookup"><span data-stu-id="a3f42-102">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>
<span data-ttu-id="a3f42-103">このトピックでは、<xref:System.Data.EntityClient.EntityCommand> クラスを使用して、パラメーター化されたストアド プロシージャを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a3f42-103">This topic shows how to execute a parameterized stored procedure by using the <xref:System.Data.EntityClient.EntityCommand> class.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="a3f42-104">この例のコードを実行するには</span><span class="sxs-lookup"><span data-stu-id="a3f42-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="a3f42-105">[School モデル](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100))をプロジェクトに追加し、 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]を使用するようにプロジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="a3f42-105">Add the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="a3f42-106">詳細については、「[方法 :Entity Data Model ウィザード](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3f42-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="a3f42-107">アプリケーションのコード ページで、次の `using` ステートメント (Visual Basic の場合は `Imports`) を追加します。</span><span class="sxs-lookup"><span data-stu-id="a3f42-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. <span data-ttu-id="a3f42-108">`GetStudentGrades` ストアド プロシージャをインポートし、戻り値の型として `CourseGrade` エンティティを指定します。</span><span class="sxs-lookup"><span data-stu-id="a3f42-108">Import the `GetStudentGrades` stored procedure and specify `CourseGrade` entities as a return type.</span></span> <span data-ttu-id="a3f42-109">ストアドプロシージャをインポートする方法の詳細について[は、「方法:ストアドプロシージャ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896231(v=vs.100))をインポートします。</span><span class="sxs-lookup"><span data-stu-id="a3f42-109">For information on how to import a stored procedure, see [How to: Import a Stored Procedure](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896231(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3f42-110">例</span><span class="sxs-lookup"><span data-stu-id="a3f42-110">Example</span></span>  
 <span data-ttu-id="a3f42-111">次のコードでは、`GetStudentGrades` ストアド プロシージャが実行されます。`StudentId` は必須パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="a3f42-111">The following code executes the `GetStudentGrades` stored procedure where `StudentId` is a required parameter.</span></span> <span data-ttu-id="a3f42-112">結果は <xref:System.Data.EntityClient.EntityDataReader> によって読み取られます。</span><span class="sxs-lookup"><span data-stu-id="a3f42-112">The results are then read by an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#storedprocwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#storedprocwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="a3f42-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3f42-113">See also</span></span>

- [<span data-ttu-id="a3f42-114">Entity Framework 用の EntityClient プロバイダー</span><span class="sxs-lookup"><span data-stu-id="a3f42-114">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
