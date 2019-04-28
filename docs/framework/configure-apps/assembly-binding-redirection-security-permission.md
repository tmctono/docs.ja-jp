---
title: アセンブリ バインディング リダイレクトのセキュリティ アクセス許可
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
ms.openlocfilehash: ba4e7e790860696f4489e9ef7b73bddcb8c4e399
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705429"
---
# <a name="assembly-binding-redirection-security-permission"></a><span data-ttu-id="9808b-102">アセンブリ バインディング リダイレクトのセキュリティ アクセス許可</span><span class="sxs-lookup"><span data-stu-id="9808b-102">Assembly Binding Redirection Security Permission</span></span>
<span data-ttu-id="9808b-103">アプリケーション構成ファイルで明示的にアセンブリ バインディングをリダイレクトするには、セキュリティ アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="9808b-103">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="9808b-104">これは、.NET Framework アセンブリおよびサードパーティ製アセンブリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9808b-104">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="9808b-105">許可を設定して、<xref:System.Security.Permissions.SecurityPermissionFlag>にフラグ、<xref:System.Security.Permissions.SecurityPermission>します。</span><span class="sxs-lookup"><span data-stu-id="9808b-105">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="9808b-106">マネージ アセンブリは、既定でアクセス許可を持っていません。</span><span class="sxs-lookup"><span data-stu-id="9808b-106">Managed assemblies have no permissions by default.</span></span>  
  
 <span data-ttu-id="9808b-107">セキュリティ アクセス許可は、イントラネット ゾーン、信頼済みゾーン (ローカル コンピューター) で実行されるアプリケーションに付与されます。</span><span class="sxs-lookup"><span data-stu-id="9808b-107">The security permission is granted to applications running in the Trusted Zone (local machine) and Intranet Zone.</span></span> <span data-ttu-id="9808b-108">インターネット ゾーンで実行されているアプリケーションが、アセンブリ バインド リダイレクトを実行するから固く禁止されています。</span><span class="sxs-lookup"><span data-stu-id="9808b-108">Applications running in the Internet Zone are strictly prohibited from performing assembly binding redirection.</span></span>  
  
 <span data-ttu-id="9808b-109">コンポーネントの発行元によって制御される発行者ポリシー ファイル、または管理者によって制御されるコンピューターの構成ファイルにアセンブリのリダイレクトを実行する場合は、アクセス許可は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9808b-109">The permission is not required if assembly redirection is performed in a publisher policy file that is controlled by the component publisher, or in the machine configuration file that is controlled by the administrator.</span></span> <span data-ttu-id="9808b-110">ただし、アクセス許可が明示的にポリシーを使用してパブリッシャーを無視するアプリケーションに必要な[ \<publisherPolicy apply="no"/>](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)アプリケーション構成ファイル内の要素。</span><span class="sxs-lookup"><span data-stu-id="9808b-110">However, the permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span>  
  
 <span data-ttu-id="9808b-111">次の表は、既定のセキュリティ設定、 **BindingRedirects**フラグ。</span><span class="sxs-lookup"><span data-stu-id="9808b-111">The following table shows the default security settings for the **BindingRedirects** flag.</span></span>  
  
|<span data-ttu-id="9808b-112">ゾーン</span><span class="sxs-lookup"><span data-stu-id="9808b-112">Zone</span></span>|<span data-ttu-id="9808b-113">BindingRedirects フラグの設定</span><span class="sxs-lookup"><span data-stu-id="9808b-113">BindingRedirects flag setting</span></span>|  
|----------|-----------------------------------|  
|<span data-ttu-id="9808b-114">信頼済みゾーン (ローカル コンピューター)</span><span class="sxs-lookup"><span data-stu-id="9808b-114">Trusted Zone (local machine)</span></span>|<span data-ttu-id="9808b-115">**ON**</span><span class="sxs-lookup"><span data-stu-id="9808b-115">**ON**</span></span>|  
|<span data-ttu-id="9808b-116">イントラネット ゾーン</span><span class="sxs-lookup"><span data-stu-id="9808b-116">Intranet Zone</span></span>|<span data-ttu-id="9808b-117">**ON**</span><span class="sxs-lookup"><span data-stu-id="9808b-117">**ON**</span></span>|  
|<span data-ttu-id="9808b-118">インターネット ゾーン</span><span class="sxs-lookup"><span data-stu-id="9808b-118">Internet Zone</span></span>|<span data-ttu-id="9808b-119">**OFF**</span><span class="sxs-lookup"><span data-stu-id="9808b-119">**OFF**</span></span>|  
|<span data-ttu-id="9808b-120">信頼されていないゾーン</span><span class="sxs-lookup"><span data-stu-id="9808b-120">Untrusted zones</span></span>|<span data-ttu-id="9808b-121">**OFF**</span><span class="sxs-lookup"><span data-stu-id="9808b-121">**OFF**</span></span>|  
  
 <span data-ttu-id="9808b-122">管理者は、これらのセキュリティ設定をサポートしたり、特定のコンピューターで特定のシナリオの制限を変更できます。</span><span class="sxs-lookup"><span data-stu-id="9808b-122">An administrator can change these security settings to support or restrict specific scenarios on a given computer.</span></span> <span data-ttu-id="9808b-123">変更するためのツールはありません、 **BindingRedirects**フラグ設定から既定では、管理者はユーザーのコンピューターに Security.config ファイルを編集する必要があります手動でします。</span><span class="sxs-lookup"><span data-stu-id="9808b-123">There are no tools for changing the **BindingRedirects** flag setting from the default; an administrator must manually edit the Security.config file on a user's computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9808b-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="9808b-124">See also</span></span>

- <span data-ttu-id="9808b-125">[発行者ポリシー ファイルとサイド バイ サイドで実行](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9808b-125">[Publisher Policy Files and Side-by-Side Execution](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))</span></span>
- [<span data-ttu-id="9808b-126">方法: 自動バインディング リダイレクトを有効/無効にする</span><span class="sxs-lookup"><span data-stu-id="9808b-126">How to: Enable and Disable Automatic Binding Redirection</span></span>](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)
- [<span data-ttu-id="9808b-127">side-by-side 実行</span><span class="sxs-lookup"><span data-stu-id="9808b-127">Side-by-Side Execution</span></span>](../../../docs/framework/deployment/side-by-side-execution.md)
