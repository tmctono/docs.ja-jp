---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: a3aba5618855f7225dc8a427516eaa72b45f6e8b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942412"
---
# <a name="servicecertificate"></a><span data-ttu-id="f9d9c-101">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="f9d9c-101">\<serviceCertificate></span></span>
<span data-ttu-id="f9d9c-102">トークンの暗号化と復号化に使用される x.509 証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="f9d9c-102">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="f9d9c-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="f9d9c-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="f9d9c-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="f9d9c-104">\<federationConfiguration></span></span>  
<span data-ttu-id="f9d9c-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="f9d9c-105">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9d9c-106">構文</span><span class="sxs-lookup"><span data-stu-id="f9d9c-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9d9c-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f9d9c-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f9d9c-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9d9c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9d9c-109">属性</span><span class="sxs-lookup"><span data-stu-id="f9d9c-109">Attributes</span></span>  
 <span data-ttu-id="f9d9c-110">なし</span><span class="sxs-lookup"><span data-stu-id="f9d9c-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f9d9c-111">子要素</span><span class="sxs-lookup"><span data-stu-id="f9d9c-111">Child Elements</span></span>  
  
|<span data-ttu-id="f9d9c-112">要素</span><span class="sxs-lookup"><span data-stu-id="f9d9c-112">Element</span></span>|<span data-ttu-id="f9d9c-113">説明</span><span class="sxs-lookup"><span data-stu-id="f9d9c-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9d9c-114">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="f9d9c-114">\<certificateReference></span></span>](certificatereference.md)|<span data-ttu-id="f9d9c-115">証明書ストアの x.509 証明書を検索して検証するために使用する設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="f9d9c-115">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f9d9c-116">親要素</span><span class="sxs-lookup"><span data-stu-id="f9d9c-116">Parent Elements</span></span>  
  
|<span data-ttu-id="f9d9c-117">要素</span><span class="sxs-lookup"><span data-stu-id="f9d9c-117">Element</span></span>|<span data-ttu-id="f9d9c-118">説明</span><span class="sxs-lookup"><span data-stu-id="f9d9c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9d9c-119">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="f9d9c-119">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="f9d9c-120"><xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (Wsfam) <xref:System.IdentityModel.Services.SessionAuthenticationModule>と (SAM) を構成する設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f9d9c-120">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f9d9c-121">例</span><span class="sxs-lookup"><span data-stu-id="f9d9c-121">Example</span></span>  
 <span data-ttu-id="f9d9c-122">次の XML は、 \<serviceCertificate > 要素の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f9d9c-122">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="f9d9c-123">XML は、「」の`CustomToken`サンプルから抜粋したものです。</span><span class="sxs-lookup"><span data-stu-id="f9d9c-123">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
