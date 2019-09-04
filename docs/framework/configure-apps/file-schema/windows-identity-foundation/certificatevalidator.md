---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 30f81dd5948a7d366c1116cffd347c85a396f5ae
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252125"
---
# <a name="certificatevalidator"></a><span data-ttu-id="7a60a-101">\<certificateValidator の ></span><span class="sxs-lookup"><span data-stu-id="7a60a-101">\<certificateValidator></span></span>
<span data-ttu-id="7a60a-102">証明書の検証に使用するカスタムの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="7a60a-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="7a60a-103">この型は、 `certificateValidationMode` [ \<certificatevalidation >](certificatevalidation.md)要素の属性が "Custom" に設定されている場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="7a60a-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
<span data-ttu-id="7a60a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7a60a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7a60a-105">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="7a60a-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="7a60a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="7a60a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="7a60a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<certificateValidation >** ](certificatevalidation.md)</span><span class="sxs-lookup"><span data-stu-id="7a60a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)</span></span>\
<span data-ttu-id="7a60a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<certificateValidator の >**</span><span class="sxs-lookup"><span data-stu-id="7a60a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a60a-109">構文</span><span class="sxs-lookup"><span data-stu-id="7a60a-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a60a-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7a60a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7a60a-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a60a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a60a-112">属性</span><span class="sxs-lookup"><span data-stu-id="7a60a-112">Attributes</span></span>  
  
|<span data-ttu-id="7a60a-113">属性</span><span class="sxs-lookup"><span data-stu-id="7a60a-113">Attribute</span></span>|<span data-ttu-id="7a60a-114">説明</span><span class="sxs-lookup"><span data-stu-id="7a60a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7a60a-115">型</span><span class="sxs-lookup"><span data-stu-id="7a60a-115">type</span></span>|<span data-ttu-id="7a60a-116"><xref:System.IdentityModel.Selectors.X509CertificateValidator>クラスから派生するカスタム型を指定します。</span><span class="sxs-lookup"><span data-stu-id="7a60a-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="7a60a-117">この型を使用するには、 [ \<certificatevalidation >](certificatevalidation.md)要素の属性を"Custom"に設定します。`certificateValidationMode`</span><span class="sxs-lookup"><span data-stu-id="7a60a-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="7a60a-118">`type`属性を指定する方法の詳細については、「[カスタム型参照](../windows-workflow-foundation/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a60a-118">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="7a60a-119">任意。</span><span class="sxs-lookup"><span data-stu-id="7a60a-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7a60a-120">子要素</span><span class="sxs-lookup"><span data-stu-id="7a60a-120">Child Elements</span></span>  
 <span data-ttu-id="7a60a-121">なし</span><span class="sxs-lookup"><span data-stu-id="7a60a-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7a60a-122">親要素</span><span class="sxs-lookup"><span data-stu-id="7a60a-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7a60a-123">要素</span><span class="sxs-lookup"><span data-stu-id="7a60a-123">Element</span></span>|<span data-ttu-id="7a60a-124">説明</span><span class="sxs-lookup"><span data-stu-id="7a60a-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7a60a-125">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="7a60a-125">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="7a60a-126">トークンハンドラーが証明書を検証するために使用する設定を制御します。</span><span class="sxs-lookup"><span data-stu-id="7a60a-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7a60a-127">例</span><span class="sxs-lookup"><span data-stu-id="7a60a-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
