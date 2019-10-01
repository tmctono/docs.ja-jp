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
ms.openlocfilehash: fa00aed2cd1e96ec788d4bc9c1c63f20561d8d1c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698184"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="3573c-102">\<httpWebRequest > 要素 (ネットワーク設定)</span><span class="sxs-lookup"><span data-stu-id="3573c-102">\<httpWebRequest> Element (Network Settings)</span></span>
<span data-ttu-id="3573c-103">Web 要求パラメーターをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="3573c-103">Customizes Web request parameters.</span></span>  
  
[<span data-ttu-id="3573c-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="3573c-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="3573c-105">&nbsp; @ no__t-1[ **@no__t 47 >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3573c-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="3573c-106">&nbsp; @ no__t @ no__t @no__t @ no__t-3[ **-6 設定 >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3573c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>  
<span data-ttu-id="3573c-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 **\<httpWebRequest >** を行います。</span><span class="sxs-lookup"><span data-stu-id="3573c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpWebRequest>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3573c-108">構文</span><span class="sxs-lookup"><span data-stu-id="3573c-108">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3573c-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3573c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3573c-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3573c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3573c-111">属性</span><span class="sxs-lookup"><span data-stu-id="3573c-111">Attributes</span></span>  
  
|<span data-ttu-id="3573c-112">**属性**</span><span class="sxs-lookup"><span data-stu-id="3573c-112">**Attribute**</span></span>|<span data-ttu-id="3573c-113">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="3573c-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="3573c-114">応答ヘッダーの最大長を kb 単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="3573c-114">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="3573c-115">既定値は 64 です。</span><span class="sxs-lookup"><span data-stu-id="3573c-115">The default is 64.</span></span> <span data-ttu-id="3573c-116">値が-1 の場合は、応答ヘッダーにサイズ制限が適用されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="3573c-116">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="3573c-117">エラー応答の最大長を kb 単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="3573c-117">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="3573c-118">既定値は 64 です。</span><span class="sxs-lookup"><span data-stu-id="3573c-118">The default is 64.</span></span> <span data-ttu-id="3573c-119">値が-1 の場合は、エラー応答にサイズ制限が適用されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="3573c-119">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="3573c-120">未承認のエラーコードへの応答としてのアップロードの最大長をバイト単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="3573c-120">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="3573c-121">既定値は -1 です。</span><span class="sxs-lookup"><span data-stu-id="3573c-121">The default is -1.</span></span> <span data-ttu-id="3573c-122">値-1 は、アップロード時にサイズ制限が適用されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="3573c-122">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="3573c-123">Unsafe ヘッダーの解析が有効かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3573c-123">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="3573c-124">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="3573c-124">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3573c-125">子要素</span><span class="sxs-lookup"><span data-stu-id="3573c-125">Child Elements</span></span>  
 <span data-ttu-id="3573c-126">なし。</span><span class="sxs-lookup"><span data-stu-id="3573c-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3573c-127">親要素</span><span class="sxs-lookup"><span data-stu-id="3573c-127">Parent Elements</span></span>  
  
|<span data-ttu-id="3573c-128">**要素**</span><span class="sxs-lookup"><span data-stu-id="3573c-128">**Element**</span></span>|<span data-ttu-id="3573c-129">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="3573c-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3573c-130">settings</span><span class="sxs-lookup"><span data-stu-id="3573c-130">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="3573c-131"><xref:System.Net> 名前空間の基本的なネットワーク オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="3573c-131">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3573c-132">コメント</span><span class="sxs-lookup"><span data-stu-id="3573c-132">Remarks</span></span>  
 <span data-ttu-id="3573c-133">既定では、.NET Framework は URI 解析に RFC 2616 を厳密に適用します。</span><span class="sxs-lookup"><span data-stu-id="3573c-133">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="3573c-134">一部のサーバー応答には、禁止されたフィールドの制御文字が含まれる場合があります。これにより、<xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> のメソッドが <xref:System.Net.WebException> をスローします。</span><span class="sxs-lookup"><span data-stu-id="3573c-134">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="3573c-135">**Useunsafeheaderparsing 解析**が**true**に設定されている場合、<xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> は、この場合はをスローしません。ただし、アプリケーションは、いくつかの形式の URI 解析攻撃に対して脆弱になります。</span><span class="sxs-lookup"><span data-stu-id="3573c-135">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="3573c-136">最適な解決策は、応答に制御文字が含まれないようにサーバーを変更することです。</span><span class="sxs-lookup"><span data-stu-id="3573c-136">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3573c-137">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="3573c-137">Configuration Files</span></span>  
 <span data-ttu-id="3573c-138">この要素は、アプリケーション構成ファイルまたはマシン構成ファイル (Machine.config) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3573c-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3573c-139">例</span><span class="sxs-lookup"><span data-stu-id="3573c-139">Example</span></span>  
 <span data-ttu-id="3573c-140">次の例は、通常の最大ヘッダー長より大きいを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3573c-140">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3573c-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="3573c-141">See also</span></span>

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="3573c-142">ネットワーク設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="3573c-142">Network Settings Schema</span></span>](index.md)
