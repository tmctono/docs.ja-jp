---
title: '方法: モデル ファイルとマッピング ファイルを組み込みリソースにする'
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: c88e0c09742d76c7508d7d782eabbe46035d3501
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251443"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="4c305-102">方法: モデル ファイルとマッピング ファイルを組み込みリソースにする</span><span class="sxs-lookup"><span data-stu-id="4c305-102">How to: Make Model and Mapping Files Embedded Resources</span></span>
<span data-ttu-id="4c305-103">を[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]使用すると、モデルファイルとマッピングファイルをアプリケーションの埋め込みリソースとして配置できます。</span><span class="sxs-lookup"><span data-stu-id="4c305-103">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="4c305-104">モデル ファイルとマッピング ファイルが組み込まれたアセンブリは、エンティティ接続と同じアプリケーション ドメインに読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c305-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="4c305-105">詳細については、「[Connection Strings (接続文字列)](connection-strings.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4c305-105">For more information, see [Connection Strings](connection-strings.md).</span></span> <span data-ttu-id="4c305-106">既定では、Entity Data Model ツールによってモデルファイルとマッピングファイルが埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="4c305-106">By default, the Entity Data Model tools embed the model and mapping files.</span></span> <span data-ttu-id="4c305-107">モデル ファイルとマッピング ファイルを手動で定義する場合は、[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] アプリケーションと共にモデル ファイルとマッピング ファイルが組み込みリソースとして確実に配置されるように、この手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="4c305-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4c305-108">組み込みリソースを保持するには、モデル ファイルとマッピング ファイルを変更するたびに、この手順を繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c305-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="4c305-109">モデル ファイルとマッピング ファイルを組み込むには</span><span class="sxs-lookup"><span data-stu-id="4c305-109">To embed model and mapping files</span></span>  
  
1. <span data-ttu-id="4c305-110">**ソリューションエクスプローラー**で、概念 (.csdl) ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c305-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2. <span data-ttu-id="4c305-111">**[プロパティ]** ペインで、 **[ビルドアクション]** を **[埋め込みリソース]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="4c305-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3. <span data-ttu-id="4c305-112">ストレージ (.ssdl) ファイルとマッピング (.msl) ファイルに対して手順 1. と手順 2. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4c305-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4. <span data-ttu-id="4c305-113">**ソリューションエクスプローラー**で、app.config ファイルをダブルクリックし、次のいずれかの`Metadata`形式に基づい`connectionString`て属性のパラメーターを変更します。</span><span class="sxs-lookup"><span data-stu-id="4c305-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    - <span data-ttu-id="4c305-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="4c305-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span></span>  
  
    - <span data-ttu-id="4c305-115">`Metadata=` `res://*/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="4c305-115">`Metadata=` `res://*/<resourceName>;`</span></span>  
  
    - `Metadata=res://*;`  
  
     <span data-ttu-id="4c305-116">詳細については、「[Connection Strings (接続文字列)](connection-strings.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4c305-116">For more information, see [Connection Strings](connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c305-117">例</span><span class="sxs-lookup"><span data-stu-id="4c305-117">Example</span></span>  
 <span data-ttu-id="4c305-118">次の接続文字列は、 [AdventureWorks Sales model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)の埋め込みモデルファイルとマッピングファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="4c305-118">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="4c305-119">この接続文字列は、プロジェクトの App.config ファイルに格納されています。</span><span class="sxs-lookup"><span data-stu-id="4c305-119">This connection string is stored in the project's App.config file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="4c305-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c305-120">See also</span></span>

- [<span data-ttu-id="4c305-121">モデリングとマッピング</span><span class="sxs-lookup"><span data-stu-id="4c305-121">Modeling and Mapping</span></span>](modeling-and-mapping.md)
- [<span data-ttu-id="4c305-122">方法: 接続文字列を定義する</span><span class="sxs-lookup"><span data-stu-id="4c305-122">How to: Define the Connection String</span></span>](how-to-define-the-connection-string.md)
- [<span data-ttu-id="4c305-123">方法: EntityConnection 接続文字列を作成する</span><span class="sxs-lookup"><span data-stu-id="4c305-123">How to: Build an EntityConnection Connection String</span></span>](how-to-build-an-entityconnection-connection-string.md)
- <span data-ttu-id="4c305-124">[ADO.NET Entity Data Model ツール](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4c305-124">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
