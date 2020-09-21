---
title: WCF Data Service クライアント ユーティリティ (DataSvcUtil.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: 600cb9a4f91ff2051f60ee86d4cb80cc5b404c61
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544298"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a><span data-ttu-id="401eb-102">WCF Data Service クライアント ユーティリティ (DataSvcUtil.exe)</span><span class="sxs-lookup"><span data-stu-id="401eb-102">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>

<span data-ttu-id="401eb-103">DataSvcUtil.exe は、WCF Data Services に付属するコマンドライン ツールです。このツールでは、Open Data Protocol (OData) フィードを使用して、.NET Framework クライアント アプリケーションのデータ サービスにアクセスするために必要なクライアント データ サービス クラスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="401eb-103">DataSvcUtil.exe is a command-line tool provided by WCF Data Services that consumes an Open Data Protocol (OData) feed and generates the client data service classes that are needed to access a data service from a .NET Framework client application.</span></span> <span data-ttu-id="401eb-104">このユーティリティでは、以下のメタデータ ソースを使用してデータ クラスを生成できます。</span><span class="sxs-lookup"><span data-stu-id="401eb-104">This utility can generate data classes by using the following metadata sources:</span></span>

- <span data-ttu-id="401eb-105">データ サービスのルート URI。</span><span class="sxs-lookup"><span data-stu-id="401eb-105">The root URI of a data service.</span></span> <span data-ttu-id="401eb-106">ユーティリティは、データ サービスによって公開されるデータ モデルが記述されたサービス メタデータ ドキュメントを要求します。</span><span class="sxs-lookup"><span data-stu-id="401eb-106">The utility requests the service metadata document, which describes the data model exposed by the data service.</span></span> <span data-ttu-id="401eb-107">詳細については、[AtomPub (RFC5023)](https://tools.ietf.org/html/rfc5023#section-8) に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="401eb-107">For more information, see [AtomPub (RFC5023)](https://tools.ietf.org/html/rfc5023#section-8).</span></span>

- <span data-ttu-id="401eb-108">概念スキーマ定義言語 (CSDL) を使用して定義されるデータ モデル ファイル (.csdl)。「[\[MC-CSDL\]: 概念スキーマ定義ファイル形式](/openspecs/windows_protocols/mc-csdl/c03ad8c3-e8b7-4306-af96-a9e52bb3df12)」の仕様で定義されています。</span><span class="sxs-lookup"><span data-stu-id="401eb-108">A data model file (.csdl) defined by using the conceptual schema definition language (CSDL), as defined in the [\[MC-CSDL\]: Conceptual Schema Definition File Format](/openspecs/windows_protocols/mc-csdl/c03ad8c3-e8b7-4306-af96-a9e52bb3df12) specification.</span></span>

- <span data-ttu-id="401eb-109">Entity Framework に付属する Entity Data Model ツールを使用して作成された .edmx ファイル。</span><span class="sxs-lookup"><span data-stu-id="401eb-109">An .edmx file created by using the Entity Data Model tools that are provided with the Entity Framework.</span></span> <span data-ttu-id="401eb-110">詳細については、「[\[MC-EDMX\]: データ サービス パッケージング形式の Entity Data Model](/openspecs/windows_protocols/mc-edmx/5dff5e25-56a1-408b-9d44-bff6634c7d16)」の仕様を参照してください。</span><span class="sxs-lookup"><span data-stu-id="401eb-110">For more information, see the [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](/openspecs/windows_protocols/mc-edmx/5dff5e25-56a1-408b-9d44-bff6634c7d16) specification.</span></span>

<span data-ttu-id="401eb-111">詳細については、[クライアント データ サービス クラスを手動で生成する](how-to-manually-generate-client-data-service-classes-wcf-data-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="401eb-111">For more information, see [How to: Manually Generate Client Data Service Classes](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>

<span data-ttu-id="401eb-112">DataSvcUtil.exe ツールは、.NET Framework のディレクトリにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="401eb-112">The DataSvcUtil.exe tool is installed in the .NET Framework directory.</span></span> <span data-ttu-id="401eb-113">多くの場合、この場所は *C:\Windows\Microsoft.NET\Framework\v4.0* です。</span><span class="sxs-lookup"><span data-stu-id="401eb-113">In many cases, this is located in *C:\Windows\Microsoft.NET\Framework\v4.0*.</span></span> <span data-ttu-id="401eb-114">64 ビット システムの場合は、*C:\Windows\Microsoft.NET\Framework64\v4.0* です。</span><span class="sxs-lookup"><span data-stu-id="401eb-114">For 64-bit systems, this is located in *C:\Windows\Microsoft.NET\Framework64\v4.0*.</span></span> <span data-ttu-id="401eb-115">DataSvcUtil.exe ツールには、Visual Studio の開発者コマンド プロンプトからアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="401eb-115">You can also access the DataSvcUtil.exe tool from Developer Command Prompt for Visual Studio.</span></span>

## <a name="syntax"></a><span data-ttu-id="401eb-116">構文</span><span class="sxs-lookup"><span data-stu-id="401eb-116">Syntax</span></span>

```console
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]
```

## <a name="parameters"></a><span data-ttu-id="401eb-117">パラメーター</span><span class="sxs-lookup"><span data-stu-id="401eb-117">Parameters</span></span>

|<span data-ttu-id="401eb-118">オプション</span><span class="sxs-lookup"><span data-stu-id="401eb-118">Option</span></span>|<span data-ttu-id="401eb-119">説明</span><span class="sxs-lookup"><span data-stu-id="401eb-119">Description</span></span>|
|------------|-----------------|
|`/dataservicecollection`|<span data-ttu-id="401eb-120">オブジェクトをコントロールにバインドするために必要なコードも生成することを指定します。</span><span class="sxs-lookup"><span data-stu-id="401eb-120">Specifies that the code required to bind objects to controls is also generated.</span></span>|
|`/help`<br /><br /> <span data-ttu-id="401eb-121">\- または -</span><span class="sxs-lookup"><span data-stu-id="401eb-121">-or-</span></span><br /><br /> `/?`|<span data-ttu-id="401eb-122">このツールのコマンド構文とオプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="401eb-122">Displays command syntax and options for the tool.</span></span>|
|<span data-ttu-id="401eb-123">`/in:` *\<file>*</span><span class="sxs-lookup"><span data-stu-id="401eb-123">`/in:` *\<file>*</span></span>|<span data-ttu-id="401eb-124">.csdl ファイルまたは .edmx ファイル、またはファイルがあるディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="401eb-124">Specifies the .csdl or .edmx file or a directory where the file is located.</span></span>|
|<span data-ttu-id="401eb-125">`/language:`[VB&#124;CSharp]</span><span class="sxs-lookup"><span data-stu-id="401eb-125">`/language:`[VB&#124;CSharp]</span></span>|<span data-ttu-id="401eb-126">生成されるソース コード ファイルの言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="401eb-126">Specifies the language for the generated source code files.</span></span> <span data-ttu-id="401eb-127">既定の言語は C# です。</span><span class="sxs-lookup"><span data-stu-id="401eb-127">The language defaults to C#.</span></span>|
|`/nologo`|<span data-ttu-id="401eb-128">著作権メッセージが表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="401eb-128">Suppresses the copyright message from displaying.</span></span>|
|<span data-ttu-id="401eb-129">`/out:` *\<file>*</span><span class="sxs-lookup"><span data-stu-id="401eb-129">`/out:` *\<file>*</span></span>|<span data-ttu-id="401eb-130">生成されたクライアント データ サービス クラスを含むソース コード ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="401eb-130">Specifies the name of the source code file that contains the generated client data service classes.</span></span>|
|<span data-ttu-id="401eb-131">`/uri:` *\<string>*</span><span class="sxs-lookup"><span data-stu-id="401eb-131">`/uri:` *\<string>*</span></span>|<span data-ttu-id="401eb-132">OData フィードの URI。</span><span class="sxs-lookup"><span data-stu-id="401eb-132">The URI of the OData feed.</span></span>|
|<span data-ttu-id="401eb-133">`/version:`[1.0&#124;2.0]</span><span class="sxs-lookup"><span data-stu-id="401eb-133">`/version:`[1.0&#124;2.0]</span></span>|<span data-ttu-id="401eb-134">許容される OData の最新バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="401eb-134">Specifies the highest accepted version of OData.</span></span> <span data-ttu-id="401eb-135">バージョンは、返されるデータ サービス メタデータに含まれる DataService 要素の `DataServiceVersion` 属性に基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="401eb-135">The version is determined based on the `DataServiceVersion` attribute of the DataService element in the returned data service metadata.</span></span> <span data-ttu-id="401eb-136">詳細については、「[データ サービスのバージョン管理](data-service-versioning-wcf-data-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="401eb-136">For more information, see [Data Service Versioning](data-service-versioning-wcf-data-services.md).</span></span> <span data-ttu-id="401eb-137">`/dataservicecollection` パラメーターを指定する場合は、`/version:2.0` も指定してデータ バインディングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="401eb-137">When you specify the `/dataservicecollection` parameter, you must also specify `/version:2.0` to enable data binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="401eb-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="401eb-138">See also</span></span>

- [<span data-ttu-id="401eb-139">データ サービス クライアント ライブラリの生成</span><span class="sxs-lookup"><span data-stu-id="401eb-139">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)
- [<span data-ttu-id="401eb-140">方法: データ サービス参照を追加する</span><span class="sxs-lookup"><span data-stu-id="401eb-140">How to: Add a Data Service Reference</span></span>](how-to-add-a-data-service-reference-wcf-data-services.md)
