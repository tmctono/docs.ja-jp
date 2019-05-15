---
title: WCF Data Service クライアント ユーティリティ (DataSvcUtil.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: bf812f45e4a4090becd8dfafe035d39d1d851860
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583643"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a><span data-ttu-id="7f2d9-102">WCF Data Service クライアント ユーティリティ (DataSvcUtil.exe)</span><span class="sxs-lookup"><span data-stu-id="7f2d9-102">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>

<span data-ttu-id="7f2d9-103">DataSvcUtil.exe は、コマンド ライン ツールを使用する WCF Data Services によって提供される、[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]フィードし、.NET Framework クライアント アプリケーションからデータ サービスにアクセスするために必要なクライアント データ サービス クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-103">DataSvcUtil.exe is a command-line tool provided by WCF Data Services that consumes an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed and generates the client data service classes that are needed to access a data service from a .NET Framework client application.</span></span> <span data-ttu-id="7f2d9-104">このユーティリティでは、以下のメタデータ ソースを使用してデータ クラスを生成できます。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-104">This utility can generate data classes by using the following metadata sources:</span></span>

- <span data-ttu-id="7f2d9-105">データ サービスのルート URI。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-105">The root URI of a data service.</span></span> <span data-ttu-id="7f2d9-106">ユーティリティは、データ サービスによって公開されるデータ モデルが記述されたサービス メタデータ ドキュメントを要求します。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-106">The utility requests the service metadata document, which describes the data model exposed by the data service.</span></span> <span data-ttu-id="7f2d9-107">詳細については、次を参照してください[OData:。サービス メタデータ ドキュメント](https://go.microsoft.com/fwlink/?LinkId=186070)します。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-107">For more information, see [OData: Service Metadata Document](https://go.microsoft.com/fwlink/?LinkId=186070).</span></span>

- <span data-ttu-id="7f2d9-108">定義されている概念スキーマ定義言語 (CSDL) を使用して定義されているデータ モデル ファイル (.csdl)、 [ \[MC-CSDL\]:概念スキーマ定義ファイル形式](https://go.microsoft.com/fwlink/?LinkID=159072)仕様。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-108">A data model file (.csdl) defined by using the conceptual schema definition language (CSDL), as defined in the [\[MC-CSDL\]: Conceptual Schema Definition File Format](https://go.microsoft.com/fwlink/?LinkID=159072) specification.</span></span>

- <span data-ttu-id="7f2d9-109">Entity Framework に付属する Entity Data Model ツールを使用して作成された .edmx ファイル。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-109">An .edmx file created by using the Entity Data Model tools that are provided with the Entity Framework.</span></span> <span data-ttu-id="7f2d9-110">詳細については、次を参照してください、 [ \[MC-EDMX\]:。データ サービス パッケージング形式のエンティティ データ モデル](https://go.microsoft.com/fwlink/?LinkID=178833)仕様。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-110">For more information, see the [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](https://go.microsoft.com/fwlink/?LinkID=178833) specification.</span></span>

<span data-ttu-id="7f2d9-111">詳細については、「[方法 :クライアント データ サービス クラスを手動で生成](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-111">For more information, see [How to: Manually Generate Client Data Service Classes](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>

<span data-ttu-id="7f2d9-112">DataSvcUtil.exe ツールは、.NET Framework ディレクトリにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-112">The DataSvcUtil.exe tool is installed in the .NET Framework directory.</span></span> <span data-ttu-id="7f2d9-113">多くの場合、これにある*C:\Windows\Microsoft.NET\Framework\v4.0*します。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-113">In many cases, this is located in *C:\Windows\Microsoft.NET\Framework\v4.0*.</span></span> <span data-ttu-id="7f2d9-114">64 ビット システムでは、これにある*C:\Windows\Microsoft.NET\Framework64\v4.0*します。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-114">For 64-bit systems, this is located in *C:\Windows\Microsoft.NET\Framework64\v4.0*.</span></span> <span data-ttu-id="7f2d9-115">アクセスすることできますも DataSvcUtil.exe ツール開発者コマンド プロンプトから Visual Studio の。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-115">You can also access the DataSvcUtil.exe tool from Developer Command Prompt for Visual Studio.</span></span>

## <a name="syntax"></a><span data-ttu-id="7f2d9-116">構文</span><span class="sxs-lookup"><span data-stu-id="7f2d9-116">Syntax</span></span>

```
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]
```

## <a name="parameters"></a><span data-ttu-id="7f2d9-117">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7f2d9-117">Parameters</span></span>

|<span data-ttu-id="7f2d9-118">オプション</span><span class="sxs-lookup"><span data-stu-id="7f2d9-118">Option</span></span>|<span data-ttu-id="7f2d9-119">説明</span><span class="sxs-lookup"><span data-stu-id="7f2d9-119">Description</span></span>|
|------------|-----------------|
|`/dataservicecollection`|<span data-ttu-id="7f2d9-120">オブジェクトをコントロールにバインドするために必要なコードも生成することを指定します。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-120">Specifies that the code required to bind objects to controls is also generated.</span></span>|
|`/help`<br /><br /> <span data-ttu-id="7f2d9-121">または</span><span class="sxs-lookup"><span data-stu-id="7f2d9-121">-or-</span></span><br /><br /> `/?`|<span data-ttu-id="7f2d9-122">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-122">Displays command syntax and options for the tool.</span></span>|
|<span data-ttu-id="7f2d9-123">`/in:` *\<file>*</span><span class="sxs-lookup"><span data-stu-id="7f2d9-123">`/in:` *\<file>*</span></span>|<span data-ttu-id="7f2d9-124">.csdl ファイルまたは .edmx ファイル、またはファイルがあるディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-124">Specifies the .csdl or .edmx file or a directory where the file is located.</span></span>|
|<span data-ttu-id="7f2d9-125">`/language:`[VB&#124;CSharp]</span><span class="sxs-lookup"><span data-stu-id="7f2d9-125">`/language:`[VB&#124;CSharp]</span></span>|<span data-ttu-id="7f2d9-126">生成されるソース コード ファイルの言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-126">Specifies the language for the generated source code files.</span></span> <span data-ttu-id="7f2d9-127">既定の言語は C# です。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-127">The language defaults to C#.</span></span>|
|`/nologo`|<span data-ttu-id="7f2d9-128">著作権メッセージが表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-128">Suppresses the copyright message from displaying.</span></span>|
|<span data-ttu-id="7f2d9-129">`/out:` *\<file>*</span><span class="sxs-lookup"><span data-stu-id="7f2d9-129">`/out:` *\<file>*</span></span>|<span data-ttu-id="7f2d9-130">生成されたクライアント データ サービス クラスを含むソース コード ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-130">Specifies the name of the source code file that contains the generated client data service classes.</span></span>|
|<span data-ttu-id="7f2d9-131">`/uri:` *\<string>*</span><span class="sxs-lookup"><span data-stu-id="7f2d9-131">`/uri:` *\<string>*</span></span>|<span data-ttu-id="7f2d9-132">OData フィードの URI。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-132">The URI of the OData feed.</span></span>|
|<span data-ttu-id="7f2d9-133">`/version:`[1.0&#124;2.0]</span><span class="sxs-lookup"><span data-stu-id="7f2d9-133">`/version:`[1.0&#124;2.0]</span></span>|<span data-ttu-id="7f2d9-134">OData の許容される最上位のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-134">Specifies the highest accepted version of OData.</span></span> <span data-ttu-id="7f2d9-135">バージョンはに基づいて決定されます、`DataServiceVersion`返されたデータ サービス メタデータの DataService 要素の属性。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-135">The version is determined based on the `DataServiceVersion` attribute of the DataService element in the returned data service metadata.</span></span> <span data-ttu-id="7f2d9-136">詳細については、次を参照してください。[データ サービスのバージョン管理](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-136">For more information, see [Data Service Versioning](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).</span></span> <span data-ttu-id="7f2d9-137">指定した場合、`/dataservicecollection`パラメーターも指定`/version:2.0`データ バインディングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-137">When you specify the `/dataservicecollection` parameter, you must also specify `/version:2.0` to enable data binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="7f2d9-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f2d9-138">See also</span></span>

- [<span data-ttu-id="7f2d9-139">データ サービス クライアント ライブラリの生成</span><span class="sxs-lookup"><span data-stu-id="7f2d9-139">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)
- [<span data-ttu-id="7f2d9-140">方法: データ サービス参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="7f2d9-140">How to: Add a Data Service Reference</span></span>](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
