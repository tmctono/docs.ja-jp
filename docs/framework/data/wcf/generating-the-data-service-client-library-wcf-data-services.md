---
title: データ サービス クライアント ライブラリの生成 (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: b938e419a5a650fe0e24445c44a67aead13349fa
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348105"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a><span data-ttu-id="41c8e-102">データ サービス クライアント ライブラリの生成 (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="41c8e-102">Generating the Data Service Client Library (WCF Data Services)</span></span>
<span data-ttu-id="41c8e-103">Open Data Protocol (OData) を実装するデータサービスは、OData フィードによって公開されるデータモデルを記述したサービスメタデータドキュメントを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="41c8e-103">A data service that implements the Open Data Protocol (OData) can return a service metadata document that describes the data model exposed by the OData feed.</span></span> <span data-ttu-id="41c8e-104">詳細については、 [OData: 概要](https://www.odata.org/documentation/odata-version-2-0/overview/)に関する記事の「サービスメタデータドキュメント」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="41c8e-104">For more information, see the Service Metadata Document section in the [OData: Overview](https://www.odata.org/documentation/odata-version-2-0/overview/) article.</span></span> <span data-ttu-id="41c8e-105">Visual Studio の **[サービス参照の追加]** ダイアログボックスを使用して、OData ベースのサービスへの参照を追加できます。</span><span class="sxs-lookup"><span data-stu-id="41c8e-105">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to an OData-based service.</span></span> <span data-ttu-id="41c8e-106">このツールを使用して、クライアントプロジェクトの OData フィードによって返されるメタデータへの参照を追加すると、次のアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="41c8e-106">When you use this tool to add a reference to the metadata returned by an OData feed in a client project, it performs the following actions:</span></span>  
  
- <span data-ttu-id="41c8e-107">データ サービスからのサービス メタデータ ドキュメントが要求され、返されたメタデータが解釈されます。</span><span class="sxs-lookup"><span data-stu-id="41c8e-107">Requests the service metadata document from the data service and interprets the returned metadata.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="41c8e-108">返されたメタデータは、クライアント プロジェクトに .edmx ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="41c8e-108">The returned metadata is stored in the client project as an .edmx file.</span></span> <span data-ttu-id="41c8e-109">.edmx ファイルは、Entity Framework で使用される .edmx ファイルと形式が異なるので、Entity Data Model デザイナーを使用して開くことができません。</span><span class="sxs-lookup"><span data-stu-id="41c8e-109">This .edmx file cannot be opened by using the Entity Data Model designer because it does not have the same format an .edmx file used by the Entity Framework.</span></span> <span data-ttu-id="41c8e-110">このメタデータ ファイルは、XML エディターまたは任意のテキスト エディターを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="41c8e-110">You can view this metadata file by using the XML editor or any text editor.</span></span> <span data-ttu-id="41c8e-111">詳細については、「 [\[MC-EDMX\]: Entity Data Model Data Services パッケージング形式](https://docs.microsoft.com/openspecs/windows_protocols/mc-edmx/5dff5e25-56a1-408b-9d44-bff6634c7d16)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41c8e-111">For more information, see [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](https://docs.microsoft.com/openspecs/windows_protocols/mc-edmx/5dff5e25-56a1-408b-9d44-bff6634c7d16).</span></span>
  
- <span data-ttu-id="41c8e-112"><xref:System.Data.Services.Client.DataServiceContext> から継承するエンティティ コンテナー クラスとしてサービスの表現が生成されます。</span><span class="sxs-lookup"><span data-stu-id="41c8e-112">Generates a representation of the service as an entity container class that inherits from <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="41c8e-113">この生成されたエンティティ コンテナー クラスは、Entity Data Model ツールが生成するエンティティ コンテナーに似ています。</span><span class="sxs-lookup"><span data-stu-id="41c8e-113">This generated entity container class resembles the entity container that the Entity Data Model tools generate.</span></span> <span data-ttu-id="41c8e-114">詳細は、[Object Services の概要 (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="41c8e-114">For more information, see [Object Services Overview (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).</span></span>  
  
- <span data-ttu-id="41c8e-115">サービス メタデータ内で見つかったデータ モデル型のデータ クラスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="41c8e-115">Generates data classes for the data model types that it discovers in the service metadata.</span></span>  
  
- <span data-ttu-id="41c8e-116">`System.Data.Services.Client` アセンブリへの参照がプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="41c8e-116">Adds a reference to the `System.Data.Services.Client` assembly to the project.</span></span>  
  
 <span data-ttu-id="41c8e-117">詳細については、「[方法: データサービス参照を追加する](how-to-add-a-data-service-reference-wcf-data-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41c8e-117">For more information, see [How to: Add a Data Service Reference](how-to-add-a-data-service-reference-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="41c8e-118">クライアントデータサービスクラスは、コマンドプロンプトで[datasvcutil.exe](wcf-data-service-client-utility-datasvcutil-exe.md)ツールを使用して生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="41c8e-118">The client data service classes can also be generated by using the [DataSvcUtil.exe](wcf-data-service-client-utility-datasvcutil-exe.md) tool at the command prompt.</span></span> <span data-ttu-id="41c8e-119">詳細については、「[方法: クライアントデータサービスクラスを手動で生成する](how-to-manually-generate-client-data-service-classes-wcf-data-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41c8e-119">For more information, see [How to: Manually Generate Client Data Service Classes](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>  
  
## <a name="client-data-type-mapping"></a><span data-ttu-id="41c8e-120">クライアント データ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="41c8e-120">Client Data Type Mapping</span></span>  
 <span data-ttu-id="41c8e-121">Visual Studio の **[サービス参照の追加]** ダイアログまたは `DataSvcUtil.exe` ツールを使用して、OData フィードに基づくクライアントデータクラスを生成する場合、.NET Framework のデータ型は、次のようにデータモデルのプリミティブ型にマップされます。</span><span class="sxs-lookup"><span data-stu-id="41c8e-121">When you use the **Add Service Reference** dialog in Visual Studio or the `DataSvcUtil.exe` tool to generate client data classes that are based on an OData feed, the .NET Framework data types are mapped to the primitive types from the data model as follows:</span></span>  
  
|<span data-ttu-id="41c8e-122">データ モデル型</span><span class="sxs-lookup"><span data-stu-id="41c8e-122">Data model type</span></span>|<span data-ttu-id="41c8e-123">.NET Framework データ型</span><span class="sxs-lookup"><span data-stu-id="41c8e-123">.NET Framework data type</span></span>|  
|---------------------|------------------------------|  
|`Edm.Binary`|<span data-ttu-id="41c8e-124"><xref:System.Byte> `[]`</span><span class="sxs-lookup"><span data-stu-id="41c8e-124"><xref:System.Byte> `[]`</span></span>|  
|`Edm.Boolean`|<xref:System.Boolean>|  
|`Edm.Byte`|<xref:System.Byte>|  
|`Edm.DateTime`|<xref:System.DateTime>|  
|`Edm.Decimal`|<xref:System.Decimal>|  
|`Edm.Double`|<xref:System.Double>|  
|`Edm.Guid`|<xref:System.Guid>|  
|`Edm.Int16`|<xref:System.Int16>|  
|`Edm.Int32`|<xref:System.Int32>|  
|`Edm.Int64`|<xref:System.Int64>|  
|`Edm.SByte`|<xref:System.SByte>|  
|`Edm.Single`|<xref:System.Single>|  
|`Edm.String`|<xref:System.String>|  
  
 <span data-ttu-id="41c8e-125">詳細については、 [OData: 概要](https://www.odata.org/documentation/odata-version-2-0/overview/)に関する記事のプリミティブデータ型に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="41c8e-125">For more information, see the Primitive Data Types section in the [OData: Overview](https://www.odata.org/documentation/odata-version-2-0/overview/) article.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="41c8e-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="41c8e-126">See also</span></span>

- [<span data-ttu-id="41c8e-127">WCF Data Services クライアント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="41c8e-127">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)
- [<span data-ttu-id="41c8e-128">クイック スタート</span><span class="sxs-lookup"><span data-stu-id="41c8e-128">Quickstart</span></span>](quickstart-wcf-data-services.md)
