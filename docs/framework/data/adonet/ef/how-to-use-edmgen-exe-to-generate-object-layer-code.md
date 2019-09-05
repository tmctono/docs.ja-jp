---
title: '方法: EdmGen.exe を使用してオブジェクトレイヤー コードを生成する'
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: b85bacff093c268cd35dca2ede36e6ceb74ca4d1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251406"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="bbf1b-102">方法: EdmGen.exe を使用してオブジェクトレイヤー コードを生成する</span><span class="sxs-lookup"><span data-stu-id="bbf1b-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>
<span data-ttu-id="bbf1b-103">このトピックでは、 [EDM ジェネレーター (edmgen.exe)](edm-generator-edmgen-exe.md)ツールを使用して、.csdl ファイルに基づいてオブジェクトレイヤーコードを生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbf1b-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="bbf1b-104">EdmGen.exe を使用して Visual Basic プロジェクト用の School モデルのオブジェクトレイヤー コードを生成するには</span><span class="sxs-lookup"><span data-stu-id="bbf1b-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="bbf1b-105">School データベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="bbf1b-105">Create the School database.</span></span> <span data-ttu-id="bbf1b-106">詳細については、「 [School サンプルデータベースの作成](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbf1b-106">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="bbf1b-107">School モデルを生成するか、School.csdl ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="bbf1b-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="bbf1b-108">詳細については、「[方法 :Edmgen.exe を使用して、モデルファイルとマッピングファイル](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)を生成します。</span><span class="sxs-lookup"><span data-stu-id="bbf1b-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="bbf1b-109">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="bbf1b-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="bbf1b-110">EdmGen.exe を使用して C# プロジェクト用の School モデルのオブジェクトレイヤー コードを生成するには</span><span class="sxs-lookup"><span data-stu-id="bbf1b-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="bbf1b-111">School データベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="bbf1b-111">Create the School database.</span></span> <span data-ttu-id="bbf1b-112">詳細については、「 [School サンプルデータベースの作成](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbf1b-112">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="bbf1b-113">School モデルを生成するか、School.csdl ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="bbf1b-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="bbf1b-114">詳細については、「[方法 :Edmgen.exe を使用して、モデルファイルとマッピングファイル](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)を生成します。</span><span class="sxs-lookup"><span data-stu-id="bbf1b-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="bbf1b-115">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="bbf1b-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bbf1b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="bbf1b-116">See also</span></span>

- [<span data-ttu-id="bbf1b-117">モデリングとマッピング</span><span class="sxs-lookup"><span data-stu-id="bbf1b-117">Modeling and Mapping</span></span>](modeling-and-mapping.md)
- <span data-ttu-id="bbf1b-118">[方法: Entity Framework プロジェクトを手動で構成する](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bbf1b-118">[How to: Manually Configure an Entity Framework Project](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span></span>
- <span data-ttu-id="bbf1b-119">[ADO.NET Entity Data Model ツール](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bbf1b-119">[ADO.NET Entity Data Model  Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
- <span data-ttu-id="bbf1b-120">[方法: クエリのパフォーマンスを向上させるためのビューを事前に生成する](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bbf1b-120">[How to: Pre-Generate Views to Improve Query Performance](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span></span>
- [<span data-ttu-id="bbf1b-121">方法: Edmgen.exe を使用して、モデルファイルとマッピングファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="bbf1b-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
