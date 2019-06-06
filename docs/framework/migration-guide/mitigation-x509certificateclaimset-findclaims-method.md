---
title: '軽減策: X509CertificateClaimSet.FindClaims メソッド'
ms.date: 03/30/2017
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7fb1eb0c502584caac11ca3dde6e7e646b29cfe
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2019
ms.locfileid: "66251089"
---
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a><span data-ttu-id="db66f-102">軽減策: X509CertificateClaimSet.FindClaims メソッド</span><span class="sxs-lookup"><span data-stu-id="db66f-102">Mitigation: X509CertificateClaimSet.FindClaims Method</span></span>
<span data-ttu-id="db66f-103"><xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> メソッドは、.NET Framework 4.6.1 を対象とするアプリから、`claimType` 引数と SAN フィールド内のすべての DNS エントリとの照合を試みます。</span><span class="sxs-lookup"><span data-stu-id="db66f-103">Starting with apps that target the .NET Framework 4.6.1,  the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method will attempt to match the `claimType` argument with all the DNS entries in its SAN field.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="db66f-104">影響</span><span class="sxs-lookup"><span data-stu-id="db66f-104">Impact</span></span>  
 <span data-ttu-id="db66f-105">この変更によって影響を受けるのは、.NET Framework 4.6.1 以降のバージョンの .NET Framework を対象とするアプリのみです。</span><span class="sxs-lookup"><span data-stu-id="db66f-105">This change only affects apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1.</span></span>  
  
 <span data-ttu-id="db66f-106">.NET Framework の以前のバージョンを対象とするアプリの場合、<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> メソッドは、`claimType` 引数と最後の DNS エントリのみの照合を試みます。</span><span class="sxs-lookup"><span data-stu-id="db66f-106">For apps that target previous versions of the .NET Framework, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method attempts to match the `claimType` argument only with the last  DNS entry.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="db66f-107">軽減策</span><span class="sxs-lookup"><span data-stu-id="db66f-107">Mitigation</span></span>  
 <span data-ttu-id="db66f-108">この変更が望ましくない場合は、.NET Framework 4.6.1 バージョン以降の .NET Framework を対象とするアプリで無効にできます。これは、そのアプリの構成ファイルの [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) セクションに次の構成設定を追加して行います。</span><span class="sxs-lookup"><span data-stu-id="db66f-108">If this change is undesirable, apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1 can opt out of it by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />   
</runtime>  
```  
  
 <span data-ttu-id="db66f-109">また、以前のバージョンの .NET Framework を対象とするものの、.NET Framework 4.6.1 以降のバージョンで実行されているアプリでは、そのアプリの構成ファイルの [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) セクションに構成設定を追加して、この動作を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="db66f-109">In addition, apps that target previous versions of the .NET Framework but are running under the .NET Framework 4.6.1 and later versions can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />   
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="db66f-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="db66f-110">See also</span></span>

- [<span data-ttu-id="db66f-111">変更の再ターゲット</span><span class="sxs-lookup"><span data-stu-id="db66f-111">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)
