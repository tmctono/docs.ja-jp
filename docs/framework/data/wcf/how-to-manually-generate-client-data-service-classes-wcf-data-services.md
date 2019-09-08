---
title: '方法: クライアントデータサービスクラスを手動で生成する (WCF Data Services)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: 106f1cedb33c0c1b333df0b9f2b8c2a70d458a0d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790429"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a><span data-ttu-id="d5b1a-102">方法: クライアントデータサービスクラスを手動で生成する (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="d5b1a-102">How to: Manually Generate Client Data Service Classes (WCF Data Services)</span></span>
<span data-ttu-id="d5b1a-103">WCF Data Services を Visual Studio と統合すると、 **[サービス参照の追加]** ダイアログボックスを使用して visual studio プロジェクトのデータサービスへの参照を追加するときに、クライアントデータサービスクラスが自動的に生成されるようになります。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-103">WCF Data Services integrates with Visual Studio to enable you to automatically generate client data service classes when you use the **Add Service Reference** dialog box to add a reference to a data service in a Visual Studio project.</span></span> <span data-ttu-id="d5b1a-104">詳細については、「[方法 :データサービス参照](how-to-add-a-data-service-reference-wcf-data-services.md)を追加します。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-104">For more information, see [How to: Add a Data Service Reference](how-to-add-a-data-service-reference-wcf-data-services.md).</span></span> <span data-ttu-id="d5b1a-105">コード生成ツールの `DataSvcUtil.exe` を使用して、同じクライアント データ サービス クラスを手動で生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-105">You can also manually generate the same client data service classes by using the code-generation tool, `DataSvcUtil.exe`.</span></span> <span data-ttu-id="d5b1a-106">このツールは WCF Data Services に含まれており、データサービス定義から .NET Framework クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-106">This tool, which is included with WCF Data Services, generates .NET Framework classes from the data service definition.</span></span> <span data-ttu-id="d5b1a-107">このツールを使用して、概念モデル (.csdl) ファイル、および Visual Studio プロジェクトの Entity Framework モデルを表す .edmx ファイルからデータ サービス クラスを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-107">It can also be used to generate data service classes from the conceptual model (.csdl) file and from the .edmx file that represents an Entity Framework model in a Visual Studio project.</span></span>

 <span data-ttu-id="d5b1a-108">このトピックの例は、Northwind サンプル データ サービスに基づいてクライアント データ サービス クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-108">The example in this topic creates client data service classes based on the Northwind sample data service.</span></span> <span data-ttu-id="d5b1a-109">このサービスは、 [WCF Data Services のクイックスタート](quickstart-wcf-data-services.md)を完了したときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-109">This service is created when you complete the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="d5b1a-110">このトピックのいくつかの例では、Northwind モデルの概念モデル ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-110">Some examples in this topic require the conceptual model file for the Northwind model.</span></span> <span data-ttu-id="d5b1a-111">詳細については、「[方法 :Edmgen.exe を使用して、モデルファイルとマッピングファイル](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)を生成します。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-111">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span> <span data-ttu-id="d5b1a-112">このトピックのいくつかの例では、Northwind モデルの .edmx ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-112">Some examples in this topic require the .edmx file for the Northwind model.</span></span> <span data-ttu-id="d5b1a-113">詳細については、「 [.Edmx ファイルの概要](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-113">For more information, see [.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).</span></span>

### <a name="to-generate-c-classes-that-support-data-binding"></a><span data-ttu-id="d5b1a-114">データ バインディングをサポートする C# クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="d5b1a-114">To generate C# classes that support data binding</span></span>

- <span data-ttu-id="d5b1a-115">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-115">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="d5b1a-116">`/uri:` パラメーターの値は Northwind サンプル データ サービスのインスタンスの URI で置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-116">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a><span data-ttu-id="d5b1a-117">データ バインディングをサポートする Visual Basic クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="d5b1a-117">To generate Visual Basic classes that support data binding</span></span>

- <span data-ttu-id="d5b1a-118">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-118">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="d5b1a-119">`/uri:` パラメーターの値は Northwind サンプル データ サービスのインスタンスの URI で置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-119">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-service-uri"></a><span data-ttu-id="d5b1a-120">サービス URI に基づいて C# クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="d5b1a-120">To generate C# classes based on the service URI</span></span>

- <span data-ttu-id="d5b1a-121">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-121">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="d5b1a-122">`/uri:` パラメーターの値は Northwind サンプル データ サービスのインスタンスの URI で置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-122">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a><span data-ttu-id="d5b1a-123">サービス URI に基づいて Visual Basic クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="d5b1a-123">To generate Visual Basic classes based on the service URI</span></span>

- <span data-ttu-id="d5b1a-124">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-124">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="d5b1a-125">`/uri:` パラメーターの値は Northwind サンプル データ サービスのインスタンスの URI で置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-125">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="d5b1a-126">概念モデル ファイル (CSDL) に基づいて C# を生成するには</span><span class="sxs-lookup"><span data-stu-id="d5b1a-126">To generate C# classes based on the conceptual model file (CSDL)</span></span>

- <span data-ttu-id="d5b1a-127">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-127">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="d5b1a-128">概念モデル ファイル (CSDL) に基づいて Visual Basic を生成するには</span><span class="sxs-lookup"><span data-stu-id="d5b1a-128">To generate Visual Basic classes based on the conceptual model file (CSDL)</span></span>

- <span data-ttu-id="d5b1a-129">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-129">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb
    ```

### <a name="to-generate-c-classes-based-on-the-edmx-file"></a><span data-ttu-id="d5b1a-130">.edmx ファイルに基づいて C# クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="d5b1a-130">To generate C# classes based on the .edmx file</span></span>

- <span data-ttu-id="d5b1a-131">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-131">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a><span data-ttu-id="d5b1a-132">.edmx ファイルに基づいて Visual Basic クラスを生成するには</span><span class="sxs-lookup"><span data-stu-id="d5b1a-132">To generate Visual Basic classes based on the .edmx file</span></span>

- <span data-ttu-id="d5b1a-133">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5b1a-133">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb
    ```

## <a name="see-also"></a><span data-ttu-id="d5b1a-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5b1a-134">See also</span></span>

- [<span data-ttu-id="d5b1a-135">データ サービス クライアント ライブラリの生成</span><span class="sxs-lookup"><span data-stu-id="d5b1a-135">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)
- [<span data-ttu-id="d5b1a-136">方法: データサービス参照の追加</span><span class="sxs-lookup"><span data-stu-id="d5b1a-136">How to: Add a Data Service Reference</span></span>](how-to-add-a-data-service-reference-wcf-data-services.md)
- [<span data-ttu-id="d5b1a-137">WCF Data Service クライアント ユーティリティ (DataSvcUtil.exe) </span><span class="sxs-lookup"><span data-stu-id="d5b1a-137">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>](wcf-data-service-client-utility-datasvcutil-exe.md)
