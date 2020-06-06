---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: 653dd9cfadbfd33f5371b77172199b946321bc8c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251860"
---
# \<serviceCertificate>
<span data-ttu-id="28358-101">トークンの暗号化と復号化に使用される x.509 証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="28358-101">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="28358-102">構文</span><span class="sxs-lookup"><span data-stu-id="28358-102">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28358-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="28358-103">Attributes and Elements</span></span>  
 <span data-ttu-id="28358-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="28358-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28358-105">属性</span><span class="sxs-lookup"><span data-stu-id="28358-105">Attributes</span></span>  
 <span data-ttu-id="28358-106">なし</span><span class="sxs-lookup"><span data-stu-id="28358-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="28358-107">子要素</span><span class="sxs-lookup"><span data-stu-id="28358-107">Child Elements</span></span>  
  
|<span data-ttu-id="28358-108">要素</span><span class="sxs-lookup"><span data-stu-id="28358-108">Element</span></span>|<span data-ttu-id="28358-109">説明</span><span class="sxs-lookup"><span data-stu-id="28358-109">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateReference>](certificatereference.md)|<span data-ttu-id="28358-110">証明書ストアの x.509 証明書を検索して検証するために使用する設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="28358-110">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="28358-111">親要素</span><span class="sxs-lookup"><span data-stu-id="28358-111">Parent Elements</span></span>  
  
|<span data-ttu-id="28358-112">要素</span><span class="sxs-lookup"><span data-stu-id="28358-112">Element</span></span>|<span data-ttu-id="28358-113">説明</span><span class="sxs-lookup"><span data-stu-id="28358-113">Description</span></span>|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|<span data-ttu-id="28358-114"><xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(Wsfam) と (SAM) を構成する設定が含まれてい <xref:System.IdentityModel.Services.SessionAuthenticationModule> ます。</span><span class="sxs-lookup"><span data-stu-id="28358-114">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="28358-115">例</span><span class="sxs-lookup"><span data-stu-id="28358-115">Example</span></span>  
 <span data-ttu-id="28358-116">次の XML は、要素の使用方法を示して \<serviceCertificate> います。</span><span class="sxs-lookup"><span data-stu-id="28358-116">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="28358-117">XML は、「」のサンプルから抜粋したものです `CustomToken` 。</span><span class="sxs-lookup"><span data-stu-id="28358-117">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
