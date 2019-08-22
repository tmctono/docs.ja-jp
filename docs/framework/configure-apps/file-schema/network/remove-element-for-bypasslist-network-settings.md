---
title: bypasslist の <remove> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- <bypasslist>, remove element
- remove element, bypasslist
- bypasslist, remove element
- remove element, bypasslist
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
ms.openlocfilehash: 0fd8de9af00aa861d92c8c201ef89545e108c790
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659240"
---
# <a name="remove-element-for-bypasslist-network-settings"></a><span data-ttu-id="729ad-102">\<bypasslist の > 要素の削除 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="729ad-102">\<remove> Element for bypasslist (Network Settings)</span></span>

<span data-ttu-id="729ad-103">プロキシバイパスリストから IP アドレスまたは DNS 名を削除します。</span><span class="sxs-lookup"><span data-stu-id="729ad-103">Removes an IP address or DNS name from the proxy bypass list.</span></span>

<span data-ttu-id="729ad-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="729ad-104">\<configuration>\</span></span>
<span data-ttu-id="729ad-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="729ad-105">\<system.net></span></span>\
<span data-ttu-id="729ad-106">\<defaultProxy > </span><span class="sxs-lookup"><span data-stu-id="729ad-106">\<defaultProxy></span></span>\
<span data-ttu-id="729ad-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="729ad-107">\<bypasslist></span></span>\
<span data-ttu-id="729ad-108">\<remove></span><span class="sxs-lookup"><span data-stu-id="729ad-108">\<remove></span></span>

## <a name="syntax"></a><span data-ttu-id="729ad-109">構文</span><span class="sxs-lookup"><span data-stu-id="729ad-109">Syntax</span></span>

```xml
<remove
  address="regular expression"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="729ad-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="729ad-110">Attributes and Elements</span></span>

<span data-ttu-id="729ad-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="729ad-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="729ad-112">属性</span><span class="sxs-lookup"><span data-stu-id="729ad-112">Attributes</span></span>

|<span data-ttu-id="729ad-113">**属性**</span><span class="sxs-lookup"><span data-stu-id="729ad-113">**Attribute**</span></span>|<span data-ttu-id="729ad-114">**説明**</span><span class="sxs-lookup"><span data-stu-id="729ad-114">**Description**</span></span>|
|-------------------|---------------------|
|`address`|<span data-ttu-id="729ad-115">IP アドレスまたは DNS 名を記述する正規表現。</span><span class="sxs-lookup"><span data-stu-id="729ad-115">A regular expression describing an IP address or DNS name.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="729ad-116">子要素</span><span class="sxs-lookup"><span data-stu-id="729ad-116">Child Elements</span></span>

<span data-ttu-id="729ad-117">なし。</span><span class="sxs-lookup"><span data-stu-id="729ad-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="729ad-118">親要素</span><span class="sxs-lookup"><span data-stu-id="729ad-118">Parent Elements</span></span>

|<span data-ttu-id="729ad-119">**要素**</span><span class="sxs-lookup"><span data-stu-id="729ad-119">**Element**</span></span>|<span data-ttu-id="729ad-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="729ad-120">**Description**</span></span>|
|-----------------|---------------------|
|[<span data-ttu-id="729ad-121">bypasslist</span><span class="sxs-lookup"><span data-stu-id="729ad-121">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="729ad-122">プロキシを使用しないアドレスを記述する一連の正規表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="729ad-122">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|

## <a name="remarks"></a><span data-ttu-id="729ad-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="729ad-123">Remarks</span></span>

<span data-ttu-id="729ad-124">要素`remove`は、プロキシサーバーをバイパスするアドレスの一覧から、IP アドレスまたは DNS サーバー名を記述する正規表現を削除します。</span><span class="sxs-lookup"><span data-stu-id="729ad-124">The `remove` element removes regular expressions describing IP addresses or DNS server names from the list of addresses that bypass a proxy server.</span></span> <span data-ttu-id="729ad-125">これらのアドレスは、構成ファイルで既に定義されているか、構成階層の上位レベルに定義されています。</span><span class="sxs-lookup"><span data-stu-id="729ad-125">The addresses were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>

<span data-ttu-id="729ad-126">`address`属性の値は、一連の IP アドレスまたはホスト名を表す正規表現である必要があります。</span><span class="sxs-lookup"><span data-stu-id="729ad-126">The value for the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>

<span data-ttu-id="729ad-127">正規表現の詳細については、「」を参照してください。[正規表現を .NET Framework](../../../../../docs/standard/base-types/regular-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="729ad-127">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>

## <a name="configuration-files"></a><span data-ttu-id="729ad-128">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="729ad-128">Configuration Files</span></span>

<span data-ttu-id="729ad-129">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="729ad-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>

## <a name="example"></a><span data-ttu-id="729ad-130">例</span><span class="sxs-lookup"><span data-stu-id="729ad-130">Example</span></span>

<span data-ttu-id="729ad-131">次の例では、adventure-works.com ドメインの以前の定義を削除し、contoso.com ドメインをバイパスリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="729ad-131">The following example removes any previous definition for the adventure-works.com domain, and then adds the contoso.com domain to the bypass list.</span></span>

```xml
<configuration>
  <system.net>
    <defaultProxy>
      <bypasslist>
        <remove address="[a-z]+\.adventure-works\.com$" />
        <add address="[a-z]+\.contoso\.com$" />
      </bypasslist>
    </defaultProxy>
  </system.net>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="729ad-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="729ad-132">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="729ad-133">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="729ad-133">Network Settings Schema</span></span>](index.md)
