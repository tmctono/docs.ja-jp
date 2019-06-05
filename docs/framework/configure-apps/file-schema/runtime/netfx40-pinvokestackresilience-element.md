---
title: <NetFx40_PInvokeStackResilience> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 318473d2913d62404c58b9d3681800ae22a9ecbf
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689851"
---
# <a name="netfx40pinvokestackresilience-element"></a><span data-ttu-id="90e6b-102">\<NetFx40_PInvokeStackResilience > 要素</span><span class="sxs-lookup"><span data-stu-id="90e6b-102">\<NetFx40_PInvokeStackResilience> Element</span></span>

<span data-ttu-id="90e6b-103">ランタイムが実行時の不適切なプラットフォーム呼び出し宣言を自動的に修正するかどうかを指定します。これにより、マネージド コードとアンマネージド コード間の遷移が遅くなります。</span><span class="sxs-lookup"><span data-stu-id="90e6b-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>

<span data-ttu-id="90e6b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="90e6b-104">\<configuration>\\</span></span>
<span data-ttu-id="90e6b-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="90e6b-105">\<runtime>\\</span></span>
<span data-ttu-id="90e6b-106">\<NetFx40_PInvokeStackResilience></span><span class="sxs-lookup"><span data-stu-id="90e6b-106">\<NetFx40_PInvokeStackResilience></span></span>

## <a name="syntax"></a><span data-ttu-id="90e6b-107">構文</span><span class="sxs-lookup"><span data-stu-id="90e6b-107">Syntax</span></span>

