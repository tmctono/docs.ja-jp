---
title: <GCCpuGroup> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: ae9c96c9d49cf3f6be94da3f77b91423cab12e0b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430483"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="626ac-102">\<GCCpuGroup> Element</span><span class="sxs-lookup"><span data-stu-id="626ac-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="626ac-103">ガベージ コレクションが複数の CPU グループをサポートするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="626ac-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

<span data-ttu-id="626ac-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="626ac-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="626ac-105">&nbsp;&nbsp;[ **\<runtime>** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="626ac-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="626ac-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<GCCpuGroup>**</span><span class="sxs-lookup"><span data-stu-id="626ac-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="626ac-107">構文</span><span class="sxs-lookup"><span data-stu-id="626ac-107">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="626ac-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="626ac-108">Attributes and Elements</span></span>

<span data-ttu-id="626ac-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="626ac-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="626ac-110">属性</span><span class="sxs-lookup"><span data-stu-id="626ac-110">Attributes</span></span>

|<span data-ttu-id="626ac-111">属性</span><span class="sxs-lookup"><span data-stu-id="626ac-111">Attribute</span></span>|<span data-ttu-id="626ac-112">説明</span><span class="sxs-lookup"><span data-stu-id="626ac-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="626ac-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="626ac-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="626ac-114">ガベージ コレクションが複数の CPU グループをサポートするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="626ac-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="626ac-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="626ac-115">enabled Attribute</span></span>

|<span data-ttu-id="626ac-116">[値]</span><span class="sxs-lookup"><span data-stu-id="626ac-116">Value</span></span>|<span data-ttu-id="626ac-117">説明</span><span class="sxs-lookup"><span data-stu-id="626ac-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="626ac-118">ガベージ コレクションは複数の CPU グループをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="626ac-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="626ac-119">既定値です。</span><span class="sxs-lookup"><span data-stu-id="626ac-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="626ac-120">ガベージ コレクションは、サーバーのガベージ コレクションが有効な場合に複数の CPU グループをサポートします。</span><span class="sxs-lookup"><span data-stu-id="626ac-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="626ac-121">子要素</span><span class="sxs-lookup"><span data-stu-id="626ac-121">Child Elements</span></span>

<span data-ttu-id="626ac-122">なし。</span><span class="sxs-lookup"><span data-stu-id="626ac-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="626ac-123">親要素</span><span class="sxs-lookup"><span data-stu-id="626ac-123">Parent Elements</span></span>

|<span data-ttu-id="626ac-124">要素</span><span class="sxs-lookup"><span data-stu-id="626ac-124">Element</span></span>|<span data-ttu-id="626ac-125">説明</span><span class="sxs-lookup"><span data-stu-id="626ac-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="626ac-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="626ac-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="626ac-127">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="626ac-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="626ac-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="626ac-128">Remarks</span></span>

<span data-ttu-id="626ac-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span><span class="sxs-lookup"><span data-stu-id="626ac-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="626ac-130">この要素は、ガベージ コレクション スレッドにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="626ac-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="626ac-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span><span class="sxs-lookup"><span data-stu-id="626ac-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="626ac-132">例</span><span class="sxs-lookup"><span data-stu-id="626ac-132">Example</span></span>

<span data-ttu-id="626ac-133">次の例は、複数の CPU グループのガベージ コレクションを有効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="626ac-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="626ac-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="626ac-134">See also</span></span>

- [<span data-ttu-id="626ac-135">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="626ac-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="626ac-136">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="626ac-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="626ac-137">To disable concurrent garbage collection</span><span class="sxs-lookup"><span data-stu-id="626ac-137">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="626ac-138">ワークステーションとサーバーのガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="626ac-138">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection)
