---
title: '方法: EdmGen.exe を使用してオブジェクトレイヤー コードを生成する'
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: 9182f815a502488f955f64f6c19aad7865d0c7c6
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039980"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="97657-102">方法: EdmGen.exe を使用してオブジェクトレイヤー コードを生成する</span><span class="sxs-lookup"><span data-stu-id="97657-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>
<span data-ttu-id="97657-103">このトピックでは、 [EDM ジェネレーター (edmgen.exe)](edm-generator-edmgen-exe.md)ツールを使用して、.csdl ファイルに基づいてオブジェクトレイヤーコードを生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="97657-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="97657-104">EdmGen.exe を使用して Visual Basic プロジェクト用の School モデルのオブジェクトレイヤー コードを生成するには</span><span class="sxs-lookup"><span data-stu-id="97657-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="97657-105">School データベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="97657-105">Create the School database.</span></span> <span data-ttu-id="97657-106">詳細については、「 [School サンプルデータベースの作成](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97657-106">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="97657-107">School モデルを生成するか、School.csdl ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="97657-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="97657-108">詳細については、「[方法: edmgen.exe を使用してモデルファイルとマッピングファイルを生成する](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97657-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="97657-109">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="97657-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="97657-110">EdmGen.exe を使用して C# プロジェクト用の School モデルのオブジェクトレイヤー コードを生成するには</span><span class="sxs-lookup"><span data-stu-id="97657-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="97657-111">School データベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="97657-111">Create the School database.</span></span> <span data-ttu-id="97657-112">詳細については、「 [School サンプルデータベースの作成](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97657-112">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="97657-113">School モデルを生成するか、School.csdl ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="97657-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="97657-114">詳細については、「[方法: edmgen.exe を使用してモデルファイルとマッピングファイルを生成する](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97657-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="97657-115">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="97657-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="97657-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="97657-116">See also</span></span>

- [<span data-ttu-id="97657-117">モデリングとマッピング</span><span class="sxs-lookup"><span data-stu-id="97657-117">Modeling and Mapping</span></span>](modeling-and-mapping.md)
- <span data-ttu-id="97657-118">[方法: Entity Framework プロジェクトを手動で構成する](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="97657-118">[How to: Manually Configure an Entity Framework Project](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span></span>
- <span data-ttu-id="97657-119">[ADO.NET Entity Data Model ツール](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="97657-119">[ADO.NET Entity Data Model  Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
- <span data-ttu-id="97657-120">[方法: ビューを事前に生成してクエリのパフォーマンスを向上させる](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="97657-120">[How to: Pre-Generate Views to Improve Query Performance](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span></span>
- [<span data-ttu-id="97657-121">方法: EdmGen.exe を使用してモデル ファイルとマッピング ファイルを生成する</span><span class="sxs-lookup"><span data-stu-id="97657-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
