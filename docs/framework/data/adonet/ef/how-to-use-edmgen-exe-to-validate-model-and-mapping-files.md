---
title: '方法: EdmGen.exe を使用してモデル ファイルとマッピング ファイルを検証する'
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: ac278123e9b0927ba6b2ce07059561e7fbb3a898
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59329273"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a><span data-ttu-id="7070b-102">方法: EdmGen.exe を使用してモデル ファイルとマッピング ファイルを検証する</span><span class="sxs-lookup"><span data-stu-id="7070b-102">How to: Use EdmGen.exe to Validate Model and Mapping Files</span></span>
<span data-ttu-id="7070b-103">このトピックでは、使用する方法を示します、 [EDM ジェネレーター (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md)モデルとマッピング ファイルを検証するためのツール。</span><span class="sxs-lookup"><span data-stu-id="7070b-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to validate the model and mapping files.</span></span> <span data-ttu-id="7070b-104">詳細については、次を参照してください。 [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="7070b-104">For more information, see [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).</span></span>  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a><span data-ttu-id="7070b-105">EdmGen.exe を使用して School モデルを検証するには</span><span class="sxs-lookup"><span data-stu-id="7070b-105">To validate the School model using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="7070b-106">School データベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="7070b-106">Create the School database.</span></span> <span data-ttu-id="7070b-107">詳細については、次を参照してください。 [School サンプル データベースを作成する](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="7070b-107">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="7070b-108">School モデルを生成します。</span><span class="sxs-lookup"><span data-stu-id="7070b-108">Generate the School model.</span></span> <span data-ttu-id="7070b-109">詳細については、「[方法 :EdmGen.exe を使用して、モデルとマッピング ファイルを生成する](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)します。</span><span class="sxs-lookup"><span data-stu-id="7070b-109">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="7070b-110">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="7070b-110">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7070b-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="7070b-111">See also</span></span>

- <span data-ttu-id="7070b-112">[方法: Entity Framework プロジェクトを手動で構成します。](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7070b-112">[How to: Manually Configure an Entity Framework Project](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span></span>
- <span data-ttu-id="7070b-113">[ADO.NET Entity Data Model ツール](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7070b-113">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
- <span data-ttu-id="7070b-114">[方法: クエリのパフォーマンスを向上させるためにビューを事前に生成します。](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7070b-114">[How to: Pre-Generate Views to Improve Query Performance](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span></span>
- [<span data-ttu-id="7070b-115">方法: EdmGen.exe を使用してオブジェクト レイヤー コードを生成するには</span><span class="sxs-lookup"><span data-stu-id="7070b-115">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)
