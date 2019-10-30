---
title: <gcAllowVeryLargeObjects> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: b6230833808ec45d702502e36f929db4e03173e1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116798"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="7a80d-102">\<gcAllowVeryLargeObjects > 要素</span><span class="sxs-lookup"><span data-stu-id="7a80d-102">\<gcAllowVeryLargeObjects> Element</span></span>
<span data-ttu-id="7a80d-103">64 ビット プラットフォームで、合計サイズが 2 GB (ギガバイト) を超える配列を有効にします。</span><span class="sxs-lookup"><span data-stu-id="7a80d-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
<span data-ttu-id="7a80d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7a80d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7a80d-105">&nbsp;&nbsp;[ **\<runtime>** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="7a80d-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="7a80d-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<gcAllowVeryLargeObjects >**</span><span class="sxs-lookup"><span data-stu-id="7a80d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a80d-107">構文</span><span class="sxs-lookup"><span data-stu-id="7a80d-107">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a80d-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7a80d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7a80d-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a80d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a80d-110">属性</span><span class="sxs-lookup"><span data-stu-id="7a80d-110">Attributes</span></span>  
  
|<span data-ttu-id="7a80d-111">属性</span><span class="sxs-lookup"><span data-stu-id="7a80d-111">Attribute</span></span>|<span data-ttu-id="7a80d-112">説明</span><span class="sxs-lookup"><span data-stu-id="7a80d-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="7a80d-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="7a80d-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="7a80d-114">64 ビット プラットフォームで、合計サイズが 2 GB (ギガバイト) を超える配列が有効であるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="7a80d-114">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="7a80d-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="7a80d-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="7a80d-116">[値]</span><span class="sxs-lookup"><span data-stu-id="7a80d-116">Value</span></span>|<span data-ttu-id="7a80d-117">説明</span><span class="sxs-lookup"><span data-stu-id="7a80d-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="7a80d-118">合計サイズが 2 GB を超える配列は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="7a80d-118">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="7a80d-119">既定値です。</span><span class="sxs-lookup"><span data-stu-id="7a80d-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="7a80d-120">64 ビット プラットフォームで、合計サイズが 2 GB を超える配列が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="7a80d-120">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7a80d-121">子要素</span><span class="sxs-lookup"><span data-stu-id="7a80d-121">Child Elements</span></span>  
 <span data-ttu-id="7a80d-122">なし。</span><span class="sxs-lookup"><span data-stu-id="7a80d-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7a80d-123">親要素</span><span class="sxs-lookup"><span data-stu-id="7a80d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7a80d-124">要素</span><span class="sxs-lookup"><span data-stu-id="7a80d-124">Element</span></span>|<span data-ttu-id="7a80d-125">説明</span><span class="sxs-lookup"><span data-stu-id="7a80d-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7a80d-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="7a80d-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7a80d-127">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="7a80d-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a80d-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="7a80d-128">Remarks</span></span>  
 <span data-ttu-id="7a80d-129">アプリケーション構成ファイルで次の要素を使用すると 2 GB を超えるサイズの配列が有効になりますが、オブジェクトのサイズや配列のサイズに対するその他の制限は変更されません。</span><span class="sxs-lookup"><span data-stu-id="7a80d-129">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="7a80d-130">配列の要素の最大数は <xref:System.UInt32.MaxValue?displayProperty=nameWithType> です。</span><span class="sxs-lookup"><span data-stu-id="7a80d-130">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="7a80d-131">バイト配列および 1 バイト構造体の配列の場合、単一次元の最大インデックスは 2,147,483,591 (0x7FFFFFC7) です。その他の種類の場合は 2,146,435,071 (0X7FEFFFFF) です。</span><span class="sxs-lookup"><span data-stu-id="7a80d-131">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
- <span data-ttu-id="7a80d-132">文字列およびその他の非配列オブジェクトの最大サイズは変更されません。</span><span class="sxs-lookup"><span data-stu-id="7a80d-132">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="7a80d-133">この機能を有効にする前に、すべての配列のサイズが 2 GB よりも小さいことを前提としたアンセーフ コードがアプリケーションに含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7a80d-133">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="7a80d-134">たとえば、バッファーとして配列を使用するアンセーフ コードが、配列は 2 GB を超えないという前提で記述されている場合、バッファー オーバーランが発生しやすくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7a80d-134">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a80d-135">例</span><span class="sxs-lookup"><span data-stu-id="7a80d-135">Example</span></span>  
 <span data-ttu-id="7a80d-136">アプリケーションでこの機能を有効にする方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="7a80d-136">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="7a80d-137">サポート対象 :</span><span class="sxs-lookup"><span data-stu-id="7a80d-137">Supported in</span></span>

<span data-ttu-id="7a80d-138">.NET Framework 4.5 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="7a80d-138">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="7a80d-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a80d-139">See also</span></span>

- [<span data-ttu-id="7a80d-140">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="7a80d-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7a80d-141">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="7a80d-141">Configuration File Schema</span></span>](../index.md)
