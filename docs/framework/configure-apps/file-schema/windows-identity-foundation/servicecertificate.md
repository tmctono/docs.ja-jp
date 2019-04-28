---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: 328d074f9edc5ddf871308a7e3d694bf94adea78
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793823"
---
# <a name="servicecertificate"></a><span data-ttu-id="b2d0b-101">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="b2d0b-101">\<serviceCertificate></span></span>
<span data-ttu-id="b2d0b-102">暗号化し、トークン暗号化解除に使用される X.509 証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="b2d0b-102">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="b2d0b-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="b2d0b-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="b2d0b-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="b2d0b-104">\<federationConfiguration></span></span>  
<span data-ttu-id="b2d0b-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="b2d0b-105">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2d0b-106">構文</span><span class="sxs-lookup"><span data-stu-id="b2d0b-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2d0b-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b2d0b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b2d0b-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b2d0b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2d0b-109">属性</span><span class="sxs-lookup"><span data-stu-id="b2d0b-109">Attributes</span></span>  
 <span data-ttu-id="b2d0b-110">なし</span><span class="sxs-lookup"><span data-stu-id="b2d0b-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b2d0b-111">子要素</span><span class="sxs-lookup"><span data-stu-id="b2d0b-111">Child Elements</span></span>  
  
|<span data-ttu-id="b2d0b-112">要素</span><span class="sxs-lookup"><span data-stu-id="b2d0b-112">Element</span></span>|<span data-ttu-id="b2d0b-113">説明</span><span class="sxs-lookup"><span data-stu-id="b2d0b-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2d0b-114">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="b2d0b-114">\<certificateReference></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|<span data-ttu-id="b2d0b-115">検索して、証明書ストアに X.509 証明書の検証に使用される設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="b2d0b-115">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b2d0b-116">親要素</span><span class="sxs-lookup"><span data-stu-id="b2d0b-116">Parent Elements</span></span>  
  
|<span data-ttu-id="b2d0b-117">要素</span><span class="sxs-lookup"><span data-stu-id="b2d0b-117">Element</span></span>|<span data-ttu-id="b2d0b-118">説明</span><span class="sxs-lookup"><span data-stu-id="b2d0b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2d0b-119">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="b2d0b-119">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="b2d0b-120">構成設定が含まれています、 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) と<xref:System.IdentityModel.Services.SessionAuthenticationModule>(SAM)。</span><span class="sxs-lookup"><span data-stu-id="b2d0b-120">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b2d0b-121">例</span><span class="sxs-lookup"><span data-stu-id="b2d0b-121">Example</span></span>  
 <span data-ttu-id="b2d0b-122">次の XML の使用を示しています、 \<serviceCertificate > 要素。</span><span class="sxs-lookup"><span data-stu-id="b2d0b-122">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="b2d0b-123">XML から取得されますが、`CustomToken`サンプル。</span><span class="sxs-lookup"><span data-stu-id="b2d0b-123">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
