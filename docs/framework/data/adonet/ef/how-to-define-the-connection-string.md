---
title: '方法: 接続文字列を定義する'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 8386f93d0e80aa824b1e91a130812b9b3a2b3619
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306386"
---
# <a name="how-to-define-the-connection-string"></a><span data-ttu-id="dc407-102">方法: 接続文字列を定義する</span><span class="sxs-lookup"><span data-stu-id="dc407-102">How to: Define the Connection String</span></span>

<span data-ttu-id="dc407-103">このトピックでは、概念モデルに接続するための接続文字列を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dc407-103">This topic shows how to define the connection string that is used when connecting to a conceptual model.</span></span> <span data-ttu-id="dc407-104">このトピックではに基づいて、 [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100))概念モデル。</span><span class="sxs-lookup"><span data-stu-id="dc407-104">This topic is based on the [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) conceptual model.</span></span> <span data-ttu-id="dc407-105">AdventureWorks Sales Model は、[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] ドキュメントのタスク関連のトピック全般で使用されます。</span><span class="sxs-lookup"><span data-stu-id="dc407-105">The AdventureWorks Sales Model is used throughout the task-related topics in the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] documentation.</span></span> <span data-ttu-id="dc407-106">このトピックでは、既に構成されていることを想定しています、 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] AdventureWorks Sales Model が定義されているとします。</span><span class="sxs-lookup"><span data-stu-id="dc407-106">This topic assumes that you have already configured the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] and defined the AdventureWorks Sales Model.</span></span> <span data-ttu-id="dc407-107">詳細については、「[方法 :モデルを定義して、マッピング ファイルを手動で](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="dc407-107">For more information, see [How to: Manually Define the Model and Mapping Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span></span> <span data-ttu-id="dc407-108">このトピックの手順でに含まれるも[方法。Entity Framework プロジェクトを手動で構成](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="dc407-108">The procedures in this topic are also included in [How to: Manually Configure an Entity Framework Project](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="dc407-109">Visual Studio プロジェクトで、Entity Data Model ウィザードを使用する場合に自動的に .edmx ファイルを生成し、使用するプロジェクトを構成します、、[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="dc407-109">If you use the Entity Data Model Wizard in a Visual Studio project, it automatically generates an .edmx file and configures the project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="dc407-110">詳細については、「[方法 :エンティティ データ モデル ウィザードを使用します。](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="dc407-110">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))</span></span>

## <a name="to-define-the-entity-framework-connection-string"></a><span data-ttu-id="dc407-111">Entity Framework 接続文字列を定義するには</span><span class="sxs-lookup"><span data-stu-id="dc407-111">To define the Entity Framework connection string</span></span>

- <span data-ttu-id="dc407-112">プロジェクトのアプリケーション構成ファイル (app.config) を開き、次の接続文字列を追加します。</span><span class="sxs-lookup"><span data-stu-id="dc407-112">Open the project's application configuration file (app.config) and add the following connection string:</span></span>

```xml
<connectionStrings>
    <add name="AdventureWorksEntities" 
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

<span data-ttu-id="dc407-113">プロジェクトがアプリケーション構成ファイルを持たない場合は、1 つを選択して、追加**新しい項目の追加**から、**プロジェクト** メニューを選択すると、**全般**カテゴリで、選択**アプリケーション構成ファイル**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="dc407-113">If your project does not have an application configuration file, you can add one by selecting **Add New Item** from the **Project** menu, selecting the **General** category, selecting **Application Configuration File**, and then clicking **Add**.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc407-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc407-114">See also</span></span>

- <span data-ttu-id="dc407-115">[クイック スタート](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="dc407-115">[Quickstart](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span></span>
- <span data-ttu-id="dc407-116">[方法: 新しい .edmx ファイルを作成します。](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="dc407-116">[How to: Create a New .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span></span>
- <span data-ttu-id="dc407-117">[ADO.NET Entity Data Model ツール](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="dc407-117">[ADO.NET Entity Data Model  Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
