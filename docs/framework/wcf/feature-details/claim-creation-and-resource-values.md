---
title: クレームの作成とリソース値
ms.date: 03/30/2017
helpviewer_keywords:
- claims [WCF], creation and resource values
ms.assetid: 30431f76-cbe7-4bad-bad7-8e43e23a82d4
ms.openlocfilehash: fabd0a2606560d99174e5ad28940c3b59ee689d9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84587054"
---
# <a name="claim-creation-and-resource-values"></a><span data-ttu-id="2bb9e-102">クレームの作成とリソース値</span><span class="sxs-lookup"><span data-stu-id="2bb9e-102">Claim Creation and Resource Values</span></span>
<span data-ttu-id="2bb9e-103"><xref:System.IdentityModel.Claims.Claim> クラスには、組み込みのクレームの種類のインスタンスを作成するためのメソッドが複数用意されています。</span><span class="sxs-lookup"><span data-stu-id="2bb9e-103">The <xref:System.IdentityModel.Claims.Claim> class provides several methods for creating instances of built-in claims types.</span></span> <span data-ttu-id="2bb9e-104">これらのメソッドの中でも、次のものは指定されたリソースに対してセマンティックまたは形式のチェックを行いません。</span><span class="sxs-lookup"><span data-stu-id="2bb9e-104">Of these methods, the following perform no semantic or format checking on the supplied resource:</span></span>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateDnsClaim%2A>  
  
- <span data-ttu-id="2bb9e-105"><xref:System.IdentityModel.Claims.Claim.CreateHashClaim%2A> (長さまたはバイト配列のコンテンツは検査されません)</span><span class="sxs-lookup"><span data-stu-id="2bb9e-105"><xref:System.IdentityModel.Claims.Claim.CreateHashClaim%2A> (does not check the length or content of the byte array)</span></span>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateNameClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateSpnClaim%2A>  
  
- <span data-ttu-id="2bb9e-106"><xref:System.IdentityModel.Claims.Claim.CreateThumbprintClaim%2A> (長さまたはバイト配列のコンテンツは検査されません)</span><span class="sxs-lookup"><span data-stu-id="2bb9e-106"><xref:System.IdentityModel.Claims.Claim.CreateThumbprintClaim%2A> (does not check the length or content of the byte array)</span></span>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateUpnClaim%2A>  
  
 <span data-ttu-id="2bb9e-107">上記のメソッドを使用する場合は、渡されるリソース値が正しい形式である、または正しい情報を含んでいること (あるいは両方) を確認するように注意してください。</span><span class="sxs-lookup"><span data-stu-id="2bb9e-107">Care should be taken when calling the above methods to ensure that the resource values passed in are of the correct format or contain the correct kind of information (or both).</span></span>  
  
 <span data-ttu-id="2bb9e-108">次のメソッドは、特定の型を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2bb9e-108">The following methods take specific types:</span></span>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateDenyOnlyWindowsSidClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateMailAddressClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateRsaClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateUriClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateWindowsSidClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateX500DistinguishedNameClaim%2A>  
  
## <a name="see-also"></a><span data-ttu-id="2bb9e-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bb9e-109">See also</span></span>

- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.ClaimSet>
- [<span data-ttu-id="2bb9e-110">ID モデルを使用したクレームと承認の管理</span><span class="sxs-lookup"><span data-stu-id="2bb9e-110">Managing Claims and Authorization with the Identity Model</span></span>](managing-claims-and-authorization-with-the-identity-model.md)
