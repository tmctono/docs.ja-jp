---
title: '方法: EdmGen.exe を使用してオブジェクトレイヤー コードを生成する'
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: 04b35dbb5e487e573a2adfff196b79e10afdfb61
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188230"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="95a90-102">方法: EdmGen.exe を使用してオブジェクトレイヤー コードを生成する</span><span class="sxs-lookup"><span data-stu-id="95a90-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>
<span data-ttu-id="95a90-103">このトピックでは、使用する方法を示します、 [EDM ジェネレーター (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) .csdl ファイルに基づいてオブジェクト レイヤー コードを生成するためのツール。</span><span class="sxs-lookup"><span data-stu-id="95a90-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="95a90-104">EdmGen.exe を使用して Visual Basic プロジェクト用の School モデルのオブジェクトレイヤー コードを生成するには</span><span class="sxs-lookup"><span data-stu-id="95a90-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="95a90-105">School データベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="95a90-105">Create the School database.</span></span> <span data-ttu-id="95a90-106">詳細については、次を参照してください。 [School サンプル データベースを作成する](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="95a90-106">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="95a90-107">School モデルを生成するか、School.csdl ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="95a90-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="95a90-108">詳細については、「[方法 :EdmGen.exe を使用して、モデルとマッピング ファイルを生成する](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)します。</span><span class="sxs-lookup"><span data-stu-id="95a90-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="95a90-109">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="95a90-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="95a90-110">EdmGen.exe を使用して C# プロジェクト用の School モデルのオブジェクトレイヤー コードを生成するには</span><span class="sxs-lookup"><span data-stu-id="95a90-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="95a90-111">School データベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="95a90-111">Create the School database.</span></span> <span data-ttu-id="95a90-112">詳細については、次を参照してください。 [School サンプル データベースを作成する](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="95a90-112">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="95a90-113">School モデルを生成するか、School.csdl ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="95a90-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="95a90-114">詳細については、「[方法 :EdmGen.exe を使用して、モデルとマッピング ファイルを生成する](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)します。</span><span class="sxs-lookup"><span data-stu-id="95a90-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="95a90-115">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="95a90-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="95a90-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="95a90-116">See also</span></span>

- [<span data-ttu-id="95a90-117">モデリングとマッピング</span><span class="sxs-lookup"><span data-stu-id="95a90-117">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [<span data-ttu-id="95a90-118">方法: Entity Framework プロジェクトを手動で構成します。</span><span class="sxs-lookup"><span data-stu-id="95a90-118">How to: Manually Configure an Entity Framework Project</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [<span data-ttu-id="95a90-119">ADO.NET Entity Data Model ツール</span><span class="sxs-lookup"><span data-stu-id="95a90-119">ADO.NET Entity Data Model  Tools</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [<span data-ttu-id="95a90-120">方法: クエリのパフォーマンスを向上させるためにビューを事前に生成します。</span><span class="sxs-lookup"><span data-stu-id="95a90-120">How to: Pre-Generate Views to Improve Query Performance</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [<span data-ttu-id="95a90-121">方法: EdmGen.exe を使用してモデル ファイルとマッピング ファイルを生成する</span><span class="sxs-lookup"><span data-stu-id="95a90-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
