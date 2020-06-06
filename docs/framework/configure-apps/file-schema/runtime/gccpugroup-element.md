---
title: <GCCpuGroup> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: f1cbe5a7109d6e4aae2e92710920a1c6b3a40d00
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "82102893"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="7628a-102">\<GCCpuGroup> 要素</span><span class="sxs-lookup"><span data-stu-id="7628a-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="7628a-103">ガベージ コレクションが複数の CPU グループをサポートするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="7628a-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**

## <a name="syntax"></a><span data-ttu-id="7628a-104">構文</span><span class="sxs-lookup"><span data-stu-id="7628a-104">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7628a-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7628a-105">Attributes and Elements</span></span>

<span data-ttu-id="7628a-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7628a-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7628a-107">属性</span><span class="sxs-lookup"><span data-stu-id="7628a-107">Attributes</span></span>

|<span data-ttu-id="7628a-108">属性</span><span class="sxs-lookup"><span data-stu-id="7628a-108">Attribute</span></span>|<span data-ttu-id="7628a-109">説明</span><span class="sxs-lookup"><span data-stu-id="7628a-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="7628a-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="7628a-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="7628a-111">ガベージ コレクションが複数の CPU グループをサポートするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="7628a-111">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="7628a-112">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="7628a-112">enabled Attribute</span></span>

|<span data-ttu-id="7628a-113">値</span><span class="sxs-lookup"><span data-stu-id="7628a-113">Value</span></span>|<span data-ttu-id="7628a-114">Description</span><span class="sxs-lookup"><span data-stu-id="7628a-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="7628a-115">ガベージ コレクションは複数の CPU グループをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7628a-115">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="7628a-116">既定値です。</span><span class="sxs-lookup"><span data-stu-id="7628a-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="7628a-117">ガベージ コレクションは、サーバーのガベージ コレクションが有効な場合に複数の CPU グループをサポートします。</span><span class="sxs-lookup"><span data-stu-id="7628a-117">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="7628a-118">子要素</span><span class="sxs-lookup"><span data-stu-id="7628a-118">Child Elements</span></span>

<span data-ttu-id="7628a-119">なし。</span><span class="sxs-lookup"><span data-stu-id="7628a-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7628a-120">親要素</span><span class="sxs-lookup"><span data-stu-id="7628a-120">Parent Elements</span></span>

|<span data-ttu-id="7628a-121">要素</span><span class="sxs-lookup"><span data-stu-id="7628a-121">Element</span></span>|<span data-ttu-id="7628a-122">Description</span><span class="sxs-lookup"><span data-stu-id="7628a-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="7628a-123">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="7628a-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="7628a-124">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7628a-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7628a-125">解説</span><span class="sxs-lookup"><span data-stu-id="7628a-125">Remarks</span></span>

<span data-ttu-id="7628a-126">コンピューターに複数の CPU グループがあり、サーバーのガベージコレクションが有効になっている場合 (要素を参照 [\<gcServer>](gcserver-element.md) )、この要素を有効にすると、すべての cpu グループにわたってガベージコレクションが拡張され、ヒープを作成および分散するときにすべてのコアが考慮されます。</span><span class="sxs-lookup"><span data-stu-id="7628a-126">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="7628a-127">この要素は、ガベージ コレクション スレッドにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="7628a-127">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="7628a-128">ランタイムがすべての CPU グループにユーザースレッドを分散できるようにするには、要素も有効にする必要があり [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="7628a-128">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="7628a-129">例</span><span class="sxs-lookup"><span data-stu-id="7628a-129">Example</span></span>

<span data-ttu-id="7628a-130">次の例は、複数の CPU グループのガベージ コレクションを有効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7628a-130">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="7628a-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="7628a-131">See also</span></span>

- [<span data-ttu-id="7628a-132">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="7628a-132">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7628a-133">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="7628a-133">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7628a-134">同時実行ガベージコレクションを無効にする</span><span class="sxs-lookup"><span data-stu-id="7628a-134">Disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="7628a-135">ワークステーションとサーバーのガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="7628a-135">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/workstation-server-gc.md)
