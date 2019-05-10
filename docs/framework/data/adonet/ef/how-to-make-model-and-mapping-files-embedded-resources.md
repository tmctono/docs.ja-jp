---
title: '方法: モデル ファイルとマッピング ファイルを組み込みリソースにする'
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: bc44b4e6a2f2b2745bd3bdcb2c003a5abe1e7207
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64632057"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="c27b4-102">方法: モデル ファイルとマッピング ファイルを組み込みリソースにする</span><span class="sxs-lookup"><span data-stu-id="c27b4-102">How to: Make Model and Mapping Files Embedded Resources</span></span>
<span data-ttu-id="c27b4-103">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]モデル ファイルとマッピング ファイルをアプリケーションの埋め込みリソースとしてデプロイすることができます。</span><span class="sxs-lookup"><span data-stu-id="c27b4-103">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="c27b4-104">モデル ファイルとマッピング ファイルが組み込まれたアセンブリは、エンティティ接続と同じアプリケーション ドメインに読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="c27b4-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="c27b4-105">詳細については、「[Connection Strings (接続文字列)](../../../../../docs/framework/data/adonet/ef/connection-strings.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c27b4-105">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span> <span data-ttu-id="c27b4-106">既定では、[!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] ツールによって、モデル ファイルとマッピング ファイルが組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="c27b4-106">By default, the [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] tools embed the model and mapping files.</span></span> <span data-ttu-id="c27b4-107">モデル ファイルとマッピング ファイルを手動で定義する場合は、[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] アプリケーションと共にモデル ファイルとマッピング ファイルが組み込みリソースとして確実に配置されるように、この手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c27b4-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c27b4-108">組み込みリソースを保持するには、モデル ファイルとマッピング ファイルを変更するたびに、この手順を繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c27b4-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="c27b4-109">モデル ファイルとマッピング ファイルを組み込むには</span><span class="sxs-lookup"><span data-stu-id="c27b4-109">To embed model and mapping files</span></span>  
  
1. <span data-ttu-id="c27b4-110">**ソリューション エクスプ ローラー**、概念 (.csdl) ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="c27b4-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2. <span data-ttu-id="c27b4-111">**プロパティ**ペインで、設定**ビルド アクション**に**埋め込まれたリソース**します。</span><span class="sxs-lookup"><span data-stu-id="c27b4-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3. <span data-ttu-id="c27b4-112">ストレージ (.ssdl) ファイルとマッピング (.msl) ファイルに対して手順 1. と手順 2. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c27b4-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4. <span data-ttu-id="c27b4-113">**ソリューション エクスプ ローラー**、App.config ファイルをダブルクリックし、変更、`Metadata`パラメーター、`connectionString`属性は、次の形式のいずれかに基づきます。</span><span class="sxs-lookup"><span data-stu-id="c27b4-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    - <span data-ttu-id="c27b4-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="c27b4-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span></span>  
  
    - <span data-ttu-id="c27b4-115">`Metadata=` `res://*/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="c27b4-115">`Metadata=` `res://*/<resourceName>;`</span></span>  
  
    - `Metadata=res://*;`  
  
     <span data-ttu-id="c27b4-116">詳細については、「[Connection Strings (接続文字列)](../../../../../docs/framework/data/adonet/ef/connection-strings.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c27b4-116">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c27b4-117">例</span><span class="sxs-lookup"><span data-stu-id="c27b4-117">Example</span></span>  
 <span data-ttu-id="c27b4-118">埋め込みモデルとマッピング ファイルを次の接続文字列が参照、 [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)します。</span><span class="sxs-lookup"><span data-stu-id="c27b4-118">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="c27b4-119">この接続文字列は、プロジェクトの App.config ファイルに格納されています。</span><span class="sxs-lookup"><span data-stu-id="c27b4-119">This connection string is stored in the project's App.config file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="c27b4-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="c27b4-120">See also</span></span>

- [<span data-ttu-id="c27b4-121">モデリングとマッピング</span><span class="sxs-lookup"><span data-stu-id="c27b4-121">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [<span data-ttu-id="c27b4-122">方法: 接続文字列を定義します。</span><span class="sxs-lookup"><span data-stu-id="c27b4-122">How to: Define the Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)
- [<span data-ttu-id="c27b4-123">方法: EntityConnection の接続文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="c27b4-123">How to: Build an EntityConnection Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)
- <span data-ttu-id="c27b4-124">[ADO.NET Entity Data Model ツール](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c27b4-124">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
