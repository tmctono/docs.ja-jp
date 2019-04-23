---
title: <GCCpuGroup> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85cfe57f7a3b8cfecfae4c4ae00efaea464e6120
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090343"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="40a98-102">\<GCCpuGroup > 要素</span><span class="sxs-lookup"><span data-stu-id="40a98-102">\<GCCpuGroup> Element</span></span>
<span data-ttu-id="40a98-103">ガベージ コレクションが複数の CPU グループをサポートするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="40a98-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>  
  
 <span data-ttu-id="40a98-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="40a98-104">\<configuration></span></span>  
<span data-ttu-id="40a98-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="40a98-105">\<runtime></span></span>  
<span data-ttu-id="40a98-106">\<GCCpuGroup></span><span class="sxs-lookup"><span data-stu-id="40a98-106">\<GCCpuGroup></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40a98-107">構文</span><span class="sxs-lookup"><span data-stu-id="40a98-107">Syntax</span></span>  
  
```xml  
<GCCpuGroup    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40a98-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="40a98-108">Attributes and Elements</span></span>  
 <span data-ttu-id="40a98-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="40a98-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40a98-110">属性</span><span class="sxs-lookup"><span data-stu-id="40a98-110">Attributes</span></span>  
  
|<span data-ttu-id="40a98-111">属性</span><span class="sxs-lookup"><span data-stu-id="40a98-111">Attribute</span></span>|<span data-ttu-id="40a98-112">説明</span><span class="sxs-lookup"><span data-stu-id="40a98-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="40a98-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="40a98-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="40a98-114">ガベージ コレクションが複数の CPU グループをサポートするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="40a98-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="40a98-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="40a98-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="40a98-116">値</span><span class="sxs-lookup"><span data-stu-id="40a98-116">Value</span></span>|<span data-ttu-id="40a98-117">説明</span><span class="sxs-lookup"><span data-stu-id="40a98-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="40a98-118">ガベージ コレクションは複数の CPU グループをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="40a98-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="40a98-119">既定値です。</span><span class="sxs-lookup"><span data-stu-id="40a98-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="40a98-120">ガベージ コレクションは、サーバーのガベージ コレクションが有効な場合に複数の CPU グループをサポートします。</span><span class="sxs-lookup"><span data-stu-id="40a98-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40a98-121">子要素</span><span class="sxs-lookup"><span data-stu-id="40a98-121">Child Elements</span></span>  
 <span data-ttu-id="40a98-122">なし。</span><span class="sxs-lookup"><span data-stu-id="40a98-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40a98-123">親要素</span><span class="sxs-lookup"><span data-stu-id="40a98-123">Parent Elements</span></span>  
  
|<span data-ttu-id="40a98-124">要素</span><span class="sxs-lookup"><span data-stu-id="40a98-124">Element</span></span>|<span data-ttu-id="40a98-125">説明</span><span class="sxs-lookup"><span data-stu-id="40a98-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="40a98-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="40a98-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="40a98-127">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="40a98-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40a98-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="40a98-128">Remarks</span></span>  
 <span data-ttu-id="40a98-129">コンピューターに複数の CPU グループとサーバーのガベージ コレクションが有効になっている (を参照してください、 [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md)要素)、この要素を有効にするすべての CPU グループ全体でガベージ コレクションを拡張し、すべてのコアにアカウントを作成すると、ヒープを分散します。</span><span class="sxs-lookup"><span data-stu-id="40a98-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40a98-130">この要素は、ガベージ コレクション スレッドにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="40a98-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="40a98-131">ユーザー スレッドをすべての CPU グループに分散するランタイムを有効にする必要がありますも有効にする、 [< Thread_UseAllCpuGroups >](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)要素。</span><span class="sxs-lookup"><span data-stu-id="40a98-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [<Thread_UseAllCpuGroups>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40a98-132">例</span><span class="sxs-lookup"><span data-stu-id="40a98-132">Example</span></span>  
 <span data-ttu-id="40a98-133">次の例は、複数の CPU グループのガベージ コレクションを有効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="40a98-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="40a98-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="40a98-134">See also</span></span>

- [<span data-ttu-id="40a98-135">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="40a98-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="40a98-136">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="40a98-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="40a98-137">同時実行ガベージ コレクションを無効にするには</span><span class="sxs-lookup"><span data-stu-id="40a98-137">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="40a98-138">ワークステーションとサーバーのガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="40a98-138">Workstation and server garbage collection</span></span>](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
