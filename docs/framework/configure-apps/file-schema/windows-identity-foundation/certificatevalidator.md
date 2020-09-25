---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 8476600769b6099bb885566de4c908c78a2dbbda
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201376"
---
# \<certificateValidator>

<span data-ttu-id="4ec45-101">証明書の検証に使用するカスタムの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ec45-101">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="4ec45-102">この型は `certificateValidationMode` 、要素の属性 [\<certificateValidation>](certificatevalidation.md) が "Custom" に設定されている場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="4ec45-102">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**  
  
## <a name="syntax"></a><span data-ttu-id="4ec45-103">構文</span><span class="sxs-lookup"><span data-stu-id="4ec45-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ec45-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4ec45-104">Attributes and Elements</span></span>  

 <span data-ttu-id="4ec45-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ec45-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ec45-106">属性</span><span class="sxs-lookup"><span data-stu-id="4ec45-106">Attributes</span></span>  
  
|<span data-ttu-id="4ec45-107">属性</span><span class="sxs-lookup"><span data-stu-id="4ec45-107">Attribute</span></span>|<span data-ttu-id="4ec45-108">[説明]</span><span class="sxs-lookup"><span data-stu-id="4ec45-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4ec45-109">type</span><span class="sxs-lookup"><span data-stu-id="4ec45-109">type</span></span>|<span data-ttu-id="4ec45-110">クラスから派生するカスタム型を指定し <xref:System.IdentityModel.Selectors.X509CertificateValidator> ます。</span><span class="sxs-lookup"><span data-stu-id="4ec45-110">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="4ec45-111">`certificateValidationMode` [\<certificateValidation>](certificatevalidation.md) この型を使用するには、要素の属性を "Custom" に設定します。</span><span class="sxs-lookup"><span data-stu-id="4ec45-111">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="4ec45-112">属性を指定する方法の詳細については `type` 、「 [カスタム型参照](../windows-workflow-foundation/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ec45-112">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="4ec45-113">省略可能。</span><span class="sxs-lookup"><span data-stu-id="4ec45-113">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ec45-114">子要素</span><span class="sxs-lookup"><span data-stu-id="4ec45-114">Child Elements</span></span>  

 <span data-ttu-id="4ec45-115">None</span><span class="sxs-lookup"><span data-stu-id="4ec45-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ec45-116">親要素</span><span class="sxs-lookup"><span data-stu-id="4ec45-116">Parent Elements</span></span>  
  
|<span data-ttu-id="4ec45-117">要素</span><span class="sxs-lookup"><span data-stu-id="4ec45-117">Element</span></span>|<span data-ttu-id="4ec45-118">説明</span><span class="sxs-lookup"><span data-stu-id="4ec45-118">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateValidation>](certificatevalidation.md)|<span data-ttu-id="4ec45-119">トークンハンドラーが証明書を検証するために使用する設定を制御します。</span><span class="sxs-lookup"><span data-stu-id="4ec45-119">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4ec45-120">例</span><span class="sxs-lookup"><span data-stu-id="4ec45-120">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />
</certificateValidation>
```
