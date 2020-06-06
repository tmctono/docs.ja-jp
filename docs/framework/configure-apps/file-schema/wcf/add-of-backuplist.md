---
title: <add> の <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 80726cc22cb56013c85c7704c28579b1337666c9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850545"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="f993a-102">\<add> の \<backupList></span><span class="sxs-lookup"><span data-stu-id="f993a-102">\<add> of \<backupList></span></span>
<span data-ttu-id="f993a-103">バックアップ エンドポイント要素を定義する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="f993a-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupList>**](backuplist.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="f993a-104">構文</span><span class="sxs-lookup"><span data-stu-id="f993a-104">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f993a-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f993a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f993a-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f993a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f993a-107">属性</span><span class="sxs-lookup"><span data-stu-id="f993a-107">Attributes</span></span>  
  
|<span data-ttu-id="f993a-108">属性</span><span class="sxs-lookup"><span data-stu-id="f993a-108">Attribute</span></span>|<span data-ttu-id="f993a-109">説明</span><span class="sxs-lookup"><span data-stu-id="f993a-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f993a-110">name</span><span class="sxs-lookup"><span data-stu-id="f993a-110">name</span></span>|<span data-ttu-id="f993a-111">バックアップ エンドポイントの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="f993a-111">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f993a-112">子要素</span><span class="sxs-lookup"><span data-stu-id="f993a-112">Child Elements</span></span>  
 <span data-ttu-id="f993a-113">なし。</span><span class="sxs-lookup"><span data-stu-id="f993a-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f993a-114">親要素</span><span class="sxs-lookup"><span data-stu-id="f993a-114">Parent Elements</span></span>  
  
|<span data-ttu-id="f993a-115">要素</span><span class="sxs-lookup"><span data-stu-id="f993a-115">Element</span></span>|<span data-ttu-id="f993a-116">Description</span><span class="sxs-lookup"><span data-stu-id="f993a-116">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="f993a-117">プライマリ エンドポイントに接続できないときにルーティング サービスが使用するエンドポイントのリストを格納します。</span><span class="sxs-lookup"><span data-stu-id="f993a-117">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f993a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f993a-118">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
