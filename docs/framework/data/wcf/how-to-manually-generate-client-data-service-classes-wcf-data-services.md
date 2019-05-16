---
title: '方法: 手動で生成するクライアント データ サービス クラス (WCF Data Services)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: fdca85360e34d6854604103c9d0ac22c5b829cf5
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634007"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a><span data-ttu-id="0a866-102">方法: 手動で生成するクライアント データ サービス クラス (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="0a866-102">How to: Manually Generate Client Data Service Classes (WCF Data Services)</span></span>
<span data-ttu-id="0a866-103">WCF Data Services を使用する場合、クライアント データ サービス クラスを自動的に生成するための Visual Studio と統合、**サービス参照の追加**ダイアログ ボックスを Visual Studio プロジェクトにデータ サービスへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="0a866-103">WCF Data Services integrates with Visual Studio to enable you to automatically generate client data service classes when you use the **Add Service Reference** dialog box to add a reference to a data service in a Visual Studio project.</span></span> <span data-ttu-id="0a866-104">詳細については、「[方法 :データ サービス参照を追加](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="0a866-104">For more information, see [How to: Add a Data Service Reference](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span></span> <span data-ttu-id="0a866-105">コード生成ツールの `DataSvcUtil.exe` を使用して、同じクライアント データ サービス クラスを手動で生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="0a866-105">You can also manually generate the same client data service classes by using the code-generation tool, `DataSvcUtil.exe`.</span></span> <span data-ttu-id="0a866-106">WCF Data Services に含まれるこのツールは、データ サービス定義から .NET Framework のクラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="0a866-106">This tool, which is included with WCF Data Services, generates .NET Framework classes from the data service definition.</span></span> <span data-ttu-id="0a866-107">このツールを使用して、概念モデル (.csdl) ファイル、および Visual Studio プロジェクトの Entity Framework モデルを表す .edmx ファイルからデータ サービス クラスを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="0a866-107">It can also be used to generate data service classes from the conceptual model (.csdl) file and from the .edmx file that represents an Entity Framework model in a Visual Studio project.</span></span>

 <span data-ttu-id="0a866-108">このトピックの例は、Northwind サンプル データ サービスに基づいてクライアント データ サービス クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="0a866-108">The example in this topic creates client data service classes based on the Northwind sample data service.</span></span> <span data-ttu-id="0a866-109">このサービスの作成を完了すると、 [WCF Data Services クイック スタート](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="0a866-109">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="0a866-110">このトピックのいくつかの例では、Northwind モデルの概念モデル ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="0a866-110">Some examples in this topic require the conceptual model file for the Northwind model.</span></span> <span data-ttu-id="0a866-111">詳細については、「[方法 :EdmGen.exe を使用して、モデルとマッピング ファイルを生成する](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)します。</span><span class="sxs-lookup"><span data-stu-id="0a866-111">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span> <span data-ttu-id="0a866-112">このトピックのいくつかの例では、Northwind モデルの .edmx ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="0a866-112">Some examples in this topic require the .edmx file for the Northwind model.</span></span> <span data-ttu-id="0a866-113">詳細については、次を参照してください。 [.edmx ファイルの概要](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="0a866-113">For more information, see [.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).</span></span>

### <a name="to-generate-c-classes-that-support-data-binding"></a><span data-ttu-id="0a866-114">データ バインディングをサポートする C# クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="0a866-114">To generate C# classes that support data binding</span></span>

- <span data-ttu-id="0a866-115">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="0a866-115">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  <span data-ttu-id="0a866-116">`/uri:` パラメーターの値は Northwind サンプル データ サービスのインスタンスの URI で置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a866-116">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a><span data-ttu-id="0a866-117">データ バインディングをサポートする Visual Basic クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="0a866-117">To generate Visual Basic classes that support data binding</span></span>

- <span data-ttu-id="0a866-118">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="0a866-118">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  <span data-ttu-id="0a866-119">`/uri:` パラメーターの値は Northwind サンプル データ サービスのインスタンスの URI で置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a866-119">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-service-uri"></a><span data-ttu-id="0a866-120">サービス URI に基づいて C# クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="0a866-120">To generate C# classes based on the service URI</span></span>

- <span data-ttu-id="0a866-121">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="0a866-121">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  <span data-ttu-id="0a866-122">`/uri:` パラメーターの値は Northwind サンプル データ サービスのインスタンスの URI で置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a866-122">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a><span data-ttu-id="0a866-123">サービス URI に基づいて Visual Basic クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="0a866-123">To generate Visual Basic classes based on the service URI</span></span>

- <span data-ttu-id="0a866-124">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="0a866-124">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  <span data-ttu-id="0a866-125">`/uri:` パラメーターの値は Northwind サンプル データ サービスのインスタンスの URI で置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a866-125">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="0a866-126">概念モデル ファイル (CSDL) に基づいて C# を生成するには</span><span class="sxs-lookup"><span data-stu-id="0a866-126">To generate C# classes based on the conceptual model file (CSDL)</span></span>

- <span data-ttu-id="0a866-127">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="0a866-127">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="0a866-128">概念モデル ファイル (CSDL) に基づいて Visual Basic を生成するには</span><span class="sxs-lookup"><span data-stu-id="0a866-128">To generate Visual Basic classes based on the conceptual model file (CSDL)</span></span>

- <span data-ttu-id="0a866-129">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="0a866-129">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb
    ```

### <a name="to-generate-c-classes-based-on-the-edmx-file"></a><span data-ttu-id="0a866-130">.edmx ファイルに基づいて C# クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="0a866-130">To generate C# classes based on the .edmx file</span></span>

- <span data-ttu-id="0a866-131">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="0a866-131">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a><span data-ttu-id="0a866-132">.edmx ファイルに基づいて Visual Basic クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="0a866-132">To generate Visual Basic classes based on the .edmx file</span></span>

- <span data-ttu-id="0a866-133">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="0a866-133">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb
    ```

## <a name="see-also"></a><span data-ttu-id="0a866-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a866-134">See also</span></span>

- [<span data-ttu-id="0a866-135">データ サービス クライアント ライブラリの生成</span><span class="sxs-lookup"><span data-stu-id="0a866-135">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)
- [<span data-ttu-id="0a866-136">方法: データ サービス参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="0a866-136">How to: Add a Data Service Reference</span></span>](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
- [<span data-ttu-id="0a866-137">WCF Data Service クライアント ユーティリティ (DataSvcUtil.exe) </span><span class="sxs-lookup"><span data-stu-id="0a866-137">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)
