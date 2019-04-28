---
title: '方法: 手動で生成するクライアント データ サービス クラス (WCF Data Services)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: d197088f94614aac007c0adc310500ae4609f757
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788714"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a><span data-ttu-id="e9cd3-102">方法: 手動で生成するクライアント データ サービス クラス (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="e9cd3-102">How to: Manually Generate Client Data Service Classes (WCF Data Services)</span></span>
<span data-ttu-id="e9cd3-103">WCF Data Services を使用する場合、クライアント データ サービス クラスを自動的に生成するための Visual Studio と統合、**サービス参照の追加**ダイアログ ボックスを Visual Studio プロジェクトにデータ サービスへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-103">WCF Data Services integrates with Visual Studio to enable you to automatically generate client data service classes when you use the **Add Service Reference** dialog box to add a reference to a data service in a Visual Studio project.</span></span> <span data-ttu-id="e9cd3-104">詳細については、「[方法 :データ サービス参照を追加](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-104">For more information, see [How to: Add a Data Service Reference](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span></span> <span data-ttu-id="e9cd3-105">コード生成ツールの `DataSvcUtil.exe` を使用して、同じクライアント データ サービス クラスを手動で生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-105">You can also manually generate the same client data service classes by using the code-generation tool, `DataSvcUtil.exe`.</span></span> <span data-ttu-id="e9cd3-106">WCF Data Services に含まれるこのツールは、データ サービス定義から .NET Framework のクラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-106">This tool, which is included with WCF Data Services, generates .NET Framework classes from the data service definition.</span></span> <span data-ttu-id="e9cd3-107">このツールを使用して、概念モデル (.csdl) ファイル、および Visual Studio プロジェクトの Entity Framework モデルを表す .edmx ファイルからデータ サービス クラスを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-107">It can also be used to generate data service classes from the conceptual model (.csdl) file and from the .edmx file that represents an Entity Framework model in a Visual Studio project.</span></span>

 <span data-ttu-id="e9cd3-108">このトピックの例は、Northwind サンプル データ サービスに基づいてクライアント データ サービス クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-108">The example in this topic creates client data service classes based on the Northwind sample data service.</span></span> <span data-ttu-id="e9cd3-109">このサービスの作成を完了すると、 [WCF Data Services クイック スタート](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-109">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="e9cd3-110">このトピックのいくつかの例では、Northwind モデルの概念モデル ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-110">Some examples in this topic require the conceptual model file for the Northwind model.</span></span> <span data-ttu-id="e9cd3-111">詳細については、「[方法 :EdmGen.exe を使用して、モデルとマッピング ファイルを生成する](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-111">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span> <span data-ttu-id="e9cd3-112">このトピックのいくつかの例では、Northwind モデルの .edmx ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-112">Some examples in this topic require the .edmx file for the Northwind model.</span></span> <span data-ttu-id="e9cd3-113">詳細については、次を参照してください。 [.edmx ファイルの概要](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-113">For more information, see [.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).</span></span>

### <a name="to-generate-c-classes-that-support-data-binding"></a><span data-ttu-id="e9cd3-114">データ バインディングをサポートする C# クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="e9cd3-114">To generate C# classes that support data binding</span></span>

- <span data-ttu-id="e9cd3-115">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-115">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  <span data-ttu-id="e9cd3-116">`/uri:` パラメーターの値は Northwind サンプル データ サービスのインスタンスの URI で置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-116">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a><span data-ttu-id="e9cd3-117">データ バインディングをサポートする Visual Basic クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="e9cd3-117">To generate Visual Basic classes that support data binding</span></span>

- <span data-ttu-id="e9cd3-118">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-118">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  <span data-ttu-id="e9cd3-119">`/uri:` パラメーターの値は Northwind サンプル データ サービスのインスタンスの URI で置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-119">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-service-uri"></a><span data-ttu-id="e9cd3-120">サービス URI に基づいて C# クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="e9cd3-120">To generate C# classes based on the service URI</span></span>

- <span data-ttu-id="e9cd3-121">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-121">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  <span data-ttu-id="e9cd3-122">`/uri:` パラメーターの値は Northwind サンプル データ サービスのインスタンスの URI で置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-122">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a><span data-ttu-id="e9cd3-123">サービス URI に基づいて Visual Basic クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="e9cd3-123">To generate Visual Basic classes based on the service URI</span></span>

- <span data-ttu-id="e9cd3-124">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-124">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  <span data-ttu-id="e9cd3-125">`/uri:` パラメーターの値は Northwind サンプル データ サービスのインスタンスの URI で置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-125">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="e9cd3-126">概念モデル ファイル (CSDL) に基づいて C# を生成するには</span><span class="sxs-lookup"><span data-stu-id="e9cd3-126">To generate C# classes based on the conceptual model file (CSDL)</span></span>

- <span data-ttu-id="e9cd3-127">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-127">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="e9cd3-128">概念モデル ファイル (CSDL) に基づいて Visual Basic を生成するには</span><span class="sxs-lookup"><span data-stu-id="e9cd3-128">To generate Visual Basic classes based on the conceptual model file (CSDL)</span></span>

- <span data-ttu-id="e9cd3-129">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-129">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb
    ```

### <a name="to-generate-c-classes-based-on-the-edmx-file"></a><span data-ttu-id="e9cd3-130">.edmx ファイルに基づいて C# クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="e9cd3-130">To generate C# classes based on the .edmx file</span></span>

- <span data-ttu-id="e9cd3-131">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-131">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a><span data-ttu-id="e9cd3-132">.edmx ファイルに基づいて Visual Basic クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="e9cd3-132">To generate Visual Basic classes based on the .edmx file</span></span>

- <span data-ttu-id="e9cd3-133">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-133">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb
    ```

## <a name="see-also"></a><span data-ttu-id="e9cd3-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9cd3-134">See also</span></span>

- [<span data-ttu-id="e9cd3-135">データ サービス クライアント ライブラリの生成</span><span class="sxs-lookup"><span data-stu-id="e9cd3-135">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)
- [<span data-ttu-id="e9cd3-136">方法: データ サービス参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="e9cd3-136">How to: Add a Data Service Reference</span></span>](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
- [<span data-ttu-id="e9cd3-137">WCF Data Service クライアント ユーティリティ (DataSvcUtil.exe) </span><span class="sxs-lookup"><span data-stu-id="e9cd3-137">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)