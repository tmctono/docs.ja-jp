---
title: GCNoAffinitize 要素
ms.date: 11/08/2019
helpviewer_keywords:
- gcNoAffinitize element
- <gcNoAffinitize> element
ms.openlocfilehash: 16d6e5adefe2b632d7251669650058d7df7cea70
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004739"
---
# <a name="gcnoaffinitize-element"></a><span data-ttu-id="0e3e6-102">\<GCNoAffinitize> 要素</span><span class="sxs-lookup"><span data-stu-id="0e3e6-102">\<GCNoAffinitize> element</span></span>

<span data-ttu-id="0e3e6-103">Cpu を使用してサーバー GC スレッドを関係付けするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="0e3e6-103">Specifies whether or not to affinitize server GC threads with CPUs.</span></span>

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCNoAffinitize>

## <a name="syntax"></a><span data-ttu-id="0e3e6-104">構文</span><span class="sxs-lookup"><span data-stu-id="0e3e6-104">Syntax</span></span>

```xml
<GCNoAffinitize
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0e3e6-105">属性と要素</span><span class="sxs-lookup"><span data-stu-id="0e3e6-105">Attributes and elements</span></span>

<span data-ttu-id="0e3e6-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0e3e6-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0e3e6-107">属性</span><span class="sxs-lookup"><span data-stu-id="0e3e6-107">Attributes</span></span>

|<span data-ttu-id="0e3e6-108">属性</span><span class="sxs-lookup"><span data-stu-id="0e3e6-108">Attribute</span></span>|<span data-ttu-id="0e3e6-109">説明</span><span class="sxs-lookup"><span data-stu-id="0e3e6-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="0e3e6-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="0e3e6-110">Required attribute.</span></span><br /><br /><span data-ttu-id="0e3e6-111">サーバー GC スレッド/ヒープをコンピューターで使用可能なプロセッサと関連付けるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="0e3e6-111">Specifies whether server GC threads/heaps are affinitized with the processors available on the machine.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="0e3e6-112">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="0e3e6-112">enabled attribute</span></span>

|<span data-ttu-id="0e3e6-113">値</span><span class="sxs-lookup"><span data-stu-id="0e3e6-113">Value</span></span>|<span data-ttu-id="0e3e6-114">[説明]</span><span class="sxs-lookup"><span data-stu-id="0e3e6-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="0e3e6-115">アフィニティ化する server GC スレッドと Cpu。</span><span class="sxs-lookup"><span data-stu-id="0e3e6-115">Affinitizes server GC threads with CPUs.</span></span> <span data-ttu-id="0e3e6-116">既定値です。</span><span class="sxs-lookup"><span data-stu-id="0e3e6-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="0e3e6-117">では、Cpu を使用してサーバー GC スレッドを関係付けません。</span><span class="sxs-lookup"><span data-stu-id="0e3e6-117">Does not affinitize server GC threads with CPUs.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="0e3e6-118">子要素</span><span class="sxs-lookup"><span data-stu-id="0e3e6-118">Child elements</span></span>

<span data-ttu-id="0e3e6-119">なし。</span><span class="sxs-lookup"><span data-stu-id="0e3e6-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0e3e6-120">親要素</span><span class="sxs-lookup"><span data-stu-id="0e3e6-120">Parent elements</span></span>

|<span data-ttu-id="0e3e6-121">要素</span><span class="sxs-lookup"><span data-stu-id="0e3e6-121">Element</span></span>|<span data-ttu-id="0e3e6-122">説明</span><span class="sxs-lookup"><span data-stu-id="0e3e6-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="0e3e6-123">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="0e3e6-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="0e3e6-124">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e3e6-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0e3e6-125">コメント</span><span class="sxs-lookup"><span data-stu-id="0e3e6-125">Remarks</span></span>

<span data-ttu-id="0e3e6-126">既定では、サーバー GC スレッドはそれぞれの Cpu とハード関係があります。</span><span class="sxs-lookup"><span data-stu-id="0e3e6-126">By default, server GC threads are hard-affinitized with their respective CPUs.</span></span> <span data-ttu-id="0e3e6-127">システムの使用可能な各プロセッサには、独自の GC ヒープとスレッドがあります。</span><span class="sxs-lookup"><span data-stu-id="0e3e6-127">Each of the system's available processors has its own GC heap and thread.</span></span> <span data-ttu-id="0e3e6-128">これは、キャッシュの使用を最適化するため、通常は推奨される設定です。</span><span class="sxs-lookup"><span data-stu-id="0e3e6-128">This is typically the preferred setting since it optimizes cache usage.</span></span> <span data-ttu-id="0e3e6-129">4.6.2 .NET Framework 以降では、 **GCNoAffinitize**要素の属性をに設定することにより、 `enabled` `true` サーバー GC スレッドと cpu を密に結合しないように指定できます。</span><span class="sxs-lookup"><span data-stu-id="0e3e6-129">Starting with .NET Framework 4.6.2, by setting the **GCNoAffinitize** element's `enabled` attribute to `true`, you can specify that server GC threads and CPUs should not be tightly coupled.</span></span>

<span data-ttu-id="0e3e6-130">Cpu を使用してサーバー GC スレッドを関係付けしないように、 **GCNoAffinitize**構成要素のみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0e3e6-130">You can specify the **GCNoAffinitize** configuration element alone to not affinitize server GC threads with CPUs.</span></span> <span data-ttu-id="0e3e6-131">また、アプリケーションで使用される GC ヒープとスレッドの数を制御するために、この要素を[Gの Apcount](gcheapcount-element.md)要素と共に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="0e3e6-131">You can also use it along with the [GCHeapCount](gcheapcount-element.md) element to control the number of GC heaps and threads used by an application.</span></span>

<span data-ttu-id="0e3e6-132">`enabled` **GCNoAffinitize**要素の属性が `false` (既定値) の場合は、 [g apcount](gcheapcount-element.md)要素を使用して gc スレッドとヒープの数を指定することもできます。また、 [GCHEAPAFFINITIZEMASK](gcheapaffinitizemask-element.md)要素を使用して、gc スレッドとヒープが関連付けられているプロセッサを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="0e3e6-132">If the `enabled` attribute of the **GCNoAffinitize** element is `false` (its default value), you can also use the [GCHeapCount](gcheapcount-element.md) element to specify the number of GC threads and heaps, along with the [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) element to specify the processors to which the GC threads and heaps are affinitized.</span></span>

## <a name="example"></a><span data-ttu-id="0e3e6-133">例</span><span class="sxs-lookup"><span data-stu-id="0e3e6-133">Example</span></span>

<span data-ttu-id="0e3e6-134">次の例では、サーバー GC スレッドをハード関係付けしていません。</span><span class="sxs-lookup"><span data-stu-id="0e3e6-134">The following example does not hard-affinitize server GC threads:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

<span data-ttu-id="0e3e6-135">次の例では、サーバー GC スレッドを関係付けせず、GC ヒープ/スレッドの数を10に制限しています。</span><span class="sxs-lookup"><span data-stu-id="0e3e6-135">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="0e3e6-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e3e6-136">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="0e3e6-137">GCHeapAffinitizeMask 要素</span><span class="sxs-lookup"><span data-stu-id="0e3e6-137">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="0e3e6-138">G不正 Apcount 要素</span><span class="sxs-lookup"><span data-stu-id="0e3e6-138">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="0e3e6-139">ガベージ コレクションの基礎</span><span class="sxs-lookup"><span data-stu-id="0e3e6-139">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="0e3e6-140">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="0e3e6-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0e3e6-141">構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="0e3e6-141">Configuration File Schema</span></span>](../index.md)
