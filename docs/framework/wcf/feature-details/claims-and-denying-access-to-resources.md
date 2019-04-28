---
title: リソースへのアクセスのクレームと拒否
ms.date: 03/30/2017
helpviewer_keywords:
- claims [WCF], denying access to resources
ms.assetid: 145ebb41-680e-4256-b14c-1efb4af1e982
ms.openlocfilehash: 4f48c59090579f4b451f615bb792a4dcb73f6df5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857596"
---
# <a name="claims-and-denying-access-to-resources"></a><span data-ttu-id="fbdac-102">リソースへのアクセスのクレームと拒否</span><span class="sxs-lookup"><span data-stu-id="fbdac-102">Claims and Denying Access to Resources</span></span>
<span data-ttu-id="fbdac-103">Windows Communication Foundation (WCF) は、クレーム ベースの承認メカニズムをサポートします。</span><span class="sxs-lookup"><span data-stu-id="fbdac-103">Windows Communication Foundation (WCF) supports a claims-based authorization mechanism.</span></span> <span data-ttu-id="fbdac-104">クレームの有無に応じてリソースへのアクセスが許可されるばかりでなく、クレームの有無に応じてリソースへのアクセスがシステムによって拒否される場合もよくあります。</span><span class="sxs-lookup"><span data-stu-id="fbdac-104">As well as allowing access to resources based on the presence of claims, systems often deny access to resources based on the presence of claims.</span></span> <span data-ttu-id="fbdac-105">このようなシステムでは、アクセスが許可された要求を探す前に、アクセスが拒否されたクレームの <xref:System.IdentityModel.Policy.AuthorizationContext> を調べる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbdac-105">Such systems should examine the <xref:System.IdentityModel.Policy.AuthorizationContext> for claims that result in access being denied before looking for claims that result in access being allowed.</span></span>  
  
 <span data-ttu-id="fbdac-106">たとえば、`Age` 型、<xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> 権限、`Under 21` リソース値というクレームを持つ任意のユーザーに対してリソースへのアクセスを拒否し、ID が `Name` 型、<xref:System.IdentityModel.Claims.Rights.Identity%2A> 権限、`Mallory` リソース値というクレームを持っている場合にのみ、リソースへのアクセスを許可するとします。</span><span class="sxs-lookup"><span data-stu-id="fbdac-106">For example, a system might deny access to a resource to anyone who has a claim with a type of `Age`, a right of <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>, and a resource value of `Under 21` only when that identity also has a claim of type `Name`, a right of <xref:System.IdentityModel.Claims.Rights.Identity%2A>, and a resource value of `Mallory`.</span></span> <span data-ttu-id="fbdac-107">言い換えると、年齢が 21 歳以下の任意のユーザーはシステムによってアクセスが拒否され、名前が Mallory である任意のユーザーにはアクセスが許可されるようにします。</span><span class="sxs-lookup"><span data-stu-id="fbdac-107">Put another way, the system denies access to anyone who is under 21 years old and grants access when the name is Mallory.</span></span> <span data-ttu-id="fbdac-108">この意味を正しく実装するには、`Age` クレームを最初に探して、ユーザーが 21 歳以下であるかどうかを判断することが重要です。</span><span class="sxs-lookup"><span data-stu-id="fbdac-108">To correctly implement this semantic, it is important to look for the `Age` claim first and determine whether the age is under 21 years old.</span></span> <span data-ttu-id="fbdac-109">そうしないと、Mallory が 21 歳以下である場合、このリソースには、`Name` クレームのみに基づいてアクセスが許可されてしまいます。</span><span class="sxs-lookup"><span data-stu-id="fbdac-109">Otherwise, if Mallory is under 21, then the resource may be granted access solely on the basis of the `Name` claim.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbdac-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbdac-110">See also</span></span>

- [<span data-ttu-id="fbdac-111">ID モデルを使用したクレームと承認の管理</span><span class="sxs-lookup"><span data-stu-id="fbdac-111">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
- [<span data-ttu-id="fbdac-112">クレームとトークン</span><span class="sxs-lookup"><span data-stu-id="fbdac-112">Claims and Tokens</span></span>](../../../../docs/framework/wcf/feature-details/claims-and-tokens.md)
