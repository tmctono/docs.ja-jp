---
title: '方法: クライアント データ サービス クラスを手動で生成する (WCF Data Services)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: 368f2546652d21be44c0ffb4cc5f279c56beda51
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165993"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a><span data-ttu-id="768b6-102">方法: クライアント データ サービス クラスを手動で生成する (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="768b6-102">How to: Manually Generate Client Data Service Classes (WCF Data Services)</span></span>

<span data-ttu-id="768b6-103">WCF Data Services を Visual Studio に統合すると、 **[サービス参照の追加]** ダイアログ ボックスを使用して参照を Visual Studio プロジェクト内のデータ サービスに追加するときに、クライアント データ サービス クラスを自動的に生成することが可能になります。</span><span class="sxs-lookup"><span data-stu-id="768b6-103">WCF Data Services integrates with Visual Studio to enable you to automatically generate client data service classes when you use the **Add Service Reference** dialog box to add a reference to a data service in a Visual Studio project.</span></span> <span data-ttu-id="768b6-104">詳細については、[データ サービス参照を追加する](how-to-add-a-data-service-reference-wcf-data-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="768b6-104">For more information, see [How to: Add a Data Service Reference](how-to-add-a-data-service-reference-wcf-data-services.md).</span></span> <span data-ttu-id="768b6-105">コード生成ツールの `DataSvcUtil.exe` を使用して、同じクライアント データ サービス クラスを手動で生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="768b6-105">You can also manually generate the same client data service classes by using the code-generation tool, `DataSvcUtil.exe`.</span></span> <span data-ttu-id="768b6-106">WCF Data Services に含まれるこのツールでは、データ サービス定義から .NET Framework クラスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="768b6-106">This tool, which is included with WCF Data Services, generates .NET Framework classes from the data service definition.</span></span> <span data-ttu-id="768b6-107">このツールを使用して、概念モデル (.csdl) ファイル、および Visual Studio プロジェクトの Entity Framework モデルを表す .edmx ファイルからデータ サービス クラスを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="768b6-107">It can also be used to generate data service classes from the conceptual model (.csdl) file and from the .edmx file that represents an Entity Framework model in a Visual Studio project.</span></span>

 <span data-ttu-id="768b6-108">このトピックの例は、Northwind サンプル データ サービスに基づいてクライアント データ サービス クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="768b6-108">The example in this topic creates client data service classes based on the Northwind sample data service.</span></span> <span data-ttu-id="768b6-109">このサービスは、[WCF Data Services クイック スタート](quickstart-wcf-data-services.md)を完了したときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="768b6-109">This service is created when you complete the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="768b6-110">このトピックのいくつかの例では、Northwind モデルの概念モデル ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="768b6-110">Some examples in this topic require the conceptual model file for the Northwind model.</span></span> <span data-ttu-id="768b6-111">詳細については、[EdmGen.exe を使用してモデル ファイルとマッピング ファイルを生成する](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="768b6-111">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span> <span data-ttu-id="768b6-112">このトピックのいくつかの例では、Northwind モデルの .edmx ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="768b6-112">Some examples in this topic require the .edmx file for the Northwind model.</span></span> <span data-ttu-id="768b6-113">詳しくは、「[.edmx ファイルの概要](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="768b6-113">For more information, see [.edmx File Overview](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).</span></span>

### <a name="to-generate-c-classes-that-support-data-binding"></a><span data-ttu-id="768b6-114">データ バインディングをサポートする C# クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="768b6-114">To generate C# classes that support data binding</span></span>

- <span data-ttu-id="768b6-115">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="768b6-115">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="768b6-116">`/uri:` パラメーターの値は Northwind サンプル データ サービスのインスタンスの URI で置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="768b6-116">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a><span data-ttu-id="768b6-117">データ バインディングをサポートする Visual Basic クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="768b6-117">To generate Visual Basic classes that support data binding</span></span>

- <span data-ttu-id="768b6-118">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="768b6-118">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="768b6-119">`/uri:` パラメーターの値は Northwind サンプル データ サービスのインスタンスの URI で置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="768b6-119">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-service-uri"></a><span data-ttu-id="768b6-120">サービス URI に基づいて C# クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="768b6-120">To generate C# classes based on the service URI</span></span>

- <span data-ttu-id="768b6-121">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="768b6-121">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="768b6-122">`/uri:` パラメーターの値は Northwind サンプル データ サービスのインスタンスの URI で置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="768b6-122">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a><span data-ttu-id="768b6-123">サービス URI に基づいて Visual Basic クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="768b6-123">To generate Visual Basic classes based on the service URI</span></span>

- <span data-ttu-id="768b6-124">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="768b6-124">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="768b6-125">`/uri:` パラメーターの値は Northwind サンプル データ サービスのインスタンスの URI で置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="768b6-125">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="768b6-126">概念モデル ファイル (CSDL) に基づいて C# を生成するには</span><span class="sxs-lookup"><span data-stu-id="768b6-126">To generate C# classes based on the conceptual model file (CSDL)</span></span>

- <span data-ttu-id="768b6-127">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="768b6-127">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="768b6-128">概念モデル ファイル (CSDL) に基づいて Visual Basic を生成するには</span><span class="sxs-lookup"><span data-stu-id="768b6-128">To generate Visual Basic classes based on the conceptual model file (CSDL)</span></span>

- <span data-ttu-id="768b6-129">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="768b6-129">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb
    ```

### <a name="to-generate-c-classes-based-on-the-edmx-file"></a><span data-ttu-id="768b6-130">.edmx ファイルに基づいて C# クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="768b6-130">To generate C# classes based on the .edmx file</span></span>

- <span data-ttu-id="768b6-131">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="768b6-131">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a><span data-ttu-id="768b6-132">.edmx ファイルに基づいて Visual Basic クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="768b6-132">To generate Visual Basic classes based on the .edmx file</span></span>

- <span data-ttu-id="768b6-133">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="768b6-133">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb
    ```

## <a name="see-also"></a><span data-ttu-id="768b6-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="768b6-134">See also</span></span>

- [<span data-ttu-id="768b6-135">データ サービス クライアント ライブラリの生成</span><span class="sxs-lookup"><span data-stu-id="768b6-135">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)
- [<span data-ttu-id="768b6-136">方法: データ サービス参照を追加する</span><span class="sxs-lookup"><span data-stu-id="768b6-136">How to: Add a Data Service Reference</span></span>](how-to-add-a-data-service-reference-wcf-data-services.md)
- [<span data-ttu-id="768b6-137">WCF Data Service クライアント ユーティリティ (DataSvcUtil.exe) </span><span class="sxs-lookup"><span data-stu-id="768b6-137">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>](wcf-data-service-client-utility-datasvcutil-exe.md)
