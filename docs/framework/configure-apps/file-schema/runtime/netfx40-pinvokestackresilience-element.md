---
title: <NetFx40_PInvokeStackResilience> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8f4dffe5428ccb7541055fa4f3f335f57deaf2ec
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252426"
---
# <a name="netfx40_pinvokestackresilience-element"></a><span data-ttu-id="58832-102">\<NetFx40_PInvokeStackResilience> 要素</span><span class="sxs-lookup"><span data-stu-id="58832-102">\<NetFx40_PInvokeStackResilience> Element</span></span>

<span data-ttu-id="58832-103">ランタイムが実行時の不適切なプラットフォーム呼び出し宣言を自動的に修正するかどうかを指定します。これにより、マネージド コードとアンマネージド コード間の遷移が遅くなります。</span><span class="sxs-lookup"><span data-stu-id="58832-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>

<span data-ttu-id="58832-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="58832-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="58832-105">&nbsp;&nbsp;[ **\<runtime>** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="58832-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="58832-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<NetFx40_PInvokeStackResilience >**</span><span class="sxs-lookup"><span data-stu-id="58832-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_PInvokeStackResilience>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="58832-107">構文</span><span class="sxs-lookup"><span data-stu-id="58832-107">Syntax</span></span>

```xml
<NetFx40_PInvokeStackResilience  enabled="1|0"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="58832-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="58832-108">Attributes and Elements</span></span>

<span data-ttu-id="58832-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="58832-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="58832-110">属性</span><span class="sxs-lookup"><span data-stu-id="58832-110">Attributes</span></span>

|<span data-ttu-id="58832-111">属性</span><span class="sxs-lookup"><span data-stu-id="58832-111">Attribute</span></span>|<span data-ttu-id="58832-112">説明</span><span class="sxs-lookup"><span data-stu-id="58832-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="58832-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="58832-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="58832-114">ランタイムが無効なプラットフォーム呼び出し宣言を検出し、実行時に32ビットプラットフォームで自動的にスタックを修正するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="58832-114">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="58832-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="58832-115">enabled Attribute</span></span>

|<span data-ttu-id="58832-116">値</span><span class="sxs-lookup"><span data-stu-id="58832-116">Value</span></span>|<span data-ttu-id="58832-117">説明</span><span class="sxs-lookup"><span data-stu-id="58832-117">Description</span></span>|
|-----------|-----------------|
|`0`|<span data-ttu-id="58832-118">ランタイムは、.NET Framework 4 で導入された高速な相互運用マーシャリングアーキテクチャを使用します。これは、不適切なプラットフォーム呼び出し宣言を検出して修正するものではありません。</span><span class="sxs-lookup"><span data-stu-id="58832-118">The runtime uses the faster interop marshaling architecture introduced in the .NET Framework 4, which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="58832-119">既定値です。</span><span class="sxs-lookup"><span data-stu-id="58832-119">This is the default.</span></span>|
|`1`|<span data-ttu-id="58832-120">ランタイムは、不適切なプラットフォーム呼び出し宣言を検出して修正する低速の遷移を使用します。</span><span class="sxs-lookup"><span data-stu-id="58832-120">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="58832-121">子要素</span><span class="sxs-lookup"><span data-stu-id="58832-121">Child Elements</span></span>

<span data-ttu-id="58832-122">なし。</span><span class="sxs-lookup"><span data-stu-id="58832-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="58832-123">親要素</span><span class="sxs-lookup"><span data-stu-id="58832-123">Parent Elements</span></span>

|<span data-ttu-id="58832-124">要素</span><span class="sxs-lookup"><span data-stu-id="58832-124">Element</span></span>|<span data-ttu-id="58832-125">説明</span><span class="sxs-lookup"><span data-stu-id="58832-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="58832-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="58832-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="58832-127">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="58832-127">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="58832-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="58832-128">Remarks</span></span>

<span data-ttu-id="58832-129">この要素を使用すると、不適切なプラットフォーム呼び出し宣言に対して実行時の回復性を高めるために、高速な相互運用マーシャリングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="58832-129">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>

<span data-ttu-id="58832-130">.NET Framework 4 以降では、合理化された相互運用マーシャリングアーキテクチャにより、マネージコードからアンマネージコードへの遷移で大幅なパフォーマンスが向上しています。</span><span class="sxs-lookup"><span data-stu-id="58832-130">Starting with the .NET Framework 4, a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="58832-131">以前のバージョンの .NET Framework では、マーシャリング層が32ビットプラットフォームで正しくないプラットフォーム呼び出し宣言を検出し、自動的にスタックを修正しました。</span><span class="sxs-lookup"><span data-stu-id="58832-131">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="58832-132">新しいマーシャリングアーキテクチャでは、この手順は不要です。</span><span class="sxs-lookup"><span data-stu-id="58832-132">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="58832-133">その結果、遷移は非常に高速になりますが、不適切なプラットフォーム呼び出しの宣言によってプログラムエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="58832-133">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>

<span data-ttu-id="58832-134">開発中に不適切な宣言を簡単に検出できるように、Visual Studio のデバッグエクスペリエンスが改善されました。</span><span class="sxs-lookup"><span data-stu-id="58832-134">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="58832-135">デバッガーがアタッチされた状態でアプリケーションを実行すると、 [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md) managed デバッグアシスタント (MDA) によって、不適切なプラットフォーム呼び出し宣言が通知されます。</span><span class="sxs-lookup"><span data-stu-id="58832-135">The [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>

<span data-ttu-id="58832-136">再コンパイルできないコンポーネントをアプリケーションで使用していて、無効なプラットフォーム呼び出し宣言を持つシナリオに対処する`NetFx40_PInvokeStackResilience`には、要素を使用できます。</span><span class="sxs-lookup"><span data-stu-id="58832-136">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="58832-137">この要素をアプリケーション構成ファイル`enabled="1"`に追加するには、以前のバージョンの .NET Framework の動作で互換性モードを使用します。これにより、移行速度が低下します。</span><span class="sxs-lookup"><span data-stu-id="58832-137">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="58832-138">以前のバージョンの .NET Framework に対してコンパイルされたアセンブリは、自動的にこの互換モードに設定され、この要素は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="58832-138">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="58832-139">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="58832-139">Configuration File</span></span>

<span data-ttu-id="58832-140">この要素は、アプリケーション構成ファイルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="58832-140">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="58832-141">例</span><span class="sxs-lookup"><span data-stu-id="58832-141">Example</span></span>

<span data-ttu-id="58832-142">次の例では、マネージコードとアンマネージコードの間の遷移が低速であるため、アプリケーションの不適切なプラットフォーム呼び出し宣言に対して高度な復元を選択する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="58832-142">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_PInvokeStackResilience enabled="1"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="58832-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="58832-143">See also</span></span>

- [<span data-ttu-id="58832-144">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="58832-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="58832-145">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="58832-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="58832-146">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="58832-146">pInvokeStackImbalance</span></span>](../../../debug-trace-profile/pinvokestackimbalance-mda.md)