```xml
<NetFx40_PInvokeStackResilience  enabled="1|0"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="90e6b-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="90e6b-108">Attributes and Elements</span></span>

<span data-ttu-id="90e6b-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="90e6b-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="90e6b-110">属性</span><span class="sxs-lookup"><span data-stu-id="90e6b-110">Attributes</span></span>

|<span data-ttu-id="90e6b-111">属性</span><span class="sxs-lookup"><span data-stu-id="90e6b-111">Attribute</span></span>|<span data-ttu-id="90e6b-112">説明</span><span class="sxs-lookup"><span data-stu-id="90e6b-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="90e6b-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="90e6b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="90e6b-114">ランタイムは不適切なプラットフォームを検出するかどうかを指定します。 宣言を呼び出すと、スタックを 32 ビット プラットフォーム上で実行時に自動的に修正します。</span><span class="sxs-lookup"><span data-stu-id="90e6b-114">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="90e6b-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="90e6b-115">enabled Attribute</span></span>

|<span data-ttu-id="90e6b-116">値</span><span class="sxs-lookup"><span data-stu-id="90e6b-116">Value</span></span>|<span data-ttu-id="90e6b-117">説明</span><span class="sxs-lookup"><span data-stu-id="90e6b-117">Description</span></span>|
|-----------|-----------------|
|`0`|<span data-ttu-id="90e6b-118">ランタイムが高速な相互運用が検出されない、.NET Framework 4 で導入されたアーキテクチャをマーシャ リングを使用し、修正プログラムの不適切なプラットフォーム呼び出し宣言します。</span><span class="sxs-lookup"><span data-stu-id="90e6b-118">The runtime uses the faster interop marshaling architecture introduced in the .NET Framework 4, which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="90e6b-119">既定値です。</span><span class="sxs-lookup"><span data-stu-id="90e6b-119">This is the default.</span></span>|
|`1`|<span data-ttu-id="90e6b-120">不適切なプラットフォームを検出してランタイムは低速遷移は呼び出しの宣言です。</span><span class="sxs-lookup"><span data-stu-id="90e6b-120">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="90e6b-121">子要素</span><span class="sxs-lookup"><span data-stu-id="90e6b-121">Child Elements</span></span>

<span data-ttu-id="90e6b-122">なし。</span><span class="sxs-lookup"><span data-stu-id="90e6b-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="90e6b-123">親要素</span><span class="sxs-lookup"><span data-stu-id="90e6b-123">Parent Elements</span></span>

|<span data-ttu-id="90e6b-124">要素</span><span class="sxs-lookup"><span data-stu-id="90e6b-124">Element</span></span>|<span data-ttu-id="90e6b-125">説明</span><span class="sxs-lookup"><span data-stu-id="90e6b-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="90e6b-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="90e6b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="90e6b-127">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="90e6b-127">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="90e6b-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="90e6b-128">Remarks</span></span>

<span data-ttu-id="90e6b-129">この要素では、高速な相互運用マーシャ リングの実行時の回復性に対して不適切なプラットフォーム呼び出し宣言を犠牲にすることができます。</span><span class="sxs-lookup"><span data-stu-id="90e6b-129">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>

<span data-ttu-id="90e6b-130">以降、.NET Framework 4 では、合理化された相互運用マーシャ リング アーキテクチャは、マネージ コードからアンマネージ コードに遷移の大幅なパフォーマンス向上を提供します。</span><span class="sxs-lookup"><span data-stu-id="90e6b-130">Starting with the .NET Framework 4, a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="90e6b-131">.NET Framework の以前のバージョンでは、マーシャ リング検出レイヤーの不適切なプラットフォームが 32 ビット プラットフォーム上で宣言を起動し、スタックを自動的に固定します。</span><span class="sxs-lookup"><span data-stu-id="90e6b-131">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="90e6b-132">新しいマーシャ リング アーキテクチャは、この手順を排除します。</span><span class="sxs-lookup"><span data-stu-id="90e6b-132">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="90e6b-133">その結果、遷移は非常に高速が不適切なプラットフォーム呼び出し宣言プログラム エラーが発生することができます。</span><span class="sxs-lookup"><span data-stu-id="90e6b-133">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>

<span data-ttu-id="90e6b-134">開発中に正しくない宣言を検出するためにを Visual Studio のデバッグ エクスペリエンスが改善されました。</span><span class="sxs-lookup"><span data-stu-id="90e6b-134">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="90e6b-135">[PInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)マネージ デバッグ アシスタント (MDA) は、アタッチされたデバッガーでアプリケーションを実行しているときに、宣言を呼び出すの不適切なプラットフォームに通知します。</span><span class="sxs-lookup"><span data-stu-id="90e6b-135">The [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>

<span data-ttu-id="90e6b-136">アプリケーションが再コンパイルすることはできませんを使用できます、不適切なプラットフォームは宣言を呼び出すが、コンポーネントを使用してシナリオに対処する、`NetFx40_PInvokeStackResilience`要素。</span><span class="sxs-lookup"><span data-stu-id="90e6b-136">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="90e6b-137">この要素を追加すると、アプリケーション構成ファイルを`enabled="1"`遷移が遅くなりますが、.NET Framework の以前のバージョンの動作との互換モードを選択します。</span><span class="sxs-lookup"><span data-stu-id="90e6b-137">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="90e6b-138">.NET Framework の以前のバージョンに対してコンパイルされたアセンブリでは、この互換モードが自動的に選択されるためし、この要素は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="90e6b-138">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="90e6b-139">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="90e6b-139">Configuration File</span></span>

<span data-ttu-id="90e6b-140">この要素は、アプリケーション構成ファイルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="90e6b-140">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="90e6b-141">例</span><span class="sxs-lookup"><span data-stu-id="90e6b-141">Example</span></span>

<span data-ttu-id="90e6b-142">次の例はプラットフォーム呼び出しの間の遷移が遅くなりますが、アプリケーションの宣言が正しくないに対する回復を強化を有効にする方法は、管理され、アンマネージ コード。</span><span class="sxs-lookup"><span data-stu-id="90e6b-142">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_PInvokeStackResilience enabled="1"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="90e6b-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="90e6b-143">See also</span></span>

- [<span data-ttu-id="90e6b-144">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="90e6b-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="90e6b-145">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="90e6b-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="90e6b-146">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="90e6b-146">pInvokeStackImbalance</span></span>](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)
