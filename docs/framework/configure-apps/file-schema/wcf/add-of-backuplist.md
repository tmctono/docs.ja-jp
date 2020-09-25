---
title: <add> の <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 6d8fd26170059226583a300b1b48b849666db929
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181623"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="dc53f-102">\<add> の \<backupList></span><span class="sxs-lookup"><span data-stu-id="dc53f-102">\<add> of \<backupList></span></span>

<span data-ttu-id="dc53f-103">バックアップ エンドポイント要素を定義する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="dc53f-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupList>**](backuplist.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="dc53f-104">構文</span><span class="sxs-lookup"><span data-stu-id="dc53f-104">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc53f-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="dc53f-105">Attributes and Elements</span></span>  

 <span data-ttu-id="dc53f-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="dc53f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc53f-107">属性</span><span class="sxs-lookup"><span data-stu-id="dc53f-107">Attributes</span></span>  
  
|<span data-ttu-id="dc53f-108">属性</span><span class="sxs-lookup"><span data-stu-id="dc53f-108">Attribute</span></span>|<span data-ttu-id="dc53f-109">説明</span><span class="sxs-lookup"><span data-stu-id="dc53f-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dc53f-110">name</span><span class="sxs-lookup"><span data-stu-id="dc53f-110">name</span></span>|<span data-ttu-id="dc53f-111">バックアップ エンドポイントの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="dc53f-111">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc53f-112">子要素</span><span class="sxs-lookup"><span data-stu-id="dc53f-112">Child Elements</span></span>  

 <span data-ttu-id="dc53f-113">なし。</span><span class="sxs-lookup"><span data-stu-id="dc53f-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dc53f-114">親要素</span><span class="sxs-lookup"><span data-stu-id="dc53f-114">Parent Elements</span></span>  
  
|<span data-ttu-id="dc53f-115">要素</span><span class="sxs-lookup"><span data-stu-id="dc53f-115">Element</span></span>|<span data-ttu-id="dc53f-116">説明</span><span class="sxs-lookup"><span data-stu-id="dc53f-116">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="dc53f-117">プライマリ エンドポイントに接続できないときにルーティング サービスが使用するエンドポイントのリストを格納します。</span><span class="sxs-lookup"><span data-stu-id="dc53f-117">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc53f-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc53f-118">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
