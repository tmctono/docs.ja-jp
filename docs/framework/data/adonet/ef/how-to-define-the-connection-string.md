---
title: '方法: 接続文字列を定義する'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 9b029644e0d4e4c7467fbe1e1144579e6edb3478
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536211"
---
# <a name="how-to-define-the-connection-string"></a><span data-ttu-id="c95ad-102">方法: 接続文字列を定義する</span><span class="sxs-lookup"><span data-stu-id="c95ad-102">How to: Define the Connection String</span></span>

<span data-ttu-id="c95ad-103">このトピックでは、概念モデルに接続するための接続文字列を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c95ad-103">This topic shows how to define the connection string that is used when connecting to a conceptual model.</span></span> <span data-ttu-id="c95ad-104">このトピックは、[AdventureWorks Sales](/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) の概念モデルが基になっています。</span><span class="sxs-lookup"><span data-stu-id="c95ad-104">This topic is based on the [AdventureWorks Sales](/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) conceptual model.</span></span> <span data-ttu-id="c95ad-105">AdventureWorks Sales Model は、Entity Framework ドキュメントのタスク関連のトピック全般で使用されます。</span><span class="sxs-lookup"><span data-stu-id="c95ad-105">The AdventureWorks Sales Model is used throughout the task-related topics in the Entity Framework documentation.</span></span> <span data-ttu-id="c95ad-106">このトピックでは、Entity Framework の構成が済んでいること、および AdventureWorks Sales Model が定義済みであることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c95ad-106">This topic assumes that you have already configured the Entity Framework and defined the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c95ad-107">詳細については、[モデル ファイルとマッピング ファイルを手動で定義する](/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c95ad-107">For more information, see [How to: Manually Define the Model and Mapping Files](/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span></span> <span data-ttu-id="c95ad-108">このトピックの手順は、「[方法: Entity Framework プロジェクトを手動で構成する](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))」にも含まれます。</span><span class="sxs-lookup"><span data-stu-id="c95ad-108">The procedures in this topic are also included in [How to: Manually Configure an Entity Framework Project](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="c95ad-109">Visual Studio プロジェクトで Entity Data Model ウィザードを使用した場合、自動的に .edmx ファイルが生成され、Entity Framework を使用するようにプロジェクトが構成されます。</span><span class="sxs-lookup"><span data-stu-id="c95ad-109">If you use the Entity Data Model Wizard in a Visual Studio project, it automatically generates an .edmx file and configures the project to use the Entity Framework.</span></span> <span data-ttu-id="c95ad-110">詳細については、[Entity Data Model ウィザードを使用する](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c95ad-110">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>

## <a name="to-define-the-entity-framework-connection-string"></a><span data-ttu-id="c95ad-111">Entity Framework 接続文字列を定義するには</span><span class="sxs-lookup"><span data-stu-id="c95ad-111">To define the Entity Framework connection string</span></span>

- <span data-ttu-id="c95ad-112">プロジェクトのアプリケーション構成ファイル (app.config) を開き、次の接続文字列を追加します。</span><span class="sxs-lookup"><span data-stu-id="c95ad-112">Open the project's application configuration file (app.config) and add the following connection string:</span></span>

```xml
<connectionStrings>
    <add name="AdventureWorksEntities"
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

<span data-ttu-id="c95ad-113">プロジェクトにアプリケーション構成ファイルが存在しない場合は、 **[プロジェクト]** メニューの **[新しい項目の追加]** を選択し、 **[全般]** カテゴリの **[アプリケーション構成ファイル]** を選択して、 **[追加]** をクリックすることによって追加できます。</span><span class="sxs-lookup"><span data-stu-id="c95ad-113">If your project does not have an application configuration file, you can add one by selecting **Add New Item** from the **Project** menu, selecting the **General** category, selecting **Application Configuration File**, and then clicking **Add**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c95ad-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="c95ad-114">See also</span></span>

- <span data-ttu-id="c95ad-115">[クイック スタート](/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c95ad-115">[Quickstart](/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span></span>
- <span data-ttu-id="c95ad-116">[方法: 新しい .edmx ファイルを作成する](/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c95ad-116">[How to: Create a New .edmx File](/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span></span>
- <span data-ttu-id="c95ad-117">[ADO.NET Entity Data Model ツール](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c95ad-117">[ADO.NET Entity Data Model  Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
