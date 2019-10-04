---
title: '方法: 接続文字列を定義する'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 9ce0b427cac17fc338877c5f85d3648d15d5ee14
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833951"
---
# <a name="how-to-define-the-connection-string"></a><span data-ttu-id="ff87b-102">方法: 接続文字列を定義する</span><span class="sxs-lookup"><span data-stu-id="ff87b-102">How to: Define the Connection String</span></span>

<span data-ttu-id="ff87b-103">このトピックでは、概念モデルに接続するための接続文字列を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ff87b-103">This topic shows how to define the connection string that is used when connecting to a conceptual model.</span></span> <span data-ttu-id="ff87b-104">このトピックは、 [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100))概念モデルに基づいています。</span><span class="sxs-lookup"><span data-stu-id="ff87b-104">This topic is based on the [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) conceptual model.</span></span> <span data-ttu-id="ff87b-105">AdventureWorks Sales Model は、Entity Framework ドキュメントのタスク関連のトピック全体で使用されます。</span><span class="sxs-lookup"><span data-stu-id="ff87b-105">The AdventureWorks Sales Model is used throughout the task-related topics in the Entity Framework documentation.</span></span> <span data-ttu-id="ff87b-106">このトピックでは、Entity Framework が既に構成されており、AdventureWorks Sales Model が定義されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="ff87b-106">This topic assumes that you have already configured the Entity Framework and defined the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ff87b-107">詳細については、「[方法 :モデルファイルとマッピングファイル](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100))を手動で定義します。</span><span class="sxs-lookup"><span data-stu-id="ff87b-107">For more information, see [How to: Manually Define the Model and Mapping Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span></span> <span data-ttu-id="ff87b-108">このトピックの手順は、次の方法[でも説明されています。Entity Framework プロジェクト](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))を手動で構成します。</span><span class="sxs-lookup"><span data-stu-id="ff87b-108">The procedures in this topic are also included in [How to: Manually Configure an Entity Framework Project](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="ff87b-109">Visual Studio プロジェクトで Entity Data Model ウィザードを使用すると、.edmx ファイルが自動的に生成され、Entity Framework を使用するようにプロジェクトが構成されます。</span><span class="sxs-lookup"><span data-stu-id="ff87b-109">If you use the Entity Data Model Wizard in a Visual Studio project, it automatically generates an .edmx file and configures the project to use the Entity Framework.</span></span> <span data-ttu-id="ff87b-110">詳細については、「[方法 :Entity Data Model ウィザード](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))を使用します。</span><span class="sxs-lookup"><span data-stu-id="ff87b-110">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>

## <a name="to-define-the-entity-framework-connection-string"></a><span data-ttu-id="ff87b-111">Entity Framework 接続文字列を定義するには</span><span class="sxs-lookup"><span data-stu-id="ff87b-111">To define the Entity Framework connection string</span></span>

- <span data-ttu-id="ff87b-112">プロジェクトのアプリケーション構成ファイル (app.config) を開き、次の接続文字列を追加します。</span><span class="sxs-lookup"><span data-stu-id="ff87b-112">Open the project's application configuration file (app.config) and add the following connection string:</span></span>

```xml
<connectionStrings>
    <add name="AdventureWorksEntities" 
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

<span data-ttu-id="ff87b-113">プロジェクトにアプリケーション構成ファイルがない場合は、**プロジェクト** メニューの **新しい項目の追加** をクリックして**全般** カテゴリを選択し、**アプリケーション構成ファイル** を選択してから、次へ をクリックして追加することができます。を**追加**します。</span><span class="sxs-lookup"><span data-stu-id="ff87b-113">If your project does not have an application configuration file, you can add one by selecting **Add New Item** from the **Project** menu, selecting the **General** category, selecting **Application Configuration File**, and then clicking **Add**.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff87b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff87b-114">See also</span></span>

- <span data-ttu-id="ff87b-115">[クイック スタート](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ff87b-115">[Quickstart](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span></span>
- <span data-ttu-id="ff87b-116">[2 つのオブジェクトが等しいかどうかをテストする方法新しい .edmx ファイルを作成します。](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ff87b-116">[How to: Create a New .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span></span>
- <span data-ttu-id="ff87b-117">[ADO.NET Entity Data Model ツール](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ff87b-117">[ADO.NET Entity Data Model  Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
