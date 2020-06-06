---
title: GCLOHThreshold 要素
ms.date: 11/20/2019
helpviewer_keywords:
- GCLOHThreshold element
- <GCLOHThreshold> element
ms.openlocfilehash: d72dc9d27984f60dfb6296217263ce8b176093c6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74451324"
---
# <a name="gclohthreshold-element"></a><span data-ttu-id="9c351-102">GCLOHThreshold 要素</span><span class="sxs-lookup"><span data-stu-id="9c351-102">GCLOHThreshold element</span></span>

<span data-ttu-id="9c351-103">ガベージコレクターがラージオブジェクトヒープ (LOH) にオブジェクトを配置するしきい値のサイズをバイト単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="9c351-103">Specifies the threshold size, in bytes, that causes the garbage collector to put objects on the large object heap (LOH).</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold>

## <a name="syntax"></a><span data-ttu-id="9c351-104">構文</span><span class="sxs-lookup"><span data-stu-id="9c351-104">Syntax</span></span>

```xml
<GCLOHThreshold
   enabled="nnnn"/>
```

## <a name="attributes"></a><span data-ttu-id="9c351-105">属性</span><span class="sxs-lookup"><span data-stu-id="9c351-105">Attributes</span></span>

|<span data-ttu-id="9c351-106">属性</span><span class="sxs-lookup"><span data-stu-id="9c351-106">Attribute</span></span>|<span data-ttu-id="9c351-107">説明</span><span class="sxs-lookup"><span data-stu-id="9c351-107">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="9c351-108">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="9c351-108">Required attribute.</span></span><br /><br /><span data-ttu-id="9c351-109">オブジェクトが大きなオブジェクトヒープに対して実行されるしきい値のサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="9c351-109">Specifies the threshold size that causes objects to go on the large object heap.</span></span>|

### <a name="enabled-attribute"></a><span data-ttu-id="9c351-110">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="9c351-110">enabled attribute</span></span>

|<span data-ttu-id="9c351-111">値</span><span class="sxs-lookup"><span data-stu-id="9c351-111">Value</span></span>|<span data-ttu-id="9c351-112">Description</span><span class="sxs-lookup"><span data-stu-id="9c351-112">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="9c351-113">オブジェクトが大きなオブジェクトヒープに対して実行されるしきい値のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="9c351-113">The threshold size, in bytes, that causes objects to go on the large object heap.</span></span>|

## <a name="child-elements"></a><span data-ttu-id="9c351-114">子要素</span><span class="sxs-lookup"><span data-stu-id="9c351-114">Child elements</span></span>

<span data-ttu-id="9c351-115">なし。</span><span class="sxs-lookup"><span data-stu-id="9c351-115">None.</span></span>

## <a name="parent-elements"></a><span data-ttu-id="9c351-116">親要素</span><span class="sxs-lookup"><span data-stu-id="9c351-116">Parent elements</span></span>

|<span data-ttu-id="9c351-117">要素</span><span class="sxs-lookup"><span data-stu-id="9c351-117">Element</span></span>|<span data-ttu-id="9c351-118">Description</span><span class="sxs-lookup"><span data-stu-id="9c351-118">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="9c351-119">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="9c351-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="9c351-120">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9c351-120">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9c351-121">解説</span><span class="sxs-lookup"><span data-stu-id="9c351-121">Remarks</span></span>

<span data-ttu-id="9c351-122">この設定は .NET Framework 4.8 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="9c351-122">This setting was introduced in .NET Framework 4.8.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c351-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c351-123">See also</span></span>

- [<span data-ttu-id="9c351-124">実行時設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="9c351-124">Run-time settings schema</span></span>](index.md)
- [<span data-ttu-id="9c351-125">構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="9c351-125">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="9c351-126">ガベージ コレクションの基礎</span><span class="sxs-lookup"><span data-stu-id="9c351-126">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="9c351-127">GC の NET Core ランタイム構成オプション</span><span class="sxs-lookup"><span data-stu-id="9c351-127">NET Core run-time config options for GC</span></span>](../../../../core/run-time-config/garbage-collector.md)
