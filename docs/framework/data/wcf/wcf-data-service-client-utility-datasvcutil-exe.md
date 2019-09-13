---
title: WCF Data Service クライアント ユーティリティ (DataSvcUtil.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: 7632362339cf9e23599f4f688f98cbc1d0b32114
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894250"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a><span data-ttu-id="5fdb3-102">WCF Data Service クライアント ユーティリティ (DataSvcUtil.exe)</span><span class="sxs-lookup"><span data-stu-id="5fdb3-102">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>

<span data-ttu-id="5fdb3-103">Datasvcutil.exe は、 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]フィードを使用し、.NET Framework クライアントアプリケーションからデータサービスにアクセスするために必要なクライアントデータサービスクラスを生成する WCF Data Services によって提供されるコマンドラインツールです。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-103">DataSvcUtil.exe is a command-line tool provided by WCF Data Services that consumes an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed and generates the client data service classes that are needed to access a data service from a .NET Framework client application.</span></span> <span data-ttu-id="5fdb3-104">このユーティリティでは、以下のメタデータ ソースを使用してデータ クラスを生成できます。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-104">This utility can generate data classes by using the following metadata sources:</span></span>

- <span data-ttu-id="5fdb3-105">データ サービスのルート URI。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-105">The root URI of a data service.</span></span> <span data-ttu-id="5fdb3-106">ユーティリティは、データ サービスによって公開されるデータ モデルが記述されたサービス メタデータ ドキュメントを要求します。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-106">The utility requests the service metadata document, which describes the data model exposed by the data service.</span></span> <span data-ttu-id="5fdb3-107">詳細については[、「OData:サービスメタデータ](https://go.microsoft.com/fwlink/?LinkId=186070)ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-107">For more information, see [OData: Service Metadata Document](https://go.microsoft.com/fwlink/?LinkId=186070).</span></span>

- <span data-ttu-id="5fdb3-108">データモデルファイル (.csdl) は、次のように、 [ \[MC-csdl\]で定義されているように、概念スキーマ定義言語 (csdl) を使用して定義されます。概念スキーマ定義ファイル形式](https://go.microsoft.com/fwlink/?LinkID=159072)の仕様。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-108">A data model file (.csdl) defined by using the conceptual schema definition language (CSDL), as defined in the [\[MC-CSDL\]: Conceptual Schema Definition File Format](https://go.microsoft.com/fwlink/?LinkID=159072) specification.</span></span>

- <span data-ttu-id="5fdb3-109">Entity Framework に付属する Entity Data Model ツールを使用して作成された .edmx ファイル。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-109">An .edmx file created by using the Entity Data Model tools that are provided with the Entity Framework.</span></span> <span data-ttu-id="5fdb3-110">詳細については、 [「 \[MC-\]EDMX:Data Services パッケージング形式](https://go.microsoft.com/fwlink/?LinkID=178833)の指定に Entity Data Model します。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-110">For more information, see the [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](https://go.microsoft.com/fwlink/?LinkID=178833) specification.</span></span>

<span data-ttu-id="5fdb3-111">詳細については、「[方法 :クライアントデータサービスクラス](how-to-manually-generate-client-data-service-classes-wcf-data-services.md)を手動で生成します。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-111">For more information, see [How to: Manually Generate Client Data Service Classes](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>

<span data-ttu-id="5fdb3-112">Datasvcutil.exe ツールは、.NET Framework ディレクトリにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-112">The DataSvcUtil.exe tool is installed in the .NET Framework directory.</span></span> <span data-ttu-id="5fdb3-113">多くの場合、これは*c:\windows\ microsoft.net \framework\v4.0*にあります。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-113">In many cases, this is located in *C:\Windows\Microsoft.NET\Framework\v4.0*.</span></span> <span data-ttu-id="5fdb3-114">64ビットシステムの場合は、 *C:\Windows\Microsoft.NET\Framework64\v4.0*にあります。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-114">For 64-bit systems, this is located in *C:\Windows\Microsoft.NET\Framework64\v4.0*.</span></span> <span data-ttu-id="5fdb3-115">開発者コマンドプロンプトの Visual Studio では、Datasvcutil.exe ツールにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-115">You can also access the DataSvcUtil.exe tool from Developer Command Prompt for Visual Studio.</span></span>

## <a name="syntax"></a><span data-ttu-id="5fdb3-116">構文</span><span class="sxs-lookup"><span data-stu-id="5fdb3-116">Syntax</span></span>

```console
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]
```

## <a name="parameters"></a><span data-ttu-id="5fdb3-117">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5fdb3-117">Parameters</span></span>

|<span data-ttu-id="5fdb3-118">オプション</span><span class="sxs-lookup"><span data-stu-id="5fdb3-118">Option</span></span>|<span data-ttu-id="5fdb3-119">説明</span><span class="sxs-lookup"><span data-stu-id="5fdb3-119">Description</span></span>|
|------------|-----------------|
|`/dataservicecollection`|<span data-ttu-id="5fdb3-120">オブジェクトをコントロールにバインドするために必要なコードも生成することを指定します。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-120">Specifies that the code required to bind objects to controls is also generated.</span></span>|
|`/help`<br /><br /> <span data-ttu-id="5fdb3-121">または</span><span class="sxs-lookup"><span data-stu-id="5fdb3-121">-or-</span></span><br /><br /> `/?`|<span data-ttu-id="5fdb3-122">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-122">Displays command syntax and options for the tool.</span></span>|
|<span data-ttu-id="5fdb3-123">`/in:`*ファイル\<>*</span><span class="sxs-lookup"><span data-stu-id="5fdb3-123">`/in:` *\<file>*</span></span>|<span data-ttu-id="5fdb3-124">.csdl ファイルまたは .edmx ファイル、またはファイルがあるディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-124">Specifies the .csdl or .edmx file or a directory where the file is located.</span></span>|
|<span data-ttu-id="5fdb3-125">`/language:`[VB&#124;CSharp]</span><span class="sxs-lookup"><span data-stu-id="5fdb3-125">`/language:`[VB&#124;CSharp]</span></span>|<span data-ttu-id="5fdb3-126">生成されるソース コード ファイルの言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-126">Specifies the language for the generated source code files.</span></span> <span data-ttu-id="5fdb3-127">既定の言語は C# です。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-127">The language defaults to C#.</span></span>|
|`/nologo`|<span data-ttu-id="5fdb3-128">著作権メッセージが表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-128">Suppresses the copyright message from displaying.</span></span>|
|<span data-ttu-id="5fdb3-129">`/out:`*ファイル\<>*</span><span class="sxs-lookup"><span data-stu-id="5fdb3-129">`/out:` *\<file>*</span></span>|<span data-ttu-id="5fdb3-130">生成されたクライアント データ サービス クラスを含むソース コード ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-130">Specifies the name of the source code file that contains the generated client data service classes.</span></span>|
|<span data-ttu-id="5fdb3-131">`/uri:`*文字列\<>*</span><span class="sxs-lookup"><span data-stu-id="5fdb3-131">`/uri:` *\<string>*</span></span>|<span data-ttu-id="5fdb3-132">OData フィードの URI。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-132">The URI of the OData feed.</span></span>|
|<span data-ttu-id="5fdb3-133">`/version:`[1.0&#124;2.0]</span><span class="sxs-lookup"><span data-stu-id="5fdb3-133">`/version:`[1.0&#124;2.0]</span></span>|<span data-ttu-id="5fdb3-134">OData の許容される最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-134">Specifies the highest accepted version of OData.</span></span> <span data-ttu-id="5fdb3-135">バージョンは、返されるデータサービス`DataServiceVersion`メタデータ内の DataService 要素の属性に基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-135">The version is determined based on the `DataServiceVersion` attribute of the DataService element in the returned data service metadata.</span></span> <span data-ttu-id="5fdb3-136">詳細については、「[データサービスのバージョン管理](data-service-versioning-wcf-data-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-136">For more information, see [Data Service Versioning](data-service-versioning-wcf-data-services.md).</span></span> <span data-ttu-id="5fdb3-137">パラメーターを指定する`/dataservicecollection`場合は、も指定し`/version:2.0`てデータバインディングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-137">When you specify the `/dataservicecollection` parameter, you must also specify `/version:2.0` to enable data binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="5fdb3-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="5fdb3-138">See also</span></span>

- [<span data-ttu-id="5fdb3-139">データ サービス クライアント ライブラリの生成</span><span class="sxs-lookup"><span data-stu-id="5fdb3-139">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)
- [<span data-ttu-id="5fdb3-140">方法: データサービス参照の追加</span><span class="sxs-lookup"><span data-stu-id="5fdb3-140">How to: Add a Data Service Reference</span></span>](how-to-add-a-data-service-reference-wcf-data-services.md)
