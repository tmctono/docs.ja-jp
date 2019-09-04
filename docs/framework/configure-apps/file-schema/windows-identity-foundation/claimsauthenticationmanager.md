---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: c901daf4d442a206345301795c7a4bdc076329cd
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252090"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="f3040-101">\<claimsAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="f3040-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="f3040-102">入力方向の要求に対して要求認証マネージャーを登録します。</span><span class="sxs-lookup"><span data-stu-id="f3040-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
<span data-ttu-id="f3040-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f3040-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f3040-104">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="f3040-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="f3040-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="f3040-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="f3040-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<claimsAuthenticationManager >**</span><span class="sxs-lookup"><span data-stu-id="f3040-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3040-107">構文</span><span class="sxs-lookup"><span data-stu-id="f3040-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3040-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f3040-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f3040-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f3040-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3040-110">属性</span><span class="sxs-lookup"><span data-stu-id="f3040-110">Attributes</span></span>  
  
|<span data-ttu-id="f3040-111">属性</span><span class="sxs-lookup"><span data-stu-id="f3040-111">Attribute</span></span>|<span data-ttu-id="f3040-112">説明</span><span class="sxs-lookup"><span data-stu-id="f3040-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f3040-113">種類</span><span class="sxs-lookup"><span data-stu-id="f3040-113">type</span></span>|<span data-ttu-id="f3040-114"><xref:System.Security.Claims.ClaimsAuthenticationManager>クラスから派生するカスタム型を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3040-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="f3040-115">`type`属性を指定する方法の詳細については、「[カスタム型参照]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3040-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3040-116">子要素</span><span class="sxs-lookup"><span data-stu-id="f3040-116">Child Elements</span></span>  
 <span data-ttu-id="f3040-117">`type`属性が存在しない場合、または`type`属性が<xref:System.Security.Claims.ClaimsAuthenticationManager>クラスを`<claimsAuthenticationManager>`参照している場合、要素は子要素を受け取りません<xref:System.Security.Claims.ClaimsAuthenticationManager> 。ただし、から派生したクラスは子構成要素を定義できます。</span><span class="sxs-lookup"><span data-stu-id="f3040-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3040-118">親要素</span><span class="sxs-lookup"><span data-stu-id="f3040-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f3040-119">要素</span><span class="sxs-lookup"><span data-stu-id="f3040-119">Element</span></span>|<span data-ttu-id="f3040-120">説明</span><span class="sxs-lookup"><span data-stu-id="f3040-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3040-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f3040-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="f3040-122">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3040-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3040-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="f3040-123">Remarks</span></span>  
 <span data-ttu-id="f3040-124">クラスに<xref:System.Security.Claims.ClaimsAuthenticationManager>よって提供される既定の動作では、入力方向の要求がエコーされます。</span><span class="sxs-lookup"><span data-stu-id="f3040-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="f3040-125">属性が指定されていない`type`場合、また<xref:System.Security.Claims.ClaimsAuthenticationManager>は属性で`<claimsAuthenticationManager>`クラスが指定されている場合、要素は子要素を受け取りません。 `type`</span><span class="sxs-lookup"><span data-stu-id="f3040-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="f3040-126">`type`属性を指定して、 <xref:System.Security.Claims.ClaimsAuthenticationManager>クラスから派生した型を登録し、カスタム動作を実装することができます。</span><span class="sxs-lookup"><span data-stu-id="f3040-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="f3040-127">派生クラスでは、 `<claimsAuthenticationManager>`要素の子要素を使用した構成をサポートできます。これを行うには、 <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A>メソッドをオーバーライドしてこれらの要素を処理します。</span><span class="sxs-lookup"><span data-stu-id="f3040-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="f3040-128">子要素に対して定義されているスキーマは、クラスのデザイナーによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="f3040-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="f3040-129">要素`<claimsAuthenticationManager>`は、プロパティ<xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType>を設定します。</span><span class="sxs-lookup"><span data-stu-id="f3040-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3040-130">例</span><span class="sxs-lookup"><span data-stu-id="f3040-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```
