---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: c25f183679f41f51ffee4f482bfe7a64763647d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941901"
---
# <a name="certificatevalidator"></a><span data-ttu-id="aff1b-101">\<certificateValidator の ></span><span class="sxs-lookup"><span data-stu-id="aff1b-101">\<certificateValidator></span></span>
<span data-ttu-id="aff1b-102">証明書の検証に使用するカスタムの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="aff1b-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="aff1b-103">この型は、 `certificateValidationMode` [ \<certificatevalidation >](certificatevalidation.md)要素の属性が "Custom" に設定されている場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="aff1b-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="aff1b-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="aff1b-104">\<system.identityModel></span></span>  
<span data-ttu-id="aff1b-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="aff1b-105">\<identityConfiguration></span></span>  
<span data-ttu-id="aff1b-106">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="aff1b-106">\<certificateValidation></span></span>  
<span data-ttu-id="aff1b-107">\<certificateValidator の ></span><span class="sxs-lookup"><span data-stu-id="aff1b-107">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aff1b-108">構文</span><span class="sxs-lookup"><span data-stu-id="aff1b-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aff1b-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="aff1b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="aff1b-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="aff1b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aff1b-111">属性</span><span class="sxs-lookup"><span data-stu-id="aff1b-111">Attributes</span></span>  
  
|<span data-ttu-id="aff1b-112">属性</span><span class="sxs-lookup"><span data-stu-id="aff1b-112">Attribute</span></span>|<span data-ttu-id="aff1b-113">説明</span><span class="sxs-lookup"><span data-stu-id="aff1b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aff1b-114">種類</span><span class="sxs-lookup"><span data-stu-id="aff1b-114">type</span></span>|<span data-ttu-id="aff1b-115"><xref:System.IdentityModel.Selectors.X509CertificateValidator>クラスから派生するカスタム型を指定します。</span><span class="sxs-lookup"><span data-stu-id="aff1b-115">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="aff1b-116">この型を使用するには、 [ \<certificatevalidation >](certificatevalidation.md)要素の属性を"Custom"に設定します。`certificateValidationMode`</span><span class="sxs-lookup"><span data-stu-id="aff1b-116">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="aff1b-117">`type`属性を指定する方法の詳細については、「[カスタム型参照](../windows-workflow-foundation/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aff1b-117">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="aff1b-118">任意。</span><span class="sxs-lookup"><span data-stu-id="aff1b-118">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aff1b-119">子要素</span><span class="sxs-lookup"><span data-stu-id="aff1b-119">Child Elements</span></span>  
 <span data-ttu-id="aff1b-120">なし</span><span class="sxs-lookup"><span data-stu-id="aff1b-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aff1b-121">親要素</span><span class="sxs-lookup"><span data-stu-id="aff1b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="aff1b-122">要素</span><span class="sxs-lookup"><span data-stu-id="aff1b-122">Element</span></span>|<span data-ttu-id="aff1b-123">説明</span><span class="sxs-lookup"><span data-stu-id="aff1b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aff1b-124">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="aff1b-124">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="aff1b-125">トークンハンドラーが証明書を検証するために使用する設定を制御します。</span><span class="sxs-lookup"><span data-stu-id="aff1b-125">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="aff1b-126">例</span><span class="sxs-lookup"><span data-stu-id="aff1b-126">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
