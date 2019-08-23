---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: 3602a4805e86833ba6070d801cef6758aaee8a5c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941824"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="63872-101">\<claimsAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="63872-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="63872-102">入力方向の要求に対して要求認証マネージャーを登録します。</span><span class="sxs-lookup"><span data-stu-id="63872-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="63872-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="63872-103">\<system.identityModel></span></span>  
<span data-ttu-id="63872-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="63872-104">\<identityConfiguration></span></span>  
<span data-ttu-id="63872-105">\<claimsAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="63872-105">\<claimsAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63872-106">構文</span><span class="sxs-lookup"><span data-stu-id="63872-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63872-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="63872-107">Attributes and Elements</span></span>  
 <span data-ttu-id="63872-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="63872-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63872-109">属性</span><span class="sxs-lookup"><span data-stu-id="63872-109">Attributes</span></span>  
  
|<span data-ttu-id="63872-110">属性</span><span class="sxs-lookup"><span data-stu-id="63872-110">Attribute</span></span>|<span data-ttu-id="63872-111">説明</span><span class="sxs-lookup"><span data-stu-id="63872-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="63872-112">種類</span><span class="sxs-lookup"><span data-stu-id="63872-112">type</span></span>|<span data-ttu-id="63872-113"><xref:System.Security.Claims.ClaimsAuthenticationManager>クラスから派生するカスタム型を指定します。</span><span class="sxs-lookup"><span data-stu-id="63872-113">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="63872-114">`type`属性を指定する方法の詳細については、「[カスタム型参照]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63872-114">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63872-115">子要素</span><span class="sxs-lookup"><span data-stu-id="63872-115">Child Elements</span></span>  
 <span data-ttu-id="63872-116">`type`属性が存在しない場合、または`type`属性が<xref:System.Security.Claims.ClaimsAuthenticationManager>クラスを`<claimsAuthenticationManager>`参照している場合、要素は子要素を受け取りません<xref:System.Security.Claims.ClaimsAuthenticationManager> 。ただし、から派生したクラスは子構成要素を定義できます。</span><span class="sxs-lookup"><span data-stu-id="63872-116">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="63872-117">親要素</span><span class="sxs-lookup"><span data-stu-id="63872-117">Parent Elements</span></span>  
  
|<span data-ttu-id="63872-118">要素</span><span class="sxs-lookup"><span data-stu-id="63872-118">Element</span></span>|<span data-ttu-id="63872-119">説明</span><span class="sxs-lookup"><span data-stu-id="63872-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="63872-120">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="63872-120">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="63872-121">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="63872-121">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63872-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="63872-122">Remarks</span></span>  
 <span data-ttu-id="63872-123">クラスに<xref:System.Security.Claims.ClaimsAuthenticationManager>よって提供される既定の動作では、入力方向の要求がエコーされます。</span><span class="sxs-lookup"><span data-stu-id="63872-123">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="63872-124">属性が指定されていない`type`場合、また<xref:System.Security.Claims.ClaimsAuthenticationManager>は属性で`<claimsAuthenticationManager>`クラスが指定されている場合、要素は子要素を受け取りません。 `type`</span><span class="sxs-lookup"><span data-stu-id="63872-124">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="63872-125">`type`属性を指定して、 <xref:System.Security.Claims.ClaimsAuthenticationManager>クラスから派生した型を登録し、カスタム動作を実装することができます。</span><span class="sxs-lookup"><span data-stu-id="63872-125">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="63872-126">派生クラスでは、 `<claimsAuthenticationManager>`要素の子要素を使用した構成をサポートできます。これを行うには、 <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A>メソッドをオーバーライドしてこれらの要素を処理します。</span><span class="sxs-lookup"><span data-stu-id="63872-126">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="63872-127">子要素に対して定義されているスキーマは、クラスのデザイナーによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="63872-127">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="63872-128">要素`<claimsAuthenticationManager>`は、プロパティ<xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType>を設定します。</span><span class="sxs-lookup"><span data-stu-id="63872-128">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63872-129">例</span><span class="sxs-lookup"><span data-stu-id="63872-129">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```
