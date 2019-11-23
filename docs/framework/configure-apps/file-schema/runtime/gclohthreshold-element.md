---
title: GCLOHThreshold element
ms.date: 11/20/2019
helpviewer_keywords:
- GCLOHThreshold element
- <GCLOHThreshold> element
ms.openlocfilehash: d72dc9d27984f60dfb6296217263ce8b176093c6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74451324"
---
# <a name="gclohthreshold-element"></a><span data-ttu-id="17d01-102">GCLOHThreshold element</span><span class="sxs-lookup"><span data-stu-id="17d01-102">GCLOHThreshold element</span></span>

<span data-ttu-id="17d01-103">Specifies the threshold size, in bytes, that causes the garbage collector to put objects on the large object heap (LOH).</span><span class="sxs-lookup"><span data-stu-id="17d01-103">Specifies the threshold size, in bytes, that causes the garbage collector to put objects on the large object heap (LOH).</span></span>

<span data-ttu-id="17d01-104">[\<configuration>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="17d01-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="17d01-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="17d01-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="17d01-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold></span><span class="sxs-lookup"><span data-stu-id="17d01-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold></span></span>

## <a name="syntax"></a><span data-ttu-id="17d01-107">構文</span><span class="sxs-lookup"><span data-stu-id="17d01-107">Syntax</span></span>

```xml
<GCLOHThreshold
   enabled="nnnn"/>
```

## <a name="attributes"></a><span data-ttu-id="17d01-108">属性</span><span class="sxs-lookup"><span data-stu-id="17d01-108">Attributes</span></span>

|<span data-ttu-id="17d01-109">属性</span><span class="sxs-lookup"><span data-stu-id="17d01-109">Attribute</span></span>|<span data-ttu-id="17d01-110">説明</span><span class="sxs-lookup"><span data-stu-id="17d01-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="17d01-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="17d01-111">Required attribute.</span></span><br /><br /><span data-ttu-id="17d01-112">Specifies the threshold size that causes objects to go on the large object heap.</span><span class="sxs-lookup"><span data-stu-id="17d01-112">Specifies the threshold size that causes objects to go on the large object heap.</span></span>|

### <a name="enabled-attribute"></a><span data-ttu-id="17d01-113">enabled attribute</span><span class="sxs-lookup"><span data-stu-id="17d01-113">enabled attribute</span></span>

|<span data-ttu-id="17d01-114">[値]</span><span class="sxs-lookup"><span data-stu-id="17d01-114">Value</span></span>|<span data-ttu-id="17d01-115">説明</span><span class="sxs-lookup"><span data-stu-id="17d01-115">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="17d01-116">The threshold size, in bytes, that causes objects to go on the large object heap.</span><span class="sxs-lookup"><span data-stu-id="17d01-116">The threshold size, in bytes, that causes objects to go on the large object heap.</span></span>|

## <a name="child-elements"></a><span data-ttu-id="17d01-117">子要素</span><span class="sxs-lookup"><span data-stu-id="17d01-117">Child elements</span></span>

<span data-ttu-id="17d01-118">なし。</span><span class="sxs-lookup"><span data-stu-id="17d01-118">None.</span></span>

## <a name="parent-elements"></a><span data-ttu-id="17d01-119">親要素</span><span class="sxs-lookup"><span data-stu-id="17d01-119">Parent elements</span></span>

|<span data-ttu-id="17d01-120">要素</span><span class="sxs-lookup"><span data-stu-id="17d01-120">Element</span></span>|<span data-ttu-id="17d01-121">説明</span><span class="sxs-lookup"><span data-stu-id="17d01-121">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="17d01-122">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="17d01-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="17d01-123">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="17d01-123">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="17d01-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="17d01-124">Remarks</span></span>

<span data-ttu-id="17d01-125">This setting was introduced in .NET Framework 4.8.</span><span class="sxs-lookup"><span data-stu-id="17d01-125">This setting was introduced in .NET Framework 4.8.</span></span>

## <a name="see-also"></a><span data-ttu-id="17d01-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="17d01-126">See also</span></span>

- [<span data-ttu-id="17d01-127">Run-time settings schema</span><span class="sxs-lookup"><span data-stu-id="17d01-127">Run-time settings schema</span></span>](index.md)
- [<span data-ttu-id="17d01-128">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="17d01-128">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="17d01-129">ガベージ コレクションの基礎</span><span class="sxs-lookup"><span data-stu-id="17d01-129">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="17d01-130">NET Core run-time config options for GC</span><span class="sxs-lookup"><span data-stu-id="17d01-130">NET Core run-time config options for GC</span></span>](../../../../core/run-time-config/garbage-collector.md)
