---
title: <GCCpuGroup> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: 352890519c1a227d664d877c3123866e5e4e1657
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116829"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="f0460-102">\<GCCpuGroup > 要素</span><span class="sxs-lookup"><span data-stu-id="f0460-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="f0460-103">ガベージ コレクションが複数の CPU グループをサポートするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0460-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

<span data-ttu-id="f0460-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f0460-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f0460-105">&nbsp;&nbsp;[ **\<runtime>** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="f0460-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="f0460-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<GCCpuGroup >**</span><span class="sxs-lookup"><span data-stu-id="f0460-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="f0460-107">構文</span><span class="sxs-lookup"><span data-stu-id="f0460-107">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f0460-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f0460-108">Attributes and Elements</span></span>

<span data-ttu-id="f0460-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f0460-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f0460-110">属性</span><span class="sxs-lookup"><span data-stu-id="f0460-110">Attributes</span></span>

|<span data-ttu-id="f0460-111">属性</span><span class="sxs-lookup"><span data-stu-id="f0460-111">Attribute</span></span>|<span data-ttu-id="f0460-112">説明</span><span class="sxs-lookup"><span data-stu-id="f0460-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="f0460-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="f0460-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="f0460-114">ガベージ コレクションが複数の CPU グループをサポートするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0460-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="f0460-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="f0460-115">enabled Attribute</span></span>

|<span data-ttu-id="f0460-116">[値]</span><span class="sxs-lookup"><span data-stu-id="f0460-116">Value</span></span>|<span data-ttu-id="f0460-117">説明</span><span class="sxs-lookup"><span data-stu-id="f0460-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="f0460-118">ガベージ コレクションは複数の CPU グループをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f0460-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="f0460-119">既定値です。</span><span class="sxs-lookup"><span data-stu-id="f0460-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="f0460-120">ガベージ コレクションは、サーバーのガベージ コレクションが有効な場合に複数の CPU グループをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f0460-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f0460-121">子要素</span><span class="sxs-lookup"><span data-stu-id="f0460-121">Child Elements</span></span>

<span data-ttu-id="f0460-122">なし。</span><span class="sxs-lookup"><span data-stu-id="f0460-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f0460-123">親要素</span><span class="sxs-lookup"><span data-stu-id="f0460-123">Parent Elements</span></span>

|<span data-ttu-id="f0460-124">要素</span><span class="sxs-lookup"><span data-stu-id="f0460-124">Element</span></span>|<span data-ttu-id="f0460-125">説明</span><span class="sxs-lookup"><span data-stu-id="f0460-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="f0460-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="f0460-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="f0460-127">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f0460-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f0460-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="f0460-128">Remarks</span></span>

<span data-ttu-id="f0460-129">コンピューターに複数の CPU グループがあり、サーバーのガベージコレクションが有効になっている場合 ( [\<gcServer >](gcserver-element.md)要素を参照)、この要素を有効にすると、すべての cpu グループにわたってガベージコレクションが拡張され、との作成時にすべてのコアが考慮されます。ヒープを分散しています。</span><span class="sxs-lookup"><span data-stu-id="f0460-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="f0460-130">この要素は、ガベージ コレクション スレッドにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="f0460-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="f0460-131">ランタイムがすべての CPU グループにユーザースレッドを分散できるようにするには、 [\<Thread_UseAllCpuGroups >](thread-useallcpugroups-element.md)要素も有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0460-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="f0460-132">例</span><span class="sxs-lookup"><span data-stu-id="f0460-132">Example</span></span>

<span data-ttu-id="f0460-133">次の例は、複数の CPU グループのガベージ コレクションを有効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f0460-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="f0460-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0460-134">See also</span></span>

- [<span data-ttu-id="f0460-135">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="f0460-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f0460-136">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="f0460-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f0460-137">同時実行ガベージコレクションを無効にするには</span><span class="sxs-lookup"><span data-stu-id="f0460-137">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="f0460-138">ワークステーションとサーバーのガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="f0460-138">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
