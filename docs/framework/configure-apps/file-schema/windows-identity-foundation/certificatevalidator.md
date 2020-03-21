---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 3f3d79d3567c1714a79423b7767ce3f454b9d52d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152789"
---
# <a name="certificatevalidator"></a><span data-ttu-id="17b13-101">\<証明書検証ツール></span><span class="sxs-lookup"><span data-stu-id="17b13-101">\<certificateValidator></span></span>
<span data-ttu-id="17b13-102">証明書の検証用のカスタム型を指定します。</span><span class="sxs-lookup"><span data-stu-id="17b13-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="17b13-103">この型は、[\<証明書](certificatevalidation.md)の`certificateValidationMode`属性が "カスタム">設定されている場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="17b13-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
<span data-ttu-id="17b13-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="17b13-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="17b13-105">&nbsp;&nbsp;[**\<>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="17b13-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="17b13-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<id構成>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="17b13-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="17b13-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<証明書検証>**](certificatevalidation.md)</span><span class="sxs-lookup"><span data-stu-id="17b13-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)</span></span>\
<span data-ttu-id="17b13-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<証明書検証ツール>**</span><span class="sxs-lookup"><span data-stu-id="17b13-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17b13-109">構文</span><span class="sxs-lookup"><span data-stu-id="17b13-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation>  
      <certificateValidator type=xs:string>  
      </certificateValidator>  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17b13-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="17b13-110">Attributes and Elements</span></span>  
 <span data-ttu-id="17b13-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="17b13-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17b13-112">属性</span><span class="sxs-lookup"><span data-stu-id="17b13-112">Attributes</span></span>  
  
|<span data-ttu-id="17b13-113">属性</span><span class="sxs-lookup"><span data-stu-id="17b13-113">Attribute</span></span>|<span data-ttu-id="17b13-114">説明</span><span class="sxs-lookup"><span data-stu-id="17b13-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="17b13-115">type</span><span class="sxs-lookup"><span data-stu-id="17b13-115">type</span></span>|<span data-ttu-id="17b13-116">クラスから派生するカスタム型を指定します<xref:System.IdentityModel.Selectors.X509CertificateValidator>。</span><span class="sxs-lookup"><span data-stu-id="17b13-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="17b13-117">この型`certificateValidationMode`を使用するには、証明書の[\<属性を [検証>](certificatevalidation.md)要素を "カスタム" に設定します。</span><span class="sxs-lookup"><span data-stu-id="17b13-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="17b13-118">`type`属性の指定方法の詳細については、「[カスタム型参照](../windows-workflow-foundation/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17b13-118">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="17b13-119">省略可能。</span><span class="sxs-lookup"><span data-stu-id="17b13-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="17b13-120">子要素</span><span class="sxs-lookup"><span data-stu-id="17b13-120">Child Elements</span></span>  
 <span data-ttu-id="17b13-121">なし</span><span class="sxs-lookup"><span data-stu-id="17b13-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="17b13-122">親要素</span><span class="sxs-lookup"><span data-stu-id="17b13-122">Parent Elements</span></span>  
  
|<span data-ttu-id="17b13-123">要素</span><span class="sxs-lookup"><span data-stu-id="17b13-123">Element</span></span>|<span data-ttu-id="17b13-124">説明</span><span class="sxs-lookup"><span data-stu-id="17b13-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17b13-125">\<証明書検証></span><span class="sxs-lookup"><span data-stu-id="17b13-125">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="17b13-126">トークン ハンドラーが証明書の検証に使用する設定を制御します。</span><span class="sxs-lookup"><span data-stu-id="17b13-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="17b13-127">例</span><span class="sxs-lookup"><span data-stu-id="17b13-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />
</certificateValidation>
```
