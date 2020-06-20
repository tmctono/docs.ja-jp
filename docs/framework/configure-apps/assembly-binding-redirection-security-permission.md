---
title: アセンブリ バインディング リダイレクトのセキュリティ アクセス許可
description: .NET のアプリケーション構成ファイルで、明示的なアセンブリバインドリダイレクトに必要なセキュリティアクセス許可について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
ms.openlocfilehash: a8596bcac4efb0aea07efcfde6726d8bbf148c24
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105091"
---
# <a name="assembly-binding-redirection-security-permission"></a><span data-ttu-id="f35ee-103">アセンブリ バインディング リダイレクトのセキュリティ アクセス許可</span><span class="sxs-lookup"><span data-stu-id="f35ee-103">Assembly Binding Redirection Security Permission</span></span>
<span data-ttu-id="f35ee-104">アプリケーション構成ファイルで明示的にアセンブリ バインディングをリダイレクトするには、セキュリティ アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="f35ee-104">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="f35ee-105">これは、.NET Framework アセンブリおよびサードパーティ製アセンブリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f35ee-105">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="f35ee-106">権限は、にフラグを設定することによって付与され <xref:System.Security.Permissions.SecurityPermissionFlag> <xref:System.Security.Permissions.SecurityPermission> ます。</span><span class="sxs-lookup"><span data-stu-id="f35ee-106">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="f35ee-107">マネージアセンブリには、既定ではアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="f35ee-107">Managed assemblies have no permissions by default.</span></span>  
  
 <span data-ttu-id="f35ee-108">セキュリティアクセス許可は、信頼済みゾーン (ローカルコンピューター) およびイントラネットゾーンで実行されているアプリケーションに付与されます。</span><span class="sxs-lookup"><span data-stu-id="f35ee-108">The security permission is granted to applications running in the Trusted Zone (local machine) and Intranet Zone.</span></span> <span data-ttu-id="f35ee-109">インターネットゾーンで実行されているアプリケーションは、アセンブリバインディングのリダイレクトを実行できません。</span><span class="sxs-lookup"><span data-stu-id="f35ee-109">Applications running in the Internet Zone are strictly prohibited from performing assembly binding redirection.</span></span>  
  
 <span data-ttu-id="f35ee-110">アセンブリのリダイレクトが、コンポーネントの発行者によって制御される発行者ポリシーファイル、または管理者によって制御されるコンピューター構成ファイルで実行される場合、このアクセス許可は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f35ee-110">The permission is not required if assembly redirection is performed in a publisher policy file that is controlled by the component publisher, or in the machine configuration file that is controlled by the administrator.</span></span> <span data-ttu-id="f35ee-111">ただし、アプリケーションでアプリケーション構成ファイルの要素を使用して発行者ポリシーを明示的に無視するには、アプリケーションのアクセス許可が必要です [\<publisherPolicy apply="no"/>](./file-schema/runtime/publisherpolicy-element.md) 。</span><span class="sxs-lookup"><span data-stu-id="f35ee-111">However, the permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](./file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span>  
  
 <span data-ttu-id="f35ee-112">次の表は、 **bindingredirects**フラグの既定のセキュリティ設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="f35ee-112">The following table shows the default security settings for the **BindingRedirects** flag.</span></span>  
  
|<span data-ttu-id="f35ee-113">ゾーン</span><span class="sxs-lookup"><span data-stu-id="f35ee-113">Zone</span></span>|<span data-ttu-id="f35ee-114">BindingRedirects フラグの設定</span><span class="sxs-lookup"><span data-stu-id="f35ee-114">BindingRedirects flag setting</span></span>|  
|----------|-----------------------------------|  
|<span data-ttu-id="f35ee-115">信頼済みゾーン (ローカルコンピューター)</span><span class="sxs-lookup"><span data-stu-id="f35ee-115">Trusted Zone (local machine)</span></span>|<span data-ttu-id="f35ee-116">**ON**</span><span class="sxs-lookup"><span data-stu-id="f35ee-116">**ON**</span></span>|  
|<span data-ttu-id="f35ee-117">イントラネット ゾーン</span><span class="sxs-lookup"><span data-stu-id="f35ee-117">Intranet Zone</span></span>|<span data-ttu-id="f35ee-118">**ON**</span><span class="sxs-lookup"><span data-stu-id="f35ee-118">**ON**</span></span>|  
|<span data-ttu-id="f35ee-119">インターネット ゾーン</span><span class="sxs-lookup"><span data-stu-id="f35ee-119">Internet Zone</span></span>|<span data-ttu-id="f35ee-120">**OFF**</span><span class="sxs-lookup"><span data-stu-id="f35ee-120">**OFF**</span></span>|  
|<span data-ttu-id="f35ee-121">信頼されていないゾーン</span><span class="sxs-lookup"><span data-stu-id="f35ee-121">Untrusted zones</span></span>|<span data-ttu-id="f35ee-122">**OFF**</span><span class="sxs-lookup"><span data-stu-id="f35ee-122">**OFF**</span></span>|  
  
 <span data-ttu-id="f35ee-123">管理者は、これらのセキュリティ設定を変更して、特定のコンピューター上の特定のシナリオをサポートまたは制限することができます。</span><span class="sxs-lookup"><span data-stu-id="f35ee-123">An administrator can change these security settings to support or restrict specific scenarios on a given computer.</span></span> <span data-ttu-id="f35ee-124">既定値から**Bindingredirects**フラグ設定を変更するためのツールはありません。管理者は、ユーザーのコンピューターの Security.config ファイルを手動で編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f35ee-124">There are no tools for changing the **BindingRedirects** flag setting from the default; an administrator must manually edit the Security.config file on a user's computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f35ee-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="f35ee-125">See also</span></span>

- <span data-ttu-id="f35ee-126">[発行者ポリシー ファイルと side-by-side 実行](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f35ee-126">[Publisher Policy Files and Side-by-Side Execution](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))</span></span>
- [<span data-ttu-id="f35ee-127">方法: 自動バインディング リダイレクトを有効/無効にする</span><span class="sxs-lookup"><span data-stu-id="f35ee-127">How to: Enable and Disable Automatic Binding Redirection</span></span>](how-to-enable-and-disable-automatic-binding-redirection.md)
- [<span data-ttu-id="f35ee-128">Side-by-side 実行</span><span class="sxs-lookup"><span data-stu-id="f35ee-128">Side-by-Side Execution</span></span>](../deployment/side-by-side-execution.md)
