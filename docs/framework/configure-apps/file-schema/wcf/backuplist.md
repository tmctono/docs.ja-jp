---
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: b0a6c604b5741c1355c35fca510cd10544dab9f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704428"
---
# <a name="backuplist"></a><span data-ttu-id="62445-101">\<backupList></span><span class="sxs-lookup"><span data-stu-id="62445-101">\<backupList></span></span>
<span data-ttu-id="62445-102">プライマリ エンドポイントに接続できない場合に使用するルーティング サービスが希望されるエンドポイントのセットを列挙したバックアップ リストを定義するための構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="62445-102">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="62445-103">リストの最初のエンドポイントがダウンしていると、ルーティング サービスは自動的にリスト内で次にあるエンドポイントにフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="62445-103">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="62445-104">これにより、クライアント アプリケーションに複雑なパターンの処理方法やサービスの配置場所を示すことなく、アプリケーションの信頼性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="62445-104">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="62445-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="62445-105">\<system.serviceModel></span></span>  
<span data-ttu-id="62445-106">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="62445-106">\<routing></span></span>  
<span data-ttu-id="62445-107">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="62445-107">\<backupLists></span></span>  
<span data-ttu-id="62445-108">\<backupList></span><span class="sxs-lookup"><span data-stu-id="62445-108">\<backupList></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62445-109">構文</span><span class="sxs-lookup"><span data-stu-id="62445-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62445-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="62445-110">Attributes and Elements</span></span>  
 <span data-ttu-id="62445-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="62445-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62445-112">属性</span><span class="sxs-lookup"><span data-stu-id="62445-112">Attributes</span></span>  
  
|<span data-ttu-id="62445-113">属性</span><span class="sxs-lookup"><span data-stu-id="62445-113">Attribute</span></span>|<span data-ttu-id="62445-114">説明</span><span class="sxs-lookup"><span data-stu-id="62445-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="62445-115">name</span><span class="sxs-lookup"><span data-stu-id="62445-115">name</span></span>|<span data-ttu-id="62445-116">このエンドポイント リストを指定するために使用される名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="62445-116">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62445-117">子要素</span><span class="sxs-lookup"><span data-stu-id="62445-117">Child Elements</span></span>  
  
|<span data-ttu-id="62445-118">要素</span><span class="sxs-lookup"><span data-stu-id="62445-118">Element</span></span>|<span data-ttu-id="62445-119">説明</span><span class="sxs-lookup"><span data-stu-id="62445-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62445-120">\<filter></span><span class="sxs-lookup"><span data-stu-id="62445-120">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="62445-121">親要素</span><span class="sxs-lookup"><span data-stu-id="62445-121">Parent Elements</span></span>  
  
|<span data-ttu-id="62445-122">要素</span><span class="sxs-lookup"><span data-stu-id="62445-122">Element</span></span>|<span data-ttu-id="62445-123">説明</span><span class="sxs-lookup"><span data-stu-id="62445-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62445-124">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="62445-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="62445-125">バックアップ エンドポイントの一覧。</span><span class="sxs-lookup"><span data-stu-id="62445-125">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62445-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="62445-126">Remarks</span></span>  
 <span data-ttu-id="62445-127">このセクションには、プライマリ エンドポイントへの送信時に通信例外が発生した場合にメッセージが送信されるエンドポイントの、順序付けられたコレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="62445-127">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="62445-128">プライマリ エンドポイントへの送信が表示されている場合、`endpointName`属性の[\<追加 >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md)通信例外によって失敗、ルーティング サービスがこの最初のエンドポイントにメッセージを送信しようとは構成セクション。</span><span class="sxs-lookup"><span data-stu-id="62445-128">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="62445-129">これも通信例外によって失敗した場合、ルーティング サービスは、送信に成功するか、通信例外以外のエラーを返すか、コレクション内のすべてのエンドポイントがエラーを返すまで、このセクションに格納された次のエンドポイントにメッセージを送信しようとします。</span><span class="sxs-lookup"><span data-stu-id="62445-129">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="62445-130">次の例では、"Destination"という名前のプライマリ エンドポイントへの送信には、通信例外が返された場合、サービスは"alternateServiceQueue"にメッセージを送信を試みます。</span><span class="sxs-lookup"><span data-stu-id="62445-130">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="62445-131">この試行でも通信例外が返された場合、ルーティング サービスはコレクション内の次のエンドポイントにメッセージを送信しようとします。</span><span class="sxs-lookup"><span data-stu-id="62445-131">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
```xml  
<filterTables>
  <filterTable name="filterTable1">
    <add filterName="MatchAllFilter1"
         endpointName="Destination"
         backupList="backupEndpointList" />
  </filterTable>
</filterTables>
<backupLists>
  <backupList name="backupEndpointList">
    <add endpointName="backupServiceQueue" />
    <add endpointName="alternateServiceQueue" />
  </backupList>
</backupLists>
```  
  
## <a name="see-also"></a><span data-ttu-id="62445-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="62445-132">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
