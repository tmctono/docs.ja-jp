---
title: '方法: モデル ファイルとマッピング ファイルを組み込みリソースにする'
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: 371f8f0317295ee39d543b5637afb93102036b62
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854597"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="a9d55-102">方法: モデル ファイルとマッピング ファイルを組み込みリソースにする</span><span class="sxs-lookup"><span data-stu-id="a9d55-102">How to: Make Model and Mapping Files Embedded Resources</span></span>
<span data-ttu-id="a9d55-103">Entity Framework を使用すると、モデルファイルとマッピングファイルをアプリケーションの埋め込みリソースとして配置できます。</span><span class="sxs-lookup"><span data-stu-id="a9d55-103">The Entity Framework enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="a9d55-104">モデル ファイルとマッピング ファイルが組み込まれたアセンブリは、エンティティ接続と同じアプリケーション ドメインに読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9d55-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="a9d55-105">詳細については、「[Connection Strings (接続文字列)](connection-strings.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a9d55-105">For more information, see [Connection Strings](connection-strings.md).</span></span> <span data-ttu-id="a9d55-106">既定では、Entity Data Model ツールによってモデルファイルとマッピングファイルが埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="a9d55-106">By default, the Entity Data Model tools embed the model and mapping files.</span></span> <span data-ttu-id="a9d55-107">モデルファイルとマッピングファイルを手動で定義する場合は、次の手順を使用して、ファイルが埋め込みリソースとして Entity Framework アプリケーションと共に配置されるようにします。</span><span class="sxs-lookup"><span data-stu-id="a9d55-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an Entity Framework application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a9d55-108">組み込みリソースを保持するには、モデル ファイルとマッピング ファイルを変更するたびに、この手順を繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9d55-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="a9d55-109">モデル ファイルとマッピング ファイルを組み込むには</span><span class="sxs-lookup"><span data-stu-id="a9d55-109">To embed model and mapping files</span></span>  
  
1. <span data-ttu-id="a9d55-110">**ソリューションエクスプローラー**で、概念 (.csdl) ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="a9d55-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2. <span data-ttu-id="a9d55-111">**[プロパティ]** ペインで、 **[ビルドアクション]** を **[埋め込みリソース]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="a9d55-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3. <span data-ttu-id="a9d55-112">ストレージ (.ssdl) ファイルとマッピング (.msl) ファイルに対して手順 1. と手順 2. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a9d55-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4. <span data-ttu-id="a9d55-113">**ソリューションエクスプローラー**で、app.config ファイルをダブルクリックし、次のいずれかの`Metadata`形式に基づい`connectionString`て属性のパラメーターを変更します。</span><span class="sxs-lookup"><span data-stu-id="a9d55-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    - <span data-ttu-id="a9d55-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="a9d55-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span></span>  
  
    - <span data-ttu-id="a9d55-115">`Metadata=` `res://*/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="a9d55-115">`Metadata=` `res://*/<resourceName>;`</span></span>  
  
    - `Metadata=res://*;`  
  
     <span data-ttu-id="a9d55-116">詳細については、「[Connection Strings (接続文字列)](connection-strings.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a9d55-116">For more information, see [Connection Strings](connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9d55-117">例</span><span class="sxs-lookup"><span data-stu-id="a9d55-117">Example</span></span>  
 <span data-ttu-id="a9d55-118">次の接続文字列は、 [AdventureWorks Sales model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)の埋め込みモデルファイルとマッピングファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="a9d55-118">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="a9d55-119">この接続文字列は、プロジェクトの App.config ファイルに格納されています。</span><span class="sxs-lookup"><span data-stu-id="a9d55-119">This connection string is stored in the project's App.config file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="a9d55-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9d55-120">See also</span></span>

- [<span data-ttu-id="a9d55-121">モデリングとマッピング</span><span class="sxs-lookup"><span data-stu-id="a9d55-121">Modeling and Mapping</span></span>](modeling-and-mapping.md)
- [<span data-ttu-id="a9d55-122">方法: 接続文字列を定義する</span><span class="sxs-lookup"><span data-stu-id="a9d55-122">How to: Define the Connection String</span></span>](how-to-define-the-connection-string.md)
- [<span data-ttu-id="a9d55-123">方法: EntityConnection 接続文字列を作成する</span><span class="sxs-lookup"><span data-stu-id="a9d55-123">How to: Build an EntityConnection Connection String</span></span>](how-to-build-an-entityconnection-connection-string.md)
- <span data-ttu-id="a9d55-124">[ADO.NET Entity Data Model ツール](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a9d55-124">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
