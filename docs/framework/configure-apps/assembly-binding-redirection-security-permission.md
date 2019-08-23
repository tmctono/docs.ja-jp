---
title: アセンブリ バインディング リダイレクトのセキュリティ アクセス許可
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
ms.openlocfilehash: b59689e78f901637674c0a1df28ed74411e8e7c7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921374"
---
# <a name="assembly-binding-redirection-security-permission"></a><span data-ttu-id="223e0-102">アセンブリ バインディング リダイレクトのセキュリティ アクセス許可</span><span class="sxs-lookup"><span data-stu-id="223e0-102">Assembly Binding Redirection Security Permission</span></span>
<span data-ttu-id="223e0-103">アプリケーション構成ファイルで明示的にアセンブリ バインディングをリダイレクトするには、セキュリティ アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="223e0-103">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="223e0-104">これは、.NET Framework アセンブリおよびサードパーティ製アセンブリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="223e0-104">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="223e0-105">権限は、 <xref:System.Security.Permissions.SecurityPermissionFlag> <xref:System.Security.Permissions.SecurityPermission>にフラグを設定することによって付与されます。</span><span class="sxs-lookup"><span data-stu-id="223e0-105">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="223e0-106">マネージアセンブリには、既定ではアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="223e0-106">Managed assemblies have no permissions by default.</span></span>  
  
 <span data-ttu-id="223e0-107">セキュリティアクセス許可は、信頼済みゾーン (ローカルコンピューター) およびイントラネットゾーンで実行されているアプリケーションに付与されます。</span><span class="sxs-lookup"><span data-stu-id="223e0-107">The security permission is granted to applications running in the Trusted Zone (local machine) and Intranet Zone.</span></span> <span data-ttu-id="223e0-108">インターネットゾーンで実行されているアプリケーションは、アセンブリバインディングのリダイレクトを実行できません。</span><span class="sxs-lookup"><span data-stu-id="223e0-108">Applications running in the Internet Zone are strictly prohibited from performing assembly binding redirection.</span></span>  
  
 <span data-ttu-id="223e0-109">コンポーネントの発行元によって制御される発行者ポリシー ファイル、または管理者によって制御されるコンピューターの構成ファイルにアセンブリのリダイレクトを実行する場合は、アクセス許可は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="223e0-109">The permission is not required if assembly redirection is performed in a publisher policy file that is controlled by the component publisher, or in the machine configuration file that is controlled by the administrator.</span></span> <span data-ttu-id="223e0-110">ただし、アクセス許可が明示的にポリシーを使用してパブリッシャーを無視するアプリケーションに必要な[ \<publisherPolicy apply="no"/>](./file-schema/runtime/publisherpolicy-element.md)アプリケーション構成ファイル内の要素。</span><span class="sxs-lookup"><span data-stu-id="223e0-110">However, the permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](./file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span>  
  
 <span data-ttu-id="223e0-111">次の表は、Bindingredirects フラグの既定のセキュリティ設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="223e0-111">The following table shows the default security settings for the **BindingRedirects** flag.</span></span>  
  
|<span data-ttu-id="223e0-112">ゾーン</span><span class="sxs-lookup"><span data-stu-id="223e0-112">Zone</span></span>|<span data-ttu-id="223e0-113">BindingRedirects フラグの設定</span><span class="sxs-lookup"><span data-stu-id="223e0-113">BindingRedirects flag setting</span></span>|  
|----------|-----------------------------------|  
|<span data-ttu-id="223e0-114">信頼済みゾーン (ローカルコンピューター)</span><span class="sxs-lookup"><span data-stu-id="223e0-114">Trusted Zone (local machine)</span></span>|<span data-ttu-id="223e0-115">**ON**</span><span class="sxs-lookup"><span data-stu-id="223e0-115">**ON**</span></span>|  
|<span data-ttu-id="223e0-116">イントラネットゾーン</span><span class="sxs-lookup"><span data-stu-id="223e0-116">Intranet Zone</span></span>|<span data-ttu-id="223e0-117">**ON**</span><span class="sxs-lookup"><span data-stu-id="223e0-117">**ON**</span></span>|  
|<span data-ttu-id="223e0-118">インターネット ゾーン</span><span class="sxs-lookup"><span data-stu-id="223e0-118">Internet Zone</span></span>|<span data-ttu-id="223e0-119">**OFF**</span><span class="sxs-lookup"><span data-stu-id="223e0-119">**OFF**</span></span>|  
|<span data-ttu-id="223e0-120">信頼されていないゾーン</span><span class="sxs-lookup"><span data-stu-id="223e0-120">Untrusted zones</span></span>|<span data-ttu-id="223e0-121">**OFF**</span><span class="sxs-lookup"><span data-stu-id="223e0-121">**OFF**</span></span>|  
  
 <span data-ttu-id="223e0-122">管理者は、これらのセキュリティ設定を変更して、特定のコンピューター上の特定のシナリオをサポートまたは制限することができます。</span><span class="sxs-lookup"><span data-stu-id="223e0-122">An administrator can change these security settings to support or restrict specific scenarios on a given computer.</span></span> <span data-ttu-id="223e0-123">既定値から**Bindingredirects**フラグ設定を変更するためのツールはありません。管理者は、ユーザーのコンピューター上のセキュリティ .config ファイルを手動で編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="223e0-123">There are no tools for changing the **BindingRedirects** flag setting from the default; an administrator must manually edit the Security.config file on a user's computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="223e0-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="223e0-124">See also</span></span>

- <span data-ttu-id="223e0-125">[発行者ポリシーファイルと Side-by-side 実行](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="223e0-125">[Publisher Policy Files and Side-by-Side Execution](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))</span></span>
- [<span data-ttu-id="223e0-126">方法: 自動バインディング リダイレクトを有効/無効にする</span><span class="sxs-lookup"><span data-stu-id="223e0-126">How to: Enable and Disable Automatic Binding Redirection</span></span>](how-to-enable-and-disable-automatic-binding-redirection.md)
- [<span data-ttu-id="223e0-127">side-by-side 実行</span><span class="sxs-lookup"><span data-stu-id="223e0-127">Side-by-Side Execution</span></span>](../deployment/side-by-side-execution.md)
