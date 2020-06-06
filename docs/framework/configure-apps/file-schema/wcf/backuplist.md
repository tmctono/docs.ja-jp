---
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 478211755b9131c03b72777ee95ff7223b9092c9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850276"
---
# \<backupList>
<span data-ttu-id="dc663-101">プライマリ エンドポイントに接続できないときにルーティング サービスで使用するエンドポイント セットを列挙したバックアップ リストを定義するための構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="dc663-101">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="dc663-102">リストの最初のエンドポイントがダウンしていると、ルーティング サービスは自動的にリスト内で次にあるエンドポイントにフェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="dc663-102">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="dc663-103">これにより、クライアント アプリケーションに複雑なパターンの処理方法やサービスの配置場所を示すことなく、アプリケーションの信頼性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="dc663-103">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupList>**  
  
## <a name="syntax"></a><span data-ttu-id="dc663-104">構文</span><span class="sxs-lookup"><span data-stu-id="dc663-104">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc663-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="dc663-105">Attributes and Elements</span></span>  
 <span data-ttu-id="dc663-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="dc663-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc663-107">属性</span><span class="sxs-lookup"><span data-stu-id="dc663-107">Attributes</span></span>  
  
|<span data-ttu-id="dc663-108">属性</span><span class="sxs-lookup"><span data-stu-id="dc663-108">Attribute</span></span>|<span data-ttu-id="dc663-109">説明</span><span class="sxs-lookup"><span data-stu-id="dc663-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dc663-110">name</span><span class="sxs-lookup"><span data-stu-id="dc663-110">name</span></span>|<span data-ttu-id="dc663-111">このエンドポイント リストを指定するために使用される名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="dc663-111">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc663-112">子要素</span><span class="sxs-lookup"><span data-stu-id="dc663-112">Child Elements</span></span>  
  
|<span data-ttu-id="dc663-113">要素</span><span class="sxs-lookup"><span data-stu-id="dc663-113">Element</span></span>|<span data-ttu-id="dc663-114">Description</span><span class="sxs-lookup"><span data-stu-id="dc663-114">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="dc663-115">親要素</span><span class="sxs-lookup"><span data-stu-id="dc663-115">Parent Elements</span></span>  
  
|<span data-ttu-id="dc663-116">要素</span><span class="sxs-lookup"><span data-stu-id="dc663-116">Element</span></span>|<span data-ttu-id="dc663-117">Description</span><span class="sxs-lookup"><span data-stu-id="dc663-117">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="dc663-118">バックアップ エンドポイントの一覧。</span><span class="sxs-lookup"><span data-stu-id="dc663-118">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc663-119">解説</span><span class="sxs-lookup"><span data-stu-id="dc663-119">Remarks</span></span>  
 <span data-ttu-id="dc663-120">このセクションには、プライマリ エンドポイントへの送信時に通信例外が発生した場合にメッセージが送信されるエンドポイントの、順序付けられたコレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dc663-120">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="dc663-121">の属性に示されているプライマリエンドポイントへの送信が `endpointName` [\<add>](add-of-entries.md) 通信例外で失敗した場合、ルーティングサービスは、この構成セクションの最初のエンドポイントにメッセージを送信しようとします。</span><span class="sxs-lookup"><span data-stu-id="dc663-121">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="dc663-122">これも通信例外によって失敗した場合、ルーティング サービスは、送信に成功するか、通信例外以外のエラーを返すか、コレクション内のすべてのエンドポイントがエラーを返すまで、このセクションに格納された次のエンドポイントにメッセージを送信しようとします。</span><span class="sxs-lookup"><span data-stu-id="dc663-122">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="dc663-123">次の例では、"Destination" という名前のプライマリエンドポイントへの送信で通信例外が返された場合、サービスは "alternateServiceQueue" にメッセージを送信しようとします。</span><span class="sxs-lookup"><span data-stu-id="dc663-123">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="dc663-124">この試行でも通信例外が返された場合、ルーティング サービスはコレクション内の次のエンドポイントにメッセージを送信しようとします。</span><span class="sxs-lookup"><span data-stu-id="dc663-124">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dc663-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc663-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
