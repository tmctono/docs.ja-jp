---
title: <bindings>
ms.date: 01/22/2018
ms.assetid: b62cd369-5409-4030-8490-9759a462dd3a
ms.openlocfilehash: fe8f620668e35183890b8bba1f254a74c962f8d3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139662"
---
# \<bindings>

<span data-ttu-id="bb92b-101">要素を使用して、 `bindings` Windows Communication Foundation (WCF) の標準バインディングとカスタムバインディングのコレクションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="bb92b-101">You can use the `bindings` element to configure a collection of standard and custom bindings for Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="bb92b-102">各エントリは、その一意の `binding` 属性で識別できる `name` 要素です。</span><span class="sxs-lookup"><span data-stu-id="bb92b-102">Each entry is a `binding` element that can be identified by its unique `name`.</span></span> <span data-ttu-id="bb92b-103">サービスは、`name` を使用してバインディングをリンクすることにより、バインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="bb92b-103">Services use bindings by linking them using the `name`.</span></span> <span data-ttu-id="bb92b-104">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bb92b-104">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="bb92b-105">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb92b-105">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>

## <a name="system-provided-bindings"></a><span data-ttu-id="bb92b-106">システム指定のバインド</span><span class="sxs-lookup"><span data-stu-id="bb92b-106">System-provided bindings</span></span>

<span data-ttu-id="bb92b-107">システム指定のバインディングは、WCF メッセージ スタックの複雑さを隠蔽します。</span><span class="sxs-lookup"><span data-stu-id="bb92b-107">System-provided bindings hide the complexity of the WCF messaging stack.</span></span> <span data-ttu-id="bb92b-108">システム指定のバインディングを使用しているアプリケーションは、スタックを完全に制御する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bb92b-108">Applications using system-provided bindings do not require full control over the stack.</span></span> <span data-ttu-id="bb92b-109">システム指定の各バインディングに公開される属性は、バインディングが処理する使用シナリオに最適な属性です。</span><span class="sxs-lookup"><span data-stu-id="bb92b-109">The attributes exposed on each system-provided binding are the ones most appropriate for the usage scenario the binding addresses.</span></span>

<span data-ttu-id="bb92b-110">システム指定の各バインディングの構成セクションは、バインディングの構成に使用される複数の構成を定義できます。</span><span class="sxs-lookup"><span data-stu-id="bb92b-110">The configuration section for each system-provided binding can define several configurations used to configure the binding.</span></span> <span data-ttu-id="bb92b-111">各構成は、一意の名前によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="bb92b-111">Each configuration is identified by a unique name.</span></span>

<span data-ttu-id="bb92b-112">システム指定のバインディングに要素または属性を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="bb92b-112">It isn't possible to add elements or attributes to a system-provided binding.</span></span> <span data-ttu-id="bb92b-113">これを行うには、「[カスタムバインド](#custom-bindings)」セクションの説明に従って、カスタムバインディングを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb92b-113">To do so, you should implement a custom binding as described in the [Custom bindings](#custom-bindings) section.</span></span> <span data-ttu-id="bb92b-114">システム指定のバインディングを完全に模倣し、ユーザーアプリケーションが制御する必要がある設定をいくつか追加するカスタムバインディングを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="bb92b-114">It's possible to define a custom binding that mimics a system-provided binding perfectly and adds a few settings the user application wants to have control over.</span></span>  

<span data-ttu-id="bb92b-115">システム指定のバインディングの一覧については、「[システム指定のバインディング](../../../wcf/system-provided-bindings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb92b-115">For a list of system-provided bindings, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>

## <a name="custom-bindings"></a><span data-ttu-id="bb92b-116">カスタムバインド</span><span class="sxs-lookup"><span data-stu-id="bb92b-116">Custom bindings</span></span>

<span data-ttu-id="bb92b-117">カスタム バインディングを使用すると、WCF メッセージ スタックのフル コントロールが可能になります。</span><span class="sxs-lookup"><span data-stu-id="bb92b-117">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="bb92b-118">個別のバインディングは、メッセージ スタックを、スタック要素の構成要素をスタックに出現する順序で指定することにより定義します。</span><span class="sxs-lookup"><span data-stu-id="bb92b-118">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="bb92b-119">各要素は、スタックの1つの要素を定義して構成します。</span><span class="sxs-lookup"><span data-stu-id="bb92b-119">Each element defines and configures one element of the stack.</span></span> <span data-ttu-id="bb92b-120">各カスタム バインディング内の `transport` 要素は 1 つだけにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb92b-120">There must be one and only one `transport` element in each custom binding.</span></span> <span data-ttu-id="bb92b-121">この要素がない場合、メッセージ スタックは不完全です。</span><span class="sxs-lookup"><span data-stu-id="bb92b-121">Without this element, the messaging stack is incomplete.</span></span>

<span data-ttu-id="bb92b-122">要素がスタックに出現する順序は重要です。それは、その順序で操作がメッセージに適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="bb92b-122">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="bb92b-123">スタック要素で必要な順序を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bb92b-123">The required order of stack elements is the following:</span></span>  

1. <span data-ttu-id="bb92b-124">トランザクション (省略可能)</span><span class="sxs-lookup"><span data-stu-id="bb92b-124">Transactions (optional)</span></span>  

2. <span data-ttu-id="bb92b-125">信頼できるメッセージング (オプション)</span><span class="sxs-lookup"><span data-stu-id="bb92b-125">Reliable messaging (optional)</span></span>  

3. <span data-ttu-id="bb92b-126">セキュリティ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="bb92b-126">Security (optional)</span></span>  

4. <span data-ttu-id="bb92b-127">エンコーダー</span><span class="sxs-lookup"><span data-stu-id="bb92b-127">Encoder</span></span>  

5. <span data-ttu-id="bb92b-128">トランスポート</span><span class="sxs-lookup"><span data-stu-id="bb92b-128">Transport</span></span>  

 <span data-ttu-id="bb92b-129">カスタム バインドは、`name` 属性によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="bb92b-129">Custom bindings are identified by their `name` attribute.</span></span> <span data-ttu-id="bb92b-130">カスタムバインディングの詳細については、「[カスタムバインド](../../../wcf/extending/custom-bindings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb92b-130">For more information on custom bindings, see [Custom Bindings](../../../wcf/extending/custom-bindings.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bb92b-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb92b-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.BindingsSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.Binding?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>
- [<span data-ttu-id="bb92b-132">バインド</span><span class="sxs-lookup"><span data-stu-id="bb92b-132">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="bb92b-133">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="bb92b-133">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
