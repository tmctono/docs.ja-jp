---
title: <Thread_UseAllCpuGroups> 要素
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
ms.openlocfilehash: a3a612c0ffbcb211157b9623d298ce8ad7a13e94
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115409"
---
# <a name="thread_useallcpugroups-element"></a><span data-ttu-id="32f79-102">\<Thread_UseAllCpuGroups> 要素</span><span class="sxs-lookup"><span data-stu-id="32f79-102">\<Thread_UseAllCpuGroups> Element</span></span>

<span data-ttu-id="32f79-103">ランタイムによって、すべての CPU グループにマネージド スレッドを分散するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="32f79-103">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Thread_UseAllCpuGroups>**  

## <a name="syntax"></a><span data-ttu-id="32f79-104">構文</span><span class="sxs-lookup"><span data-stu-id="32f79-104">Syntax</span></span>

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="32f79-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="32f79-105">Attributes and Elements</span></span>

<span data-ttu-id="32f79-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="32f79-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="32f79-107">属性</span><span class="sxs-lookup"><span data-stu-id="32f79-107">Attributes</span></span>

|<span data-ttu-id="32f79-108">属性</span><span class="sxs-lookup"><span data-stu-id="32f79-108">Attribute</span></span>|<span data-ttu-id="32f79-109">説明</span><span class="sxs-lookup"><span data-stu-id="32f79-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="32f79-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="32f79-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="32f79-111">ランタイムによって、すべての CPU グループにマネージド スレッドを分散するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="32f79-111">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="32f79-112">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="32f79-112">enabled Attribute</span></span>

|<span data-ttu-id="32f79-113">値</span><span class="sxs-lookup"><span data-stu-id="32f79-113">Value</span></span>|<span data-ttu-id="32f79-114">Description</span><span class="sxs-lookup"><span data-stu-id="32f79-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="32f79-115">ランタイムは、複数の CPU グループにマネージド スレッドを分散しません。</span><span class="sxs-lookup"><span data-stu-id="32f79-115">The runtime does not distribute managed threads across multiple CPU groups.</span></span> <span data-ttu-id="32f79-116">既定値です。</span><span class="sxs-lookup"><span data-stu-id="32f79-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="32f79-117">コンピューターに複数の CPU グループがあり、 [\<GCCpuGroup>](gccpugroup-element.md) 要素が有効になっている場合、ランタイムは複数の cpu グループにマネージスレッドを分散します。</span><span class="sxs-lookup"><span data-stu-id="32f79-117">The runtime distributes managed threads across multiple CPU groups, if the computer has multiple CPU groups and the [\<GCCpuGroup>](gccpugroup-element.md) element is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="32f79-118">子要素</span><span class="sxs-lookup"><span data-stu-id="32f79-118">Child Elements</span></span>

<span data-ttu-id="32f79-119">なし。</span><span class="sxs-lookup"><span data-stu-id="32f79-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="32f79-120">親要素</span><span class="sxs-lookup"><span data-stu-id="32f79-120">Parent Elements</span></span>

|<span data-ttu-id="32f79-121">要素</span><span class="sxs-lookup"><span data-stu-id="32f79-121">Element</span></span>|<span data-ttu-id="32f79-122">Description</span><span class="sxs-lookup"><span data-stu-id="32f79-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="32f79-123">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="32f79-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="32f79-124">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="32f79-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="32f79-125">解説</span><span class="sxs-lookup"><span data-stu-id="32f79-125">Remarks</span></span>

<span data-ttu-id="32f79-126">コンピューターに複数の CPU グループがある場合、この要素を有効にすると、ランタイムは、すべての CPU グループにマネージド スレッドを分散します。</span><span class="sxs-lookup"><span data-stu-id="32f79-126">When a computer has multiple CPU groups, enabling this element causes the runtime to distribute managed threads across all CPU groups.</span></span> <span data-ttu-id="32f79-127">この機能を使用するには、要素を有効にする必要もあります。これにより、 [\<GCCpuGroup>](gccpugroup-element.md) ガベージコレクションがすべての CPU グループに拡張され、ヒープを作成および分散するときにすべてのコアが考慮されます。</span><span class="sxs-lookup"><span data-stu-id="32f79-127">To use this feature, you must also enable the [\<GCCpuGroup>](gccpugroup-element.md) element, which extends garbage collection to all CPU groups and takes all cores into account when creating and balancing heaps.</span></span> <span data-ttu-id="32f79-128">要素を有効にする [\<GCCpuGroup>](gccpugroup-element.md) には、要素を有効にする必要があり [\<gcServer>](gcserver-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="32f79-128">Enabling the [\<GCCpuGroup>](gccpugroup-element.md) element requires enabling the [\<gcServer>](gcserver-element.md) element.</span></span> <span data-ttu-id="32f79-129">これらの要素が有効でない場合、`<Thread_UseAllCpuGroups>` 要素を有効にしても効力はありません。</span><span class="sxs-lookup"><span data-stu-id="32f79-129">If these elements are not enabled, enabling the `<Thread_UseAllCpuGroups>` element has no effect.</span></span>

## <a name="example"></a><span data-ttu-id="32f79-130">例</span><span class="sxs-lookup"><span data-stu-id="32f79-130">Example</span></span>

<span data-ttu-id="32f79-131">次の例は、複数の CPU グループのサポートを有効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="32f79-131">The following example shows how to enable support for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <Thread_UseAllCpuGroups enabled="true"/>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="32f79-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="32f79-132">See also</span></span>

- [<span data-ttu-id="32f79-133">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="32f79-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="32f79-134">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="32f79-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="32f79-135">\<GCCpuGroup>Element</span><span class="sxs-lookup"><span data-stu-id="32f79-135">\<GCCpuGroup> Element</span></span>](gccpugroup-element.md)
