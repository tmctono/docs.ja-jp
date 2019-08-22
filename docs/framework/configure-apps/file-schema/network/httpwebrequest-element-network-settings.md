---
title: <httpWebRequest> 要素 (ネットワーク設定)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: de5672e5c6762b1e0742e717a3d499a4f93ee8ec
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659342"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="55035-102">\<httpWebRequest > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="55035-102">\<httpWebRequest> Element (Network Settings)</span></span>
<span data-ttu-id="55035-103">Web 要求パラメーターをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="55035-103">Customizes Web request parameters.</span></span>  
  
 <span data-ttu-id="55035-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="55035-104">\<configuration></span></span>  
<span data-ttu-id="55035-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="55035-105">\<system.net></span></span>  
<span data-ttu-id="55035-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="55035-106">\<settings></span></span>  
<span data-ttu-id="55035-107">\<httpWebRequest ></span><span class="sxs-lookup"><span data-stu-id="55035-107">\<httpWebRequest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55035-108">構文</span><span class="sxs-lookup"><span data-stu-id="55035-108">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55035-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="55035-109">Attributes and Elements</span></span>  
 <span data-ttu-id="55035-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="55035-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55035-111">属性</span><span class="sxs-lookup"><span data-stu-id="55035-111">Attributes</span></span>  
  
|<span data-ttu-id="55035-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="55035-112">**Attribute**</span></span>|<span data-ttu-id="55035-113">**説明**</span><span class="sxs-lookup"><span data-stu-id="55035-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="55035-114">応答ヘッダーの最大長を kb 単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="55035-114">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="55035-115">既定値は 64 です。</span><span class="sxs-lookup"><span data-stu-id="55035-115">The default is 64.</span></span> <span data-ttu-id="55035-116">値が-1 の場合は、応答ヘッダーにサイズ制限が適用されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="55035-116">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="55035-117">エラー応答の最大長を kb 単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="55035-117">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="55035-118">既定値は 64 です。</span><span class="sxs-lookup"><span data-stu-id="55035-118">The default is 64.</span></span> <span data-ttu-id="55035-119">値が-1 の場合は、エラー応答にサイズ制限が適用されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="55035-119">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="55035-120">未承認のエラーコードへの応答としてのアップロードの最大長をバイト単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="55035-120">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="55035-121">既定値は -1 です。</span><span class="sxs-lookup"><span data-stu-id="55035-121">The default is -1.</span></span> <span data-ttu-id="55035-122">値-1 は、アップロード時にサイズ制限が適用されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="55035-122">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="55035-123">Unsafe ヘッダーの解析が有効かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="55035-123">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="55035-124">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="55035-124">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="55035-125">子要素</span><span class="sxs-lookup"><span data-stu-id="55035-125">Child Elements</span></span>  
 <span data-ttu-id="55035-126">なし。</span><span class="sxs-lookup"><span data-stu-id="55035-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="55035-127">親要素</span><span class="sxs-lookup"><span data-stu-id="55035-127">Parent Elements</span></span>  
  
|<span data-ttu-id="55035-128">**要素**</span><span class="sxs-lookup"><span data-stu-id="55035-128">**Element**</span></span>|<span data-ttu-id="55035-129">**説明**</span><span class="sxs-lookup"><span data-stu-id="55035-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="55035-130">settings</span><span class="sxs-lookup"><span data-stu-id="55035-130">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="55035-131"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="55035-131">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55035-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="55035-132">Remarks</span></span>  
 <span data-ttu-id="55035-133">既定では、.NET Framework は URI 解析に RFC 2616 を厳密に適用します。</span><span class="sxs-lookup"><span data-stu-id="55035-133">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="55035-134">一部のサーバー応答には、禁止されたフィールドの制御文字<xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType>が含まれる場合<xref:System.Net.WebException>があります。これにより、メソッドはをスローします。</span><span class="sxs-lookup"><span data-stu-id="55035-134">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="55035-135">**Useunsafeheaderparsing**が**true**に設定され<xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType>ている場合、はこの場合にをスローしません。ただし、アプリケーションは、いくつかの形式の URI 解析攻撃に対して脆弱になります。</span><span class="sxs-lookup"><span data-stu-id="55035-135">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="55035-136">最適な解決策は、応答に制御文字が含まれないようにサーバーを変更することです。</span><span class="sxs-lookup"><span data-stu-id="55035-136">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="55035-137">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="55035-137">Configuration Files</span></span>  
 <span data-ttu-id="55035-138">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="55035-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="55035-139">例</span><span class="sxs-lookup"><span data-stu-id="55035-139">Example</span></span>  
 <span data-ttu-id="55035-140">次の例は、通常の最大ヘッダー長より大きいを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="55035-140">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="55035-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="55035-141">See also</span></span>

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="55035-142">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="55035-142">Network Settings Schema</span></span>](index.md)
