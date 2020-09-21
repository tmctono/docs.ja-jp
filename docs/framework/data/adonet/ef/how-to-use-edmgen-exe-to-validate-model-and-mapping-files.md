---
title: '方法: EdmGen.exe を使用してモデル ファイルとマッピング ファイルを検証する'
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: a5e3124eb907b8077df7db4d71240f6e6b7bae63
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544506"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a><span data-ttu-id="47c16-102">方法: EdmGen.exe を使用してモデル ファイルとマッピング ファイルを検証する</span><span class="sxs-lookup"><span data-stu-id="47c16-102">How to: Use EdmGen.exe to Validate Model and Mapping Files</span></span>
<span data-ttu-id="47c16-103">このトピックでは、[EDM ジェネレーター (EdmGen.exe)](edm-generator-edmgen-exe.md) ツールを使用してモデル ファイルとマッピング ファイルを検証する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="47c16-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](edm-generator-edmgen-exe.md) tool to validate the model and mapping files.</span></span> <span data-ttu-id="47c16-104">詳細については、「[Entity Data Model](../entity-data-model.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47c16-104">For more information, see [Entity Data Model](../entity-data-model.md).</span></span>  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a><span data-ttu-id="47c16-105">EdmGen.exe を使用して School モデルを検証するには</span><span class="sxs-lookup"><span data-stu-id="47c16-105">To validate the School model using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="47c16-106">School データベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="47c16-106">Create the School database.</span></span> <span data-ttu-id="47c16-107">詳細については、「[School サンプル データベースの作成](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47c16-107">For more information, see [Creating the School Sample Database](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="47c16-108">School モデルを生成します。</span><span class="sxs-lookup"><span data-stu-id="47c16-108">Generate the School model.</span></span> <span data-ttu-id="47c16-109">詳細については、[EdmGen.exe を使用してモデル ファイルとマッピング ファイルを生成する](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47c16-109">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="47c16-110">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="47c16-110">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="47c16-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="47c16-111">See also</span></span>

- <span data-ttu-id="47c16-112">[方法: Entity Framework プロジェクトを手動で構成する](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="47c16-112">[How to: Manually Configure an Entity Framework Project](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span></span>
- <span data-ttu-id="47c16-113">[ADO.NET Entity Data Model ツール](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="47c16-113">[ADO.NET Entity Data Model Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
- <span data-ttu-id="47c16-114">[方法: ビューを事前に生成してクエリ パフォーマンスを向上させる](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="47c16-114">[How to: Pre-Generate Views to Improve Query Performance](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span></span>
- [<span data-ttu-id="47c16-115">方法: EdmGen.exe を使用してオブジェクトレイヤー コードを生成する</span><span class="sxs-lookup"><span data-stu-id="47c16-115">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>](how-to-use-edmgen-exe-to-generate-object-layer-code.md)
