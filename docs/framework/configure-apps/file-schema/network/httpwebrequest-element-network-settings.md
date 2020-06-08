---
title: <httpWebRequest> 要素 (ネットワーク設定)
description: <httpWebRequest>ネットワーク設定要素は、.NET Framework 内の Web 要求パラメーターをカスタマイズします。
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: 59ab425dcef8ac5283035910a9d78a89a16be8b1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504590"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="893a1-103">\<httpWebRequest> 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="893a1-103">\<httpWebRequest> Element (Network Settings)</span></span>
<span data-ttu-id="893a1-104">Web 要求パラメーターをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="893a1-104">Customizes Web request parameters.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpWebRequest>**

## <a name="syntax"></a><span data-ttu-id="893a1-105">構文</span><span class="sxs-lookup"><span data-stu-id="893a1-105">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="893a1-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="893a1-106">Attributes and Elements</span></span>  
 <span data-ttu-id="893a1-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="893a1-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="893a1-108">属性</span><span class="sxs-lookup"><span data-stu-id="893a1-108">Attributes</span></span>  
  
|<span data-ttu-id="893a1-109">**属性**</span><span class="sxs-lookup"><span data-stu-id="893a1-109">**Attribute**</span></span>|<span data-ttu-id="893a1-110">**説明**</span><span class="sxs-lookup"><span data-stu-id="893a1-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="893a1-111">応答ヘッダーの最大長を kb 単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="893a1-111">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="893a1-112">既定値は、64 です。</span><span class="sxs-lookup"><span data-stu-id="893a1-112">The default is 64.</span></span> <span data-ttu-id="893a1-113">値が-1 の場合は、応答ヘッダーにサイズ制限が適用されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="893a1-113">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="893a1-114">エラー応答の最大長を kb 単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="893a1-114">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="893a1-115">既定値は、64 です。</span><span class="sxs-lookup"><span data-stu-id="893a1-115">The default is 64.</span></span> <span data-ttu-id="893a1-116">値が-1 の場合は、エラー応答にサイズ制限が適用されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="893a1-116">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="893a1-117">未承認のエラーコードへの応答としてのアップロードの最大長をバイト単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="893a1-117">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="893a1-118">既定値は -1 です。</span><span class="sxs-lookup"><span data-stu-id="893a1-118">The default is -1.</span></span> <span data-ttu-id="893a1-119">値 -1 は、アップロード情報にサイズ制限が適用されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="893a1-119">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="893a1-120">Unsafe ヘッダーの解析が有効かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="893a1-120">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="893a1-121">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="893a1-121">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="893a1-122">子要素</span><span class="sxs-lookup"><span data-stu-id="893a1-122">Child Elements</span></span>  
 <span data-ttu-id="893a1-123">なし。</span><span class="sxs-lookup"><span data-stu-id="893a1-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="893a1-124">親要素</span><span class="sxs-lookup"><span data-stu-id="893a1-124">Parent Elements</span></span>  
  
|<span data-ttu-id="893a1-125">**要素**</span><span class="sxs-lookup"><span data-stu-id="893a1-125">**Element**</span></span>|<span data-ttu-id="893a1-126">**説明**</span><span class="sxs-lookup"><span data-stu-id="893a1-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="893a1-127">設定</span><span class="sxs-lookup"><span data-stu-id="893a1-127">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="893a1-128"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="893a1-128">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="893a1-129">解説</span><span class="sxs-lookup"><span data-stu-id="893a1-129">Remarks</span></span>  
 <span data-ttu-id="893a1-130">既定では、.NET Framework は URI 解析に RFC 2616 を厳密に適用します。</span><span class="sxs-lookup"><span data-stu-id="893a1-130">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="893a1-131">一部のサーバー応答には、禁止されたフィールドの制御文字が含まれる場合があります。これにより、 <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> メソッドはをスローし <xref:System.Net.WebException> ます。</span><span class="sxs-lookup"><span data-stu-id="893a1-131">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="893a1-132">**Useunsafeheaderparsing**が**true**に設定されている場合、 <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> はこの場合にをスローしません。ただし、アプリケーションは、いくつかの形式の URI 解析攻撃に対して脆弱になります。</span><span class="sxs-lookup"><span data-stu-id="893a1-132">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="893a1-133">最適な解決策は、応答に制御文字が含まれないようにサーバーを変更することです。</span><span class="sxs-lookup"><span data-stu-id="893a1-133">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="893a1-134">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="893a1-134">Configuration Files</span></span>  
 <span data-ttu-id="893a1-135">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="893a1-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="893a1-136">例</span><span class="sxs-lookup"><span data-stu-id="893a1-136">Example</span></span>  
 <span data-ttu-id="893a1-137">次の例は、通常の最大ヘッダー長より大きいを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="893a1-137">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="893a1-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="893a1-138">See also</span></span>

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="893a1-139">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="893a1-139">Network Settings Schema</span></span>](index.md)
