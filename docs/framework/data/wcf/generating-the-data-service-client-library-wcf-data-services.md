---
title: データ サービス クライアント ライブラリの生成 (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: d53f2d209d6fb0a6f3cadb96245338060ece87db
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780291"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a><span data-ttu-id="885fb-102">データ サービス クライアント ライブラリの生成 (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="885fb-102">Generating the Data Service Client Library (WCF Data Services)</span></span>
<span data-ttu-id="885fb-103">を実装[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]するデータサービスは、 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]フィードによって公開されるデータモデルを記述したサービスメタデータドキュメントを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="885fb-103">A data service that implements the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] can return a service metadata document that describes the data model exposed by the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed.</span></span> <span data-ttu-id="885fb-104">詳細については[、「OData:サービスメタデータ](https://go.microsoft.com/fwlink/?LinkId=186070)ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="885fb-104">For more information, see [OData: Service Metadata Document](https://go.microsoft.com/fwlink/?LinkId=186070).</span></span> <span data-ttu-id="885fb-105">Visual Studio の **[サービス参照の追加]** ダイアログボックスを使用して、ベースの[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]サービスへの参照を追加できます。</span><span class="sxs-lookup"><span data-stu-id="885fb-105">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-based service.</span></span> <span data-ttu-id="885fb-106">このツールを使用して、クライアントプロジェクトの[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]フィードによって返されるメタデータへの参照を追加すると、次のアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="885fb-106">When you use this tool to add a reference to the metadata returned by an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in a client project, it performs the following actions:</span></span>  
  
- <span data-ttu-id="885fb-107">データ サービスからのサービス メタデータ ドキュメントが要求され、返されたメタデータが解釈されます。</span><span class="sxs-lookup"><span data-stu-id="885fb-107">Requests the service metadata document from the data service and interprets the returned metadata.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="885fb-108">返されたメタデータは、クライアント プロジェクトに .edmx ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="885fb-108">The returned metadata is stored in the client project as an .edmx file.</span></span> <span data-ttu-id="885fb-109">.edmx ファイルは、Entity Framework で使用される .edmx ファイルと形式が異なるので、Entity Data Model デザイナーを使用して開くことができません。</span><span class="sxs-lookup"><span data-stu-id="885fb-109">This .edmx file cannot be opened by using the Entity Data Model designer because it does not have the same format an .edmx file used by the Entity Framework.</span></span> <span data-ttu-id="885fb-110">このメタデータ ファイルは、XML エディターまたは任意のテキスト エディターを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="885fb-110">You can view this metadata file by using the XML editor or any text editor.</span></span> <span data-ttu-id="885fb-111">詳細については、 [「 \[MC-\]EDMX:Data Services パッケージング形式](https://go.microsoft.com/fwlink/?LinkID=178833)の仕様の Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="885fb-111">For more information, see the [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](https://go.microsoft.com/fwlink/?LinkID=178833) specification</span></span>  
  
- <span data-ttu-id="885fb-112"><xref:System.Data.Services.Client.DataServiceContext> から継承するエンティティ コンテナー クラスとしてサービスの表現が生成されます。</span><span class="sxs-lookup"><span data-stu-id="885fb-112">Generates a representation of the service as an entity container class that inherits from <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="885fb-113">この生成されたエンティティ コンテナー クラスは、Entity Data Model ツールが生成するエンティティ コンテナーに似ています。</span><span class="sxs-lookup"><span data-stu-id="885fb-113">This generated entity container class resembles the entity container that the Entity Data Model tools generate.</span></span> <span data-ttu-id="885fb-114">詳細は、[Object Services の概要 (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="885fb-114">For more information, see [Object Services Overview (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).</span></span>  
  
- <span data-ttu-id="885fb-115">サービス メタデータ内で見つかったデータ モデル型のデータ クラスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="885fb-115">Generates data classes for the data model types that it discovers in the service metadata.</span></span>  
  
- <span data-ttu-id="885fb-116">`System.Data.Services.Client` アセンブリへの参照がプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="885fb-116">Adds a reference to the `System.Data.Services.Client` assembly to the project.</span></span>  
  
 <span data-ttu-id="885fb-117">詳細については、「[方法 :データサービス参照](how-to-add-a-data-service-reference-wcf-data-services.md)を追加します。</span><span class="sxs-lookup"><span data-stu-id="885fb-117">For more information, see [How to: Add a Data Service Reference](how-to-add-a-data-service-reference-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="885fb-118">クライアントデータサービスクラスは、コマンドプロンプトで[datasvcutil.exe](wcf-data-service-client-utility-datasvcutil-exe.md)ツールを使用して生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="885fb-118">The client data service classes can also be generated by using the [DataSvcUtil.exe](wcf-data-service-client-utility-datasvcutil-exe.md) tool at the command prompt.</span></span> <span data-ttu-id="885fb-119">詳細については、「[方法 :クライアントデータサービスクラス](how-to-manually-generate-client-data-service-classes-wcf-data-services.md)を手動で生成します。</span><span class="sxs-lookup"><span data-stu-id="885fb-119">For more information, see [How to: Manually Generate Client Data Service Classes](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>  
  
## <a name="client-data-type-mapping"></a><span data-ttu-id="885fb-120">クライアント データ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="885fb-120">Client Data Type Mapping</span></span>  
 <span data-ttu-id="885fb-121">Visual Studio の **[サービス参照の追加]** ダイアログボックスまたは`DataSvcUtil.exe`ツールを使用して、 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]フィードに基づくクライアントデータクラスを生成する場合、次のように、.NET Framework データ型がデータモデルのプリミティブ型にマップされます。</span><span class="sxs-lookup"><span data-stu-id="885fb-121">When you use the **Add Service Reference** dialog in Visual Studio or the `DataSvcUtil.exe` tool to generate client data classes that are based on an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, the .NET Framework data types are mapped to the primitive types from the data model as follows:</span></span>  
  
|<span data-ttu-id="885fb-122">データ モデル型</span><span class="sxs-lookup"><span data-stu-id="885fb-122">Data model type</span></span>|<span data-ttu-id="885fb-123">.NET Framework データ型</span><span class="sxs-lookup"><span data-stu-id="885fb-123">.NET Framework data type</span></span>|  
|---------------------|------------------------------|  
|`Edm.Binary`|<span data-ttu-id="885fb-124"><xref:System.Byte> `[]`</span><span class="sxs-lookup"><span data-stu-id="885fb-124"><xref:System.Byte> `[]`</span></span>|  
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
  
 <span data-ttu-id="885fb-125">詳細については[、「OData:プリミティブデータ型](https://go.microsoft.com/fwlink/?LinkId=186072)。</span><span class="sxs-lookup"><span data-stu-id="885fb-125">For more information, see [OData: Primitive Data Types](https://go.microsoft.com/fwlink/?LinkId=186072).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="885fb-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="885fb-126">See also</span></span>

- [<span data-ttu-id="885fb-127">WCF Data Services クライアント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="885fb-127">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)
- [<span data-ttu-id="885fb-128">クイック スタート</span><span class="sxs-lookup"><span data-stu-id="885fb-128">Quickstart</span></span>](quickstart-wcf-data-services.md)
