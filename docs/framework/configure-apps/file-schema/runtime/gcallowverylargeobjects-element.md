---
title: <gcAllowVeryLargeObjects> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: 8b2f39a0867228474afdee788474fda11f14ca82
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154128"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="a2ec7-102">\<gcAllowVeryLargeObjects> 要素</span><span class="sxs-lookup"><span data-stu-id="a2ec7-102">\<gcAllowVeryLargeObjects> Element</span></span>
<span data-ttu-id="a2ec7-103">64 ビット プラットフォームで、合計サイズが 2 GB (ギガバイト) を超える配列を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a2ec7-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**  
  
## <a name="syntax"></a><span data-ttu-id="a2ec7-104">構文</span><span class="sxs-lookup"><span data-stu-id="a2ec7-104">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2ec7-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a2ec7-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a2ec7-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2ec7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2ec7-107">属性</span><span class="sxs-lookup"><span data-stu-id="a2ec7-107">Attributes</span></span>  
  
|<span data-ttu-id="a2ec7-108">属性</span><span class="sxs-lookup"><span data-stu-id="a2ec7-108">Attribute</span></span>|<span data-ttu-id="a2ec7-109">説明</span><span class="sxs-lookup"><span data-stu-id="a2ec7-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a2ec7-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="a2ec7-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="a2ec7-111">64 ビット プラットフォームで、合計サイズが 2 GB (ギガバイト) を超える配列が有効であるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2ec7-111">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a2ec7-112">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="a2ec7-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="a2ec7-113">値</span><span class="sxs-lookup"><span data-stu-id="a2ec7-113">Value</span></span>|<span data-ttu-id="a2ec7-114">Description</span><span class="sxs-lookup"><span data-stu-id="a2ec7-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="a2ec7-115">合計サイズが 2 GB を超える配列は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="a2ec7-115">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="a2ec7-116">既定値です。</span><span class="sxs-lookup"><span data-stu-id="a2ec7-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="a2ec7-117">64 ビット プラットフォームで、合計サイズが 2 GB を超える配列が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="a2ec7-117">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2ec7-118">子要素</span><span class="sxs-lookup"><span data-stu-id="a2ec7-118">Child Elements</span></span>  
 <span data-ttu-id="a2ec7-119">なし。</span><span class="sxs-lookup"><span data-stu-id="a2ec7-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a2ec7-120">親要素</span><span class="sxs-lookup"><span data-stu-id="a2ec7-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a2ec7-121">要素</span><span class="sxs-lookup"><span data-stu-id="a2ec7-121">Element</span></span>|<span data-ttu-id="a2ec7-122">Description</span><span class="sxs-lookup"><span data-stu-id="a2ec7-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a2ec7-123">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="a2ec7-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a2ec7-124">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="a2ec7-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2ec7-125">解説</span><span class="sxs-lookup"><span data-stu-id="a2ec7-125">Remarks</span></span>  
 <span data-ttu-id="a2ec7-126">アプリケーション構成ファイルで次の要素を使用すると 2 GB を超えるサイズの配列が有効になりますが、オブジェクトのサイズや配列のサイズに対するその他の制限は変更されません。</span><span class="sxs-lookup"><span data-stu-id="a2ec7-126">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="a2ec7-127">配列の要素の最大数は <xref:System.UInt32.MaxValue?displayProperty=nameWithType> です。</span><span class="sxs-lookup"><span data-stu-id="a2ec7-127">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="a2ec7-128">バイト配列および 1 バイト構造体の配列の場合、単一次元の最大インデックスは 2,147,483,591 (0x7FFFFFC7) です。その他の種類の場合は 2,146,435,071 (0X7FEFFFFF) です。</span><span class="sxs-lookup"><span data-stu-id="a2ec7-128">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
- <span data-ttu-id="a2ec7-129">文字列およびその他の非配列オブジェクトの最大サイズは変更されません。</span><span class="sxs-lookup"><span data-stu-id="a2ec7-129">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="a2ec7-130">この機能を有効にする前に、すべての配列のサイズが 2 GB よりも小さいことを前提としたアンセーフ コードがアプリケーションに含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a2ec7-130">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="a2ec7-131">たとえば、バッファーとして配列を使用するアンセーフ コードが、配列は 2 GB を超えないという前提で記述されている場合、バッファー オーバーランが発生しやすくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2ec7-131">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2ec7-132">例</span><span class="sxs-lookup"><span data-stu-id="a2ec7-132">Example</span></span>  
 <span data-ttu-id="a2ec7-133">アプリケーションでこの機能を有効にする方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="a2ec7-133">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="a2ec7-134">サポート対象 :</span><span class="sxs-lookup"><span data-stu-id="a2ec7-134">Supported in</span></span>

<span data-ttu-id="a2ec7-135">.NET Framework 4.5 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="a2ec7-135">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="a2ec7-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2ec7-136">See also</span></span>

- [<span data-ttu-id="a2ec7-137">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="a2ec7-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a2ec7-138">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="a2ec7-138">Configuration File Schema</span></span>](../index.md)
