---
title: データ定義言語の操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec50083d-44f4-4093-9b23-5eacd601f96e
ms.openlocfilehash: da37dc2ff08f127e17cd4e6f7cbeab88f2c8d5e9
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583449"
---
# <a name="working-with-data-definition-language"></a><span data-ttu-id="e5121-102">データ定義言語の操作</span><span class="sxs-lookup"><span data-stu-id="e5121-102">Working with Data Definition Language</span></span>
<span data-ttu-id="e5121-103">.NET Framework バージョン 4 以降、[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]データ定義言語 (DDL) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e5121-103">Starting with the .NET Framework version 4, the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] supports data definition language (DDL).</span></span> <span data-ttu-id="e5121-104">これにより、接続文字列、およびストレージ (SSDL) モデルのメターデータに基づいて、データベース インスタンスを作成または削除できます。</span><span class="sxs-lookup"><span data-stu-id="e5121-104">This allows you to create or delete a database instance based on the connection string and the metadata of the storage (SSDL) model.</span></span>  
  
 <span data-ttu-id="e5121-105"><xref:System.Data.Objects.ObjectContext> の次のメソッドでは、接続文字列と SSDL の内容を使用して、データベースの作成と削除、データベースが存在するかどうかの確認、生成された DDL スクリプトの表示を実行します。</span><span class="sxs-lookup"><span data-stu-id="e5121-105">The following methods on the <xref:System.Data.Objects.ObjectContext> use the connection string and the SSDL content to accomplish the following: create or delete the database, check whether the database exists, and view the generated DDL script:</span></span>  
  
- <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A>  
  
- <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>  
  
- <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>  
  
- <xref:System.Data.Objects.ObjectContext.CreateDatabaseScript%2A>  
  
> [!NOTE]
>  <span data-ttu-id="e5121-106">DDL コマンドを実行するには、十分なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="e5121-106">Executing the DDL commands assumes sufficient permissions.</span></span>  
  
 <span data-ttu-id="e5121-107">上記に示したメソッドは、ほとんどの作業を基になる ADO.NET データ プロバイダーに委任します。</span><span class="sxs-lookup"><span data-stu-id="e5121-107">The methods previously listed delegate most of the work to the underlying ADO.NET data provider.</span></span> <span data-ttu-id="e5121-108">データベース オブジェクトの生成に使用される名前付け規則が、照会および更新に使用される規則と一致していることは、プロバイダーによって保証されています。</span><span class="sxs-lookup"><span data-stu-id="e5121-108">It is the provider’s responsibility to ensure that the naming convention used to generate database objects is consistent with conventions used for querying and updates.</span></span>  
  
 <span data-ttu-id="e5121-109">次の例は、既存のモデルを基にデータベースを生成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e5121-109">The following example shows you how to generate the database based on the existing model.</span></span> <span data-ttu-id="e5121-110">また、新しいエンティティ オブジェクトはオブジェクト コンテキストに追加され、データベースに保存されます。</span><span class="sxs-lookup"><span data-stu-id="e5121-110">It also adds a new entity object to the object context and then saves it to the database.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="e5121-111">手順</span><span class="sxs-lookup"><span data-stu-id="e5121-111">Procedures</span></span>  
  
#### <a name="to-define-a-database-based-on-the-existing-model"></a><span data-ttu-id="e5121-112">既存のモデルに基づいてデータベースを定義するには</span><span class="sxs-lookup"><span data-stu-id="e5121-112">To define a database based on the existing model</span></span>  
  
1. <span data-ttu-id="e5121-113">コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="e5121-113">Create a console application.</span></span>  
  
2. <span data-ttu-id="e5121-114">既存のモデルをアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="e5121-114">Add an existing model to your application.</span></span>  
  
    1. <span data-ttu-id="e5121-115">という名前の空のモデルを追加`SchoolModel`します。</span><span class="sxs-lookup"><span data-stu-id="e5121-115">Add an empty model named `SchoolModel`.</span></span> <span data-ttu-id="e5121-116">空のモデルを作成するを参照してください。、[方法。新しい .edmx ファイルを作成する](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))トピック。</span><span class="sxs-lookup"><span data-stu-id="e5121-116">To create an empty model, see the [How to: Create a New .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100)) topic.</span></span>  
  
     <span data-ttu-id="e5121-117">SchoolModel.edmx ファイルがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="e5121-117">The SchoolModel.edmx file is added to your project.</span></span>  
  
    1. <span data-ttu-id="e5121-118">概念、ストレージをコピーしてから、School モデルのコンテンツのマッピング、 [School モデル](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100))トピック。</span><span class="sxs-lookup"><span data-stu-id="e5121-118">Copy the conceptual, storage, and mapping content for the School model from the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) topic.</span></span>  
  
    2. <span data-ttu-id="e5121-119">SchoolModel.edmx ファイルを開き、`edmx:Runtime` タグ内にその内容を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="e5121-119">Open the SchoolModel.edmx file and paste the content within the `edmx:Runtime` tags.</span></span>  
  
3. <span data-ttu-id="e5121-120">main 関数に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e5121-120">Add the following code to your main function.</span></span> <span data-ttu-id="e5121-121">このコードでは、データベース サーバーへの接続文字列を初期化し、DDL スクリプトを表示して、データベースを作成します。さらに、コンテキストに新しいエンティティを追加して、データベースに変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="e5121-121">The code initializes the connection string to your database server, views the DDL script, creates the database, adds a new entity to the context, and saves the changes to the database.</span></span>  
  
     [!code-csharp[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/csharp/VS_Snippets_Data/DP ObjectServices Concepts/CS/Source.cs#ddl)]
     [!code-vb[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP ObjectServices Concepts/VB/Source.vb#ddl)]
