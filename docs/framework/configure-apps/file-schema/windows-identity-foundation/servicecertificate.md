---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: 653dd9cfadbfd33f5371b77172199b946321bc8c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251860"
---
# <a name="servicecertificate"></a><span data-ttu-id="5cfe1-101">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="5cfe1-101">\<serviceCertificate></span></span>
<span data-ttu-id="5cfe1-102">トークンの暗号化と復号化に使用される x.509 証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="5cfe1-102">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
<span data-ttu-id="5cfe1-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5cfe1-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5cfe1-104">&nbsp;&nbsp;[ **\<> のシステム**](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="5cfe1-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="5cfe1-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationConfiguration >** ](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="5cfe1-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="5cfe1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceCertificate >**</span><span class="sxs-lookup"><span data-stu-id="5cfe1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cfe1-107">構文</span><span class="sxs-lookup"><span data-stu-id="5cfe1-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5cfe1-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5cfe1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5cfe1-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5cfe1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5cfe1-110">属性</span><span class="sxs-lookup"><span data-stu-id="5cfe1-110">Attributes</span></span>  
 <span data-ttu-id="5cfe1-111">なし</span><span class="sxs-lookup"><span data-stu-id="5cfe1-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5cfe1-112">子要素</span><span class="sxs-lookup"><span data-stu-id="5cfe1-112">Child Elements</span></span>  
  
|<span data-ttu-id="5cfe1-113">要素</span><span class="sxs-lookup"><span data-stu-id="5cfe1-113">Element</span></span>|<span data-ttu-id="5cfe1-114">説明</span><span class="sxs-lookup"><span data-stu-id="5cfe1-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5cfe1-115">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="5cfe1-115">\<certificateReference></span></span>](certificatereference.md)|<span data-ttu-id="5cfe1-116">証明書ストアの x.509 証明書を検索して検証するために使用する設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="5cfe1-116">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5cfe1-117">親要素</span><span class="sxs-lookup"><span data-stu-id="5cfe1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="5cfe1-118">要素</span><span class="sxs-lookup"><span data-stu-id="5cfe1-118">Element</span></span>|<span data-ttu-id="5cfe1-119">説明</span><span class="sxs-lookup"><span data-stu-id="5cfe1-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5cfe1-120">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="5cfe1-120">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="5cfe1-121"><xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (Wsfam) <xref:System.IdentityModel.Services.SessionAuthenticationModule>と (SAM) を構成する設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5cfe1-121">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5cfe1-122">例</span><span class="sxs-lookup"><span data-stu-id="5cfe1-122">Example</span></span>  
 <span data-ttu-id="5cfe1-123">次の XML は、 \<serviceCertificate > 要素の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5cfe1-123">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="5cfe1-124">XML は、「」の`CustomToken`サンプルから抜粋したものです。</span><span class="sxs-lookup"><span data-stu-id="5cfe1-124">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
