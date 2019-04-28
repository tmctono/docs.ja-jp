---
title: データ サービス クライアント ライブラリの生成 (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: 96b7bfabef589464e99e808d19f0dee6cfb23536
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765662"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a><span data-ttu-id="867ca-102">データ サービス クライアント ライブラリの生成 (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="867ca-102">Generating the Data Service Client Library (WCF Data Services)</span></span>
<span data-ttu-id="867ca-103">実装するデータ サービス、[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]によって公開されているデータ モデルを説明するサービス メタデータ ドキュメントを返すことができます、[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]フィードします。</span><span class="sxs-lookup"><span data-stu-id="867ca-103">A data service that implements the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] can return a service metadata document that describes the data model exposed by the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed.</span></span> <span data-ttu-id="867ca-104">詳細については、次を参照してください[OData:。サービス メタデータ ドキュメント](https://go.microsoft.com/fwlink/?LinkId=186070)します。</span><span class="sxs-lookup"><span data-stu-id="867ca-104">For more information, see [OData: Service Metadata Document](https://go.microsoft.com/fwlink/?LinkId=186070).</span></span> <span data-ttu-id="867ca-105">使用することができます、**サービス参照の追加**への参照を追加する Visual Studio でのダイアログ、 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-ベースのサービスです。</span><span class="sxs-lookup"><span data-stu-id="867ca-105">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-based service.</span></span> <span data-ttu-id="867ca-106">によって返されるメタデータへの参照を追加するこのツールを使用する場合、[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]クライアント プロジェクトでのフィードを次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="867ca-106">When you use this tool to add a reference to the metadata returned by an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in a client project, it performs the following actions:</span></span>  
  
- <span data-ttu-id="867ca-107">データ サービスからのサービス メタデータ ドキュメントが要求され、返されたメタデータが解釈されます。</span><span class="sxs-lookup"><span data-stu-id="867ca-107">Requests the service metadata document from the data service and interprets the returned metadata.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="867ca-108">返されたメタデータは、クライアント プロジェクトに .edmx ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="867ca-108">The returned metadata is stored in the client project as an .edmx file.</span></span> <span data-ttu-id="867ca-109">.edmx ファイルは、Entity Framework で使用される .edmx ファイルと形式が異なるので、Entity Data Model デザイナーを使用して開くことができません。</span><span class="sxs-lookup"><span data-stu-id="867ca-109">This .edmx file cannot be opened by using the Entity Data Model designer because it does not have the same format an .edmx file used by the Entity Framework.</span></span> <span data-ttu-id="867ca-110">このメタデータ ファイルは、XML エディターまたは任意のテキスト エディターを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="867ca-110">You can view this metadata file by using the XML editor or any text editor.</span></span> <span data-ttu-id="867ca-111">詳細については、次を参照してください、 [ \[MC-EDMX\]:。データ サービス パッケージング形式のエンティティ データ モデル](https://go.microsoft.com/fwlink/?LinkID=178833)仕様</span><span class="sxs-lookup"><span data-stu-id="867ca-111">For more information, see the [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](https://go.microsoft.com/fwlink/?LinkID=178833) specification</span></span>  
  
- <span data-ttu-id="867ca-112"><xref:System.Data.Services.Client.DataServiceContext> から継承するエンティティ コンテナー クラスとしてサービスの表現が生成されます。</span><span class="sxs-lookup"><span data-stu-id="867ca-112">Generates a representation of the service as an entity container class that inherits from <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="867ca-113">この生成されたエンティティ コンテナー クラスは、Entity Data Model ツールが生成するエンティティ コンテナーに似ています。</span><span class="sxs-lookup"><span data-stu-id="867ca-113">This generated entity container class resembles the entity container that the Entity Data Model tools generate.</span></span> <span data-ttu-id="867ca-114">詳細は、[Object Services の概要 (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="867ca-114">For more information, see [Object Services Overview (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).</span></span>  
  
- <span data-ttu-id="867ca-115">サービス メタデータ内で見つかったデータ モデル型のデータ クラスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="867ca-115">Generates data classes for the data model types that it discovers in the service metadata.</span></span>  
  
- <span data-ttu-id="867ca-116">`System.Data.Services.Client` アセンブリへの参照がプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="867ca-116">Adds a reference to the `System.Data.Services.Client` assembly to the project.</span></span>  
  
 <span data-ttu-id="867ca-117">詳細については、「[方法 :データ サービス参照を追加](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="867ca-117">For more information, see [How to: Add a Data Service Reference](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="867ca-118">使用して、クライアント データ サービス クラスを生成することことも、 [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)コマンド プロンプト ツールです。</span><span class="sxs-lookup"><span data-stu-id="867ca-118">The client data service classes can also be generated by using the [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) tool at the command prompt.</span></span> <span data-ttu-id="867ca-119">詳細については、「[方法 :クライアント データ サービス クラスを手動で生成](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="867ca-119">For more information, see [How to: Manually Generate Client Data Service Classes](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>  
  
## <a name="client-data-type-mapping"></a><span data-ttu-id="867ca-120">クライアント データ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="867ca-120">Client Data Type Mapping</span></span>  
 <span data-ttu-id="867ca-121">使用すると、**サービス参照の追加**Visual Studio でダイアログまたは`DataSvcUtil.exe`に基づくクライアント データ クラスを生成するためのツール、 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] .NET Framework のデータ型は、フィードからプリミティブ型にマップされます、データは、次のようにモデルします。</span><span class="sxs-lookup"><span data-stu-id="867ca-121">When you use the **Add Service Reference** dialog in Visual Studio or the `DataSvcUtil.exe` tool to generate client data classes that are based on an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, the .NET Framework data types are mapped to the primitive types from the data model as follows:</span></span>  
  
|<span data-ttu-id="867ca-122">データ モデル型</span><span class="sxs-lookup"><span data-stu-id="867ca-122">Data model type</span></span>|<span data-ttu-id="867ca-123">.NET Framework データ型</span><span class="sxs-lookup"><span data-stu-id="867ca-123">.NET Framework data type</span></span>|  
|---------------------|------------------------------|  
|`Edm.Binary`|<span data-ttu-id="867ca-124"><xref:System.Byte> `[]`</span><span class="sxs-lookup"><span data-stu-id="867ca-124"><xref:System.Byte> `[]`</span></span>|  
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
  
 <span data-ttu-id="867ca-125">詳細については、次を参照してください[OData:。プリミティブ データ型](https://go.microsoft.com/fwlink/?LinkId=186072)します。</span><span class="sxs-lookup"><span data-stu-id="867ca-125">For more information, see [OData: Primitive Data Types](https://go.microsoft.com/fwlink/?LinkId=186072).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="867ca-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="867ca-126">See also</span></span>

- [<span data-ttu-id="867ca-127">WCF Data Services クライアント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="867ca-127">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [<span data-ttu-id="867ca-128">クイック スタート</span><span class="sxs-lookup"><span data-stu-id="867ca-128">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
