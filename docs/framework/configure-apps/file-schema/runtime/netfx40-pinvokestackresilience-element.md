---
title: <NetFx40_PInvokeStackResilience> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
ms.openlocfilehash: 86f50aafe0b21d5080288e09ac7118ca1e4c939a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73116158"
---
# <a name="netfx40_pinvokestackresilience-element"></a><span data-ttu-id="446da-102">\<NetFx40_PInvokeStackResilience> 要素</span><span class="sxs-lookup"><span data-stu-id="446da-102">\<NetFx40_PInvokeStackResilience> Element</span></span>

<span data-ttu-id="446da-103">ランタイムが実行時の不適切なプラットフォーム呼び出し宣言を自動的に修正するかどうかを指定します。これにより、マネージド コードとアンマネージド コード間の遷移が遅くなります。</span><span class="sxs-lookup"><span data-stu-id="446da-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_PInvokeStackResilience>**  

## <a name="syntax"></a><span data-ttu-id="446da-104">構文</span><span class="sxs-lookup"><span data-stu-id="446da-104">Syntax</span></span>

```xml
<NetFx40_PInvokeStackResilience  enabled="1|0"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="446da-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="446da-105">Attributes and Elements</span></span>

<span data-ttu-id="446da-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="446da-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="446da-107">属性</span><span class="sxs-lookup"><span data-stu-id="446da-107">Attributes</span></span>

|<span data-ttu-id="446da-108">属性</span><span class="sxs-lookup"><span data-stu-id="446da-108">Attribute</span></span>|<span data-ttu-id="446da-109">説明</span><span class="sxs-lookup"><span data-stu-id="446da-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="446da-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="446da-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="446da-111">ランタイムが無効なプラットフォーム呼び出し宣言を検出し、実行時に32ビットプラットフォームで自動的にスタックを修正するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="446da-111">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="446da-112">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="446da-112">enabled Attribute</span></span>

|<span data-ttu-id="446da-113">値</span><span class="sxs-lookup"><span data-stu-id="446da-113">Value</span></span>|<span data-ttu-id="446da-114">Description</span><span class="sxs-lookup"><span data-stu-id="446da-114">Description</span></span>|
|-----------|-----------------|
|`0`|<span data-ttu-id="446da-115">ランタイムは、.NET Framework 4 で導入された高速な相互運用マーシャリングアーキテクチャを使用します。これは、不適切なプラットフォーム呼び出し宣言を検出して修正するものではありません。</span><span class="sxs-lookup"><span data-stu-id="446da-115">The runtime uses the faster interop marshaling architecture introduced in the .NET Framework 4, which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="446da-116">既定値です。</span><span class="sxs-lookup"><span data-stu-id="446da-116">This is the default.</span></span>|
|`1`|<span data-ttu-id="446da-117">ランタイムは、不適切なプラットフォーム呼び出し宣言を検出して修正する低速の遷移を使用します。</span><span class="sxs-lookup"><span data-stu-id="446da-117">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="446da-118">子要素</span><span class="sxs-lookup"><span data-stu-id="446da-118">Child Elements</span></span>

<span data-ttu-id="446da-119">なし。</span><span class="sxs-lookup"><span data-stu-id="446da-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="446da-120">親要素</span><span class="sxs-lookup"><span data-stu-id="446da-120">Parent Elements</span></span>

|<span data-ttu-id="446da-121">要素</span><span class="sxs-lookup"><span data-stu-id="446da-121">Element</span></span>|<span data-ttu-id="446da-122">Description</span><span class="sxs-lookup"><span data-stu-id="446da-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="446da-123">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="446da-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="446da-124">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="446da-124">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="446da-125">解説</span><span class="sxs-lookup"><span data-stu-id="446da-125">Remarks</span></span>

<span data-ttu-id="446da-126">この要素を使用すると、不適切なプラットフォーム呼び出し宣言に対して実行時の回復性を高めるために、高速な相互運用マーシャリングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="446da-126">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>

<span data-ttu-id="446da-127">.NET Framework 4 以降では、合理化された相互運用マーシャリングアーキテクチャにより、マネージコードからアンマネージコードへの遷移で大幅なパフォーマンスが向上しています。</span><span class="sxs-lookup"><span data-stu-id="446da-127">Starting with the .NET Framework 4, a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="446da-128">以前のバージョンの .NET Framework では、マーシャリング層が32ビットプラットフォームで正しくないプラットフォーム呼び出し宣言を検出し、自動的にスタックを修正しました。</span><span class="sxs-lookup"><span data-stu-id="446da-128">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="446da-129">新しいマーシャリングアーキテクチャでは、この手順は不要です。</span><span class="sxs-lookup"><span data-stu-id="446da-129">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="446da-130">その結果、遷移は非常に高速になりますが、不適切なプラットフォーム呼び出しの宣言によってプログラムエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="446da-130">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>

<span data-ttu-id="446da-131">開発中に不適切な宣言を簡単に検出できるように、Visual Studio のデバッグエクスペリエンスが改善されました。</span><span class="sxs-lookup"><span data-stu-id="446da-131">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="446da-132">デバッガーがアタッチされた状態でアプリケーションを実行すると、 [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md) managed デバッグアシスタント (MDA) によって、不適切なプラットフォーム呼び出し宣言が通知されます。</span><span class="sxs-lookup"><span data-stu-id="446da-132">The [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>

<span data-ttu-id="446da-133">再コンパイルできないコンポーネントをアプリケーションで使用していて、無効なプラットフォーム呼び出し宣言を持つシナリオに対処するには、要素を使用でき `NetFx40_PInvokeStackResilience` ます。</span><span class="sxs-lookup"><span data-stu-id="446da-133">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="446da-134">この要素をアプリケーション構成ファイルに追加するには、 `enabled="1"` 以前のバージョンの .NET Framework の動作で互換性モードを使用します。これにより、移行速度が低下します。</span><span class="sxs-lookup"><span data-stu-id="446da-134">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="446da-135">以前のバージョンの .NET Framework に対してコンパイルされたアセンブリは、自動的にこの互換モードに設定され、この要素は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="446da-135">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="446da-136">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="446da-136">Configuration File</span></span>

<span data-ttu-id="446da-137">この要素は、アプリケーション構成ファイルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="446da-137">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="446da-138">例</span><span class="sxs-lookup"><span data-stu-id="446da-138">Example</span></span>

<span data-ttu-id="446da-139">次の例では、マネージコードとアンマネージコードの間の遷移が低速であるため、アプリケーションの不適切なプラットフォーム呼び出し宣言に対して高度な復元を選択する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="446da-139">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_PInvokeStackResilience enabled="1"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="446da-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="446da-140">See also</span></span>

- [<span data-ttu-id="446da-141">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="446da-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="446da-142">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="446da-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="446da-143">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="446da-143">pInvokeStackImbalance</span></span>](../../../debug-trace-profile/pinvokestackimbalance-mda.md)
