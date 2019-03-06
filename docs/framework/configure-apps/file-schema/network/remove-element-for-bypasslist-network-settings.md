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
ms.openlocfilehash: a04cca3e57af5cc422776c5b2444a140e86f98b9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354259"
---
# <a name="remove-element-for-bypasslist-network-settings"></a><span data-ttu-id="0cb72-102">\<削除 > bypasslist (ネットワーク設定) の要素</span><span class="sxs-lookup"><span data-stu-id="0cb72-102">\<remove> Element for bypasslist (Network Settings)</span></span>

<span data-ttu-id="0cb72-103">プロキシ バイ パスの一覧から IP アドレスまたは DNS 名を削除します。</span><span class="sxs-lookup"><span data-stu-id="0cb72-103">Removes an IP address or DNS name from the proxy bypass list.</span></span>

<span data-ttu-id="0cb72-104">\<configuration>\\</span><span class="sxs-lookup"><span data-stu-id="0cb72-104">\<configuration>\\</span></span>
<span data-ttu-id="0cb72-105">\<system.net>\\</span><span class="sxs-lookup"><span data-stu-id="0cb72-105">\<system.net>\\</span></span>
<span data-ttu-id="0cb72-106">\<defaultProxy>\\</span><span class="sxs-lookup"><span data-stu-id="0cb72-106">\<defaultProxy>\\</span></span>
<span data-ttu-id="0cb72-107">\<bypasslist>\\</span><span class="sxs-lookup"><span data-stu-id="0cb72-107">\<bypasslist>\\</span></span>
<span data-ttu-id="0cb72-108">\<remove></span><span class="sxs-lookup"><span data-stu-id="0cb72-108">\<remove></span></span>

## <a name="syntax"></a><span data-ttu-id="0cb72-109">構文</span><span class="sxs-lookup"><span data-stu-id="0cb72-109">Syntax</span></span>

```xml
<remove
  address="regular expression"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0cb72-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0cb72-110">Attributes and Elements</span></span>

<span data-ttu-id="0cb72-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0cb72-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0cb72-112">属性</span><span class="sxs-lookup"><span data-stu-id="0cb72-112">Attributes</span></span>

|<span data-ttu-id="0cb72-113">**属性**</span><span class="sxs-lookup"><span data-stu-id="0cb72-113">**Attribute**</span></span>|<span data-ttu-id="0cb72-114">**説明**</span><span class="sxs-lookup"><span data-stu-id="0cb72-114">**Description**</span></span>|
|-------------------|---------------------|
|`address`|<span data-ttu-id="0cb72-115">IP アドレスまたは DNS 名を記述する正規表現。</span><span class="sxs-lookup"><span data-stu-id="0cb72-115">A regular expression describing an IP address or DNS name.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="0cb72-116">子要素</span><span class="sxs-lookup"><span data-stu-id="0cb72-116">Child Elements</span></span>

<span data-ttu-id="0cb72-117">なし。</span><span class="sxs-lookup"><span data-stu-id="0cb72-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0cb72-118">親要素</span><span class="sxs-lookup"><span data-stu-id="0cb72-118">Parent Elements</span></span>

|<span data-ttu-id="0cb72-119">**要素**</span><span class="sxs-lookup"><span data-stu-id="0cb72-119">**Element**</span></span>|<span data-ttu-id="0cb72-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="0cb72-120">**Description**</span></span>|
|-----------------|---------------------|
|[<span data-ttu-id="0cb72-121">bypasslist</span><span class="sxs-lookup"><span data-stu-id="0cb72-121">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="0cb72-122">一連のプロキシを使用しないアドレスを記述する正規表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="0cb72-122">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0cb72-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="0cb72-123">Remarks</span></span>

<span data-ttu-id="0cb72-124">`remove`要素は、IP アドレスまたはプロキシ サーバーをバイパスするアドレスのリストから DNS サーバー名を記述する正規表現を削除します。</span><span class="sxs-lookup"><span data-stu-id="0cb72-124">The `remove` element removes regular expressions describing IP addresses or DNS server names from the list of addresses that bypass a proxy server.</span></span> <span data-ttu-id="0cb72-125">アドレスは、構成ファイルで、または構成階層のより高いレベルで既に定義されてです。</span><span class="sxs-lookup"><span data-stu-id="0cb72-125">The addresses were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>

<span data-ttu-id="0cb72-126">値、`address`属性は、一連の IP アドレスまたはホスト名を記述する正規表現をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cb72-126">The value for the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>

<span data-ttu-id="0cb72-127">正規表現の詳細についてを参照してください。[.NET framework の正規表現](../../../../../docs/standard/base-types/regular-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="0cb72-127">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>

## <a name="configuration-files"></a><span data-ttu-id="0cb72-128">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="0cb72-128">Configuration Files</span></span>

<span data-ttu-id="0cb72-129">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="0cb72-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>

## <a name="example"></a><span data-ttu-id="0cb72-130">例</span><span class="sxs-lookup"><span data-stu-id="0cb72-130">Example</span></span>

<span data-ttu-id="0cb72-131">次の例では、adventure-works.com のドメインの以前の定義を削除し、バイパス リストに contoso.com ドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="0cb72-131">The following example removes any previous definition for the adventure-works.com domain, and then adds the contoso.com domain to the bypass list.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="0cb72-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="0cb72-132">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="0cb72-133">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="0cb72-133">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
