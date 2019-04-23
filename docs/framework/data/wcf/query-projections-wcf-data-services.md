---
title: クエリ射影 (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- projection [WCF Data Services]
- WCF Data Services, projection
- query projection [WCF Data Services]
- WCF Data Services, querying
ms.assetid: a09f4985-9f0d-48c8-b183-83d67a3dfe5f
ms.openlocfilehash: 2e4c40d6c71a254d5f40ea42788608e10c5872a7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59517175"
---
# <a name="query-projections-wcf-data-services"></a><span data-ttu-id="ba8a2-102">クエリ射影 (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="ba8a2-102">Query Projections (WCF Data Services)</span></span>

<span data-ttu-id="ba8a2-103">プロジェクションのメカニズムを提供する、[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]応答で返されるエンティティの特定のプロパティのみ指定することで、クエリによって返されるフィード内のデータの量を削減します。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-103">Projection provides a mechanism in the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] to reduce the amount of data in the feed returned by a query by specifying that only certain properties of an entity are returned in the response.</span></span> <span data-ttu-id="ba8a2-104">詳細については、次を参照してください[OData:。選択システム クエリ オプション ($select)](https://go.microsoft.com/fwlink/?LinkId=186076)します。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-104">For more information, see [OData: Select System Query Option ($select)](https://go.microsoft.com/fwlink/?LinkId=186076).</span></span>

<span data-ttu-id="ba8a2-105">このトピックでは、クエリ射影を定義する方法、エンティティ型、エンティティ型以外の要件、射影された結果に対する更新、射影された型の作成について説明すると共に、射影に関する注意事項をリストします。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-105">This topic describes how to define a query projection, what the requirements are for entity and non-entity types, making updates to projected results, creating projected types, and lists some projection considerations.</span></span>

## <a name="defining-a-query-projection"></a><span data-ttu-id="ba8a2-106">クエリ射影の定義</span><span class="sxs-lookup"><span data-stu-id="ba8a2-106">Defining a Query Projection</span></span>

<span data-ttu-id="ba8a2-107">句を追加できます、プロジェクション クエリを使用するか、`$select`クエリ オプションを URI でまたはを使用して、[選択](~/docs/csharp/language-reference/keywords/select-clause.md)句 ([選択](~/docs/visual-basic/language-reference/queries/select-clause.md)Visual Basic で)、LINQ クエリで。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-107">You can add a projection clause to a query either by using the `$select` query option in a URI or by using the [select](~/docs/csharp/language-reference/keywords/select-clause.md) clause ([Select](~/docs/visual-basic/language-reference/queries/select-clause.md) in Visual Basic) in a LINQ query.</span></span> <span data-ttu-id="ba8a2-108">返されたエンティティ データは、クライアント上のエンティティ型またはエンティティ型以外に射影できます。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-108">Returned entity data can be projected into either entity types or non-entity types on the client.</span></span> <span data-ttu-id="ba8a2-109">このトピックでは、LINQ クエリで `select` 句を使用する例を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-109">Examples in this topic demonstrate how to use the `select` clause in a LINQ query.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba8a2-110">射影された型に対して行った更新を保存すると、データ サービスでデータの損失が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-110">Data loss might occur in the data service when you save updates that were made to projected types.</span></span> <span data-ttu-id="ba8a2-111">詳細については、次を参照してください。[投影に関する考慮事項](#considerations)します。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-111">For more information, see [Projection Considerations](#considerations).</span></span>

## <a name="requirements-for-entity-and-non-entity-types"></a><span data-ttu-id="ba8a2-112">エンティティ型およびエンティティ型以外の要件</span><span class="sxs-lookup"><span data-stu-id="ba8a2-112">Requirements for Entity and Non-Entity Types</span></span>

<span data-ttu-id="ba8a2-113">エンティティ型には、エンティティ キーを構成する 1 つ以上の Identity プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-113">Entity types must have one or more identity properties that make up the entity key.</span></span> <span data-ttu-id="ba8a2-114">エンティティ型は、次のいずれかの方法によりクライアントで定義されます。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-114">Entity types are defined on clients in one of the following ways:</span></span>

- <span data-ttu-id="ba8a2-115"><xref:System.Data.Services.Common.DataServiceKeyAttribute> または <xref:System.Data.Services.Common.DataServiceEntityAttribute> を型に適用する。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-115">By applying the <xref:System.Data.Services.Common.DataServiceKeyAttribute> or <xref:System.Data.Services.Common.DataServiceEntityAttribute> to the type.</span></span>

- <span data-ttu-id="ba8a2-116">型に `ID` という名前のプロパティがある場合。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-116">When the type has a property named `ID`.</span></span>

- <span data-ttu-id="ba8a2-117">型がという名前のプロパティを持っている場合*型*`ID`ここで、*型*型の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-117">When the type has a property named *type*`ID`, where *type* is the name of the type.</span></span>

<span data-ttu-id="ba8a2-118">既定では、クライアントで定義された型にクエリ結果を射影した場合、射影で要求されたプロパティがクライアント型に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-118">By default, when you project query results into a type defined at the client, the properties requested in the projection must exist in the client type.</span></span> <span data-ttu-id="ba8a2-119">ただし、`true` の <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> プロパテに <xref:System.Data.Services.Client.DataServiceContext> という値を指定した場合、射影で指定されたプロパティがクライアント型に含まれる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-119">However, when you specify a value of `true` for the <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> property of the <xref:System.Data.Services.Client.DataServiceContext>, properties specified in the projection are not required to occur in the client type.</span></span>

### <a name="making-updates-to-projected-results"></a><span data-ttu-id="ba8a2-120">射影された結果に対する更新</span><span class="sxs-lookup"><span data-stu-id="ba8a2-120">Making Updates to Projected Results</span></span>

<span data-ttu-id="ba8a2-121">クエリ結果をクライアント上のエンティティ型に射影する場合、<xref:System.Data.Services.Client.DataServiceContext> はそれらのオブジェクトを追跡し、<xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> メソッドが呼び出されるとデータ サービスに更新内容が送り返されます。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-121">When you project query results into entity types on the client, the <xref:System.Data.Services.Client.DataServiceContext> can track those objects with updates to be sent back to the data service when the <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> method is called.</span></span> <span data-ttu-id="ba8a2-122">ただし、クライアント上のエンティティ型以外に射影されたデータの更新内容は、データ サービスに送り返すことはできません。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-122">However, updates that are made to data projected into non-entity types on the client cannot be sent back to the data service.</span></span> <span data-ttu-id="ba8a2-123">これは、エンティティ インスタンスを識別するキーがなければ、データ サービスはデータ ソース内の正しいエンティティを更新できないためです。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-123">This is because without a key to identify the entity instance, the data service cannot update the correct entity in the data source.</span></span> <span data-ttu-id="ba8a2-124">エンティティ型以外は <xref:System.Data.Services.Client.DataServiceContext> にはアタッチされません。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-124">Non-entity types are not attached to the <xref:System.Data.Services.Client.DataServiceContext>.</span></span>

<span data-ttu-id="ba8a2-125">データ サービスで定義されたエンティティ型の 1 つ以上のプロパティが、エンティティの射影先のクライアント型に含まれない場合、新しいエンティティの挿入には、これらの欠損しているプロパティは含まれません。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-125">When one or more properties of an entity type defined in the data service do not occur in the client type into which the entity is projected, inserts of new entities will not contain these missing properties.</span></span> <span data-ttu-id="ba8a2-126">この場合、既存のエンティティに加えられた更新プログラムは**も**不足しているこれらのプロパティは含まれません。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-126">In this case, updates that are made to existing entities will **also** not include these missing properties.</span></span> <span data-ttu-id="ba8a2-127">そのようなプロパティに対する値が存在する場合、データ ソースの定義に従い、更新ではその値がそのプロパティの既定値としてリセットされます。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-127">When a value exists for such a property, the update resets it to the default value for the property, as defined in the data source.</span></span>

### <a name="creating-projected-types"></a><span data-ttu-id="ba8a2-128">射影型の作成</span><span class="sxs-lookup"><span data-stu-id="ba8a2-128">Creating Projected Types</span></span>

<span data-ttu-id="ba8a2-129">次の例では、`Customers` 型のアドレス関連のプロパティを、クライアントで定義されエンティティ型として属性化された新しい `CustomerAddress` 型に射影する匿名の LINQ クエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-129">The following example uses an anonymous LINQ query that projects the address-related properties of the `Customers` type into a new `CustomerAddress` type, which is defined on the client and is attributed as an entity type:</span></span>

[!code-csharp[Astoria Northwind Client#SelectCustomerAddressSpecific](~/samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#selectcustomeraddressspecific)]
[!code-vb[Astoria Northwind Client#SelectCustomerAddressSpecific](~/samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#selectcustomeraddressspecific)]

<span data-ttu-id="ba8a2-130">この例では、コンストラクターを呼び出す代わりに、オブジェクト初期化子パターンを使用して `CustomerAddress` 型の新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-130">In this example, the object initializer pattern is used to create a new instance of the `CustomerAddress` type instead of calling a constructor.</span></span> <span data-ttu-id="ba8a2-131">コンストラクターは、エンティティ型への射影ではサポートされていませんが、エンティティ型以外および匿名型への射影では使用できます。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-131">Constructors are not supported when projecting into entity types, but they can be used when projecting into non-entity and anonymous types.</span></span> <span data-ttu-id="ba8a2-132">`CustomerAddress` は、エンティティ型であるため、変更を加えてデータ サービスに送り返すことができます。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-132">Because `CustomerAddress` is an entity type, changes can be made and sent back to the data service.</span></span>

<span data-ttu-id="ba8a2-133">さらに、`Customer` 型からのデータは、匿名型ではなく `CustomerAddress` エンティティ型のインスタンスに射影されます。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-133">Also, the data from the `Customer` type is projected into an instance of the `CustomerAddress` entity type instead of an anonymous type.</span></span> <span data-ttu-id="ba8a2-134">匿名型への射影はサポートされていますが、匿名型はエンティティ型以外として扱われるので、データは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-134">Projection into anonymous types is supported, but the data is read-only because anonymous types are treated as non-entity types.</span></span>

<span data-ttu-id="ba8a2-135"> <xref:System.Data.Services.Client.MergeOption> の <xref:System.Data.Services.Client.DataServiceContext> 設定は、クエリ射影時の ID 解決に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-135">The <xref:System.Data.Services.Client.MergeOption> settings of the <xref:System.Data.Services.Client.DataServiceContext> are used for identity resolution during query projection.</span></span> <span data-ttu-id="ba8a2-136">これは、`Customer` 型のインスタンスが <xref:System.Data.Services.Client.DataServiceContext> に存在する場合、同じ ID を持つ `CustomerAddress` のインスタンスは <xref:System.Data.Services.Client.MergeOption> で設定された ID 解決ルールに従うことを意味します。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-136">This means that if an instance of the `Customer` type already exists in the <xref:System.Data.Services.Client.DataServiceContext>, an instance of `CustomerAddress` with the same identity will follow the identity resolution rules set by the <xref:System.Data.Services.Client.MergeOption></span></span>

<span data-ttu-id="ba8a2-137">次に示しますをエンティティとエンティティ以外の型に結果を射影する場合の動作を。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-137">The following describes the behaviors when projecting results into entity and non-entity types:</span></span>

<span data-ttu-id="ba8a2-138">**初期化子を使用して新しい射影インスタンスを作成します。**</span><span class="sxs-lookup"><span data-stu-id="ba8a2-138">**Creating a new projected instance by using initializers**</span></span>

- <span data-ttu-id="ba8a2-139">例:</span><span class="sxs-lookup"><span data-stu-id="ba8a2-139">Example:</span></span>

   [!code-csharp[Astoria Northwind Client#ProjectWithInitializer](~/samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#projectwithinitializer)]
   [!code-vb[Astoria Northwind Client#ProjectWithInitializer](~/samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#projectwithinitializer)]

- <span data-ttu-id="ba8a2-140">エンティティの種類:サポート状況</span><span class="sxs-lookup"><span data-stu-id="ba8a2-140">Entity type: Supported</span></span>

- <span data-ttu-id="ba8a2-141">非エンティティの種類:サポート状況</span><span class="sxs-lookup"><span data-stu-id="ba8a2-141">Non-entity type: Supported</span></span>

<span data-ttu-id="ba8a2-142">**コンス トラクターを使用して新しい射影インスタンスを作成します。**</span><span class="sxs-lookup"><span data-stu-id="ba8a2-142">**Creating a new projected instance by using constructors**</span></span>

- <span data-ttu-id="ba8a2-143">例:</span><span class="sxs-lookup"><span data-stu-id="ba8a2-143">Example:</span></span>

   [!code-csharp[Astoria Northwind Client#ProjectWithConstructor](~/samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#projectwithconstructor)]
   [!code-vb[Astoria Northwind Client#ProjectWithConstructor](~/samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#projectwithconstructor)]

- <span data-ttu-id="ba8a2-144">エンティティの種類:<xref:System.NotSupportedException> 発生</span><span class="sxs-lookup"><span data-stu-id="ba8a2-144">Entity type: A <xref:System.NotSupportedException> is raised.</span></span>

- <span data-ttu-id="ba8a2-145">非エンティティの種類:サポート状況</span><span class="sxs-lookup"><span data-stu-id="ba8a2-145">Non-entity type: Supported</span></span>

<span data-ttu-id="ba8a2-146">**プロジェクションを使用して、プロパティ値を変換するには**</span><span class="sxs-lookup"><span data-stu-id="ba8a2-146">**Using projection to transform a property value**</span></span>

- <span data-ttu-id="ba8a2-147">例:</span><span class="sxs-lookup"><span data-stu-id="ba8a2-147">Example:</span></span>

   [!code-csharp[Astoria Northwind Client#ProjectWithTransform](~/samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#projectwithtransform)]
   [!code-vb[Astoria Northwind Client#ProjectWithTransform](~/samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#projectwithtransform)]

- <span data-ttu-id="ba8a2-148">エンティティの種類:この変換は、エンティティ型では混乱の原因となり、別のエンティティに属するデータ ソース内のデータを上書きする可能性があるため、サポートされません。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-148">Entity type: This transformation is not supported for entity types because it can lead to confusion and potentially overwriting the data in the data source that belongs to another entity.</span></span> <span data-ttu-id="ba8a2-149"><xref:System.NotSupportedException> 発生</span><span class="sxs-lookup"><span data-stu-id="ba8a2-149">A <xref:System.NotSupportedException> is raised.</span></span>

- <span data-ttu-id="ba8a2-150">非エンティティの種類:サポート状況</span><span class="sxs-lookup"><span data-stu-id="ba8a2-150">Non-entity type: Supported</span></span>

<a name="considerations"></a>

## <a name="projection-considerations"></a><span data-ttu-id="ba8a2-151">射影時の注意事項</span><span class="sxs-lookup"><span data-stu-id="ba8a2-151">Projection Considerations</span></span>

<span data-ttu-id="ba8a2-152">クエリ射影を定義する場合は、次の点にも注意してください。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-152">The following additional considerations apply when defining a query projection.</span></span>

- <span data-ttu-id="ba8a2-153">Atom 形式のフィードを独自に定義する場合、カスタム マッピングが定義されているすべてのエンティティ プロパティが射影に含まれることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-153">When you define custom feeds for the Atom format, you must make sure that all entity properties that have custom mappings defined are included in the projection.</span></span> <span data-ttu-id="ba8a2-154">マップされているエンティティ プロパティがこの射影に含まれていない場合、データの損失が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-154">When a mapped entity property is not included in the projection, data loss might occur.</span></span> <span data-ttu-id="ba8a2-155">詳細については、次を参照してください。[フィードのカスタマイズ](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-155">For more information, see [Feed Customization](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).</span></span>

- <span data-ttu-id="ba8a2-156">データ サービスのデータ モデルのエンティティのすべてのプロパティを含まない射影型に挿入を行った場合、クライアントで射影に含まれていないプロパティは既定値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-156">When inserts are made to a projected type that does not contain all of the properties of the entity in the data model of the data service, the properties not included in the projection at the client are set to their default values.</span></span>

- <span data-ttu-id="ba8a2-157">データ サービスのデータ モデルのエンティティのすべてのプロパティを含まない射影影型に対して更新を行った場合、クライアントで射影に含まれていない既存の値は初期化されていない既定値で上書きされます。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-157">When updates are made to a projected type that does not contain all of the properties of the entity in the data model of the data service, existing values not included in the projection on the client will be overwritten with uninitialized default values.</span></span>

- <span data-ttu-id="ba8a2-158">射影に複合プロパティが含まれる場合、複合オブジェクト全体が返される必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-158">When a projection includes a complex property, the entire complex object must be returned.</span></span>

- <span data-ttu-id="ba8a2-159">射影にナビゲーション プロパティが含まれる場合、<xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> メソッドを呼び出す必要はなく、関連オブジェクトが暗黙的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-159">When a projection includes a navigation property, the related objects are loaded implicitly without having to call the <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> method.</span></span> <span data-ttu-id="ba8a2-160">射影されたクエリでの <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> メソッドの使用はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-160">The <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> method is not supported for use in a projected query.</span></span>

- <span data-ttu-id="ba8a2-161">クライアント上のクエリ射影クエリは、要求 URI の `$select` クエリ オプションを使用するように変換されます。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-161">Query projections queries on the client are translated to use the `$select` query option in the request URI.</span></span> <span data-ttu-id="ba8a2-162">[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] クエリ オプションをサポートしない `$select` の以前のバージョンに対して、射影のあるクエリを実行すると、エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-162">When a query with projection is executed against a previous version of [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] that does not support the `$select` query option, an error is returned.</span></span> <span data-ttu-id="ba8a2-163">これは、データ サービスの  <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> の <xref:System.Data.Services.DataServiceBehavior> が <xref:System.Data.Services.Common.DataServiceProtocolVersion.V1> という値に設定されている場合にも発生します。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-163">This can also happen when the <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> of the <xref:System.Data.Services.DataServiceBehavior> for the data service is set to a value of <xref:System.Data.Services.Common.DataServiceProtocolVersion.V1>.</span></span> <span data-ttu-id="ba8a2-164">詳細については、次を参照してください。[データ サービスのバージョン管理](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-164">For more information, see [Data Service Versioning](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).</span></span>

<span data-ttu-id="ba8a2-165">詳細については、「[方法 :クエリ結果を射影](../../../../docs/framework/data/wcf/how-to-project-query-results-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-165">For more information, see [How to: Project Query Results](../../../../docs/framework/data/wcf/how-to-project-query-results-wcf-data-services.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ba8a2-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba8a2-166">See also</span></span>

- [<span data-ttu-id="ba8a2-167">データ サービスに対するクエリ</span><span class="sxs-lookup"><span data-stu-id="ba8a2-167">Querying the Data Service</span></span>](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)
