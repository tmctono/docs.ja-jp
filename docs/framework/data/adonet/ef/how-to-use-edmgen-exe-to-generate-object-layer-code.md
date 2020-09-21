---
title: '方法: EdmGen.exe を使用してオブジェクトレイヤー コードを生成する'
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: 9a73a803d310ebd847e49f4bd71609f8ef9f2944
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546641"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="90e1f-102">方法: EdmGen.exe を使用してオブジェクトレイヤー コードを生成する</span><span class="sxs-lookup"><span data-stu-id="90e1f-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>
<span data-ttu-id="90e1f-103">このトピックでは、[EDM ジェネレーター (EdmGen.exe)](edm-generator-edmgen-exe.md) ツールを使用して、.csdl ファイルに基づくオブジェクトレイヤー コードを生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="90e1f-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="90e1f-104">EdmGen.exe を使用して Visual Basic プロジェクト用の School モデルのオブジェクトレイヤー コードを生成するには</span><span class="sxs-lookup"><span data-stu-id="90e1f-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="90e1f-105">School データベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="90e1f-105">Create the School database.</span></span> <span data-ttu-id="90e1f-106">詳細については、「[School サンプル データベースの作成](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90e1f-106">For more information, see [Creating the School Sample Database](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="90e1f-107">School モデルを生成するか、School.csdl ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="90e1f-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="90e1f-108">詳細については、[EdmGen.exe を使用してモデル ファイルとマッピング ファイルを生成する](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90e1f-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="90e1f-109">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="90e1f-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="90e1f-110">EdmGen.exe を使用して C# プロジェクト用の School モデルのオブジェクトレイヤー コードを生成するには</span><span class="sxs-lookup"><span data-stu-id="90e1f-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="90e1f-111">School データベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="90e1f-111">Create the School database.</span></span> <span data-ttu-id="90e1f-112">詳細については、「[School サンプル データベースの作成](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90e1f-112">For more information, see [Creating the School Sample Database](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="90e1f-113">School モデルを生成するか、School.csdl ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="90e1f-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="90e1f-114">詳細については、[EdmGen.exe を使用してモデル ファイルとマッピング ファイルを生成する](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90e1f-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="90e1f-115">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="90e1f-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="90e1f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="90e1f-116">See also</span></span>

- [<span data-ttu-id="90e1f-117">モデリングとマッピング</span><span class="sxs-lookup"><span data-stu-id="90e1f-117">Modeling and Mapping</span></span>](modeling-and-mapping.md)
- <span data-ttu-id="90e1f-118">[方法: Entity Framework プロジェクトを手動で構成する](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="90e1f-118">[How to: Manually Configure an Entity Framework Project](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span></span>
- <span data-ttu-id="90e1f-119">[ADO.NET Entity Data Model ツール](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="90e1f-119">[ADO.NET Entity Data Model  Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
- <span data-ttu-id="90e1f-120">[方法: ビューを事前に生成してクエリ パフォーマンスを向上させる](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="90e1f-120">[How to: Pre-Generate Views to Improve Query Performance](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span></span>
- [<span data-ttu-id="90e1f-121">方法: EdmGen.exe を使用してモデル ファイルとマッピング ファイルを生成する</span><span class="sxs-lookup"><span data-stu-id="90e1f-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
