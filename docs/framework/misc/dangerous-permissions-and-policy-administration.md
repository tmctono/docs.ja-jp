---
title: 危険なアクセス許可とポリシー管理
ms.date: 03/30/2017
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f79fd3e0678fc0bba0d3074904f9ce9460fc6c20
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910927"
---
# <a name="dangerous-permissions-and-policy-administration"></a><span data-ttu-id="95f3e-102">危険なアクセス許可とポリシー管理</span><span class="sxs-lookup"><span data-stu-id="95f3e-102">Dangerous Permissions and Policy Administration</span></span>
<span data-ttu-id="95f3e-103">.NET Framework がアクセス許可を提供する保護された操作のいくつかで、セキュリティ システムが回避されてしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="95f3e-103">Several of the protected operations for which the .NET Framework provides permissions can potentially allow the security system to be circumvented.</span></span> <span data-ttu-id="95f3e-104">これらの危険なアクセス許可は信頼できるコードにのみ付与し、その付与は必要な場合に限る必要があります。</span><span class="sxs-lookup"><span data-stu-id="95f3e-104">These dangerous permissions should be given only to trustworthy code, and then only as necessary.</span></span> <span data-ttu-id="95f3e-105">これらのアクセス許可が付与されると、通常、悪意のあるコードに対する防御策はありません。</span><span class="sxs-lookup"><span data-stu-id="95f3e-105">There is usually no defense against malicious code if it is granted these permissions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="95f3e-106">.NET Framework 4 では、.NET Framework セキュリティモデルと用語に重要な変更が加えられています。</span><span class="sxs-lookup"><span data-stu-id="95f3e-106">In the .NET Framework 4, there have been important changes to the .NET Framework security model and terminology.</span></span> <span data-ttu-id="95f3e-107">これらの変更の詳細については、「[セキュリティの変更](../../../docs/framework/security/security-changes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95f3e-107">For more information about these changes, see [Security Changes](../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="95f3e-108">危険なアクセス許可については、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="95f3e-108">The dangerous permissions are explained in the following table.</span></span>  
  
|<span data-ttu-id="95f3e-109">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="95f3e-109">Permission</span></span>|<span data-ttu-id="95f3e-110">潜在的なリスク</span><span class="sxs-lookup"><span data-stu-id="95f3e-110">Potential risk</span></span>|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|<span data-ttu-id="95f3e-111">マネージド コードからアンマネージド コードを呼び出せるようにしますが、これは大抵リスクを伴います。</span><span class="sxs-lookup"><span data-stu-id="95f3e-111">Allows managed code to call into unmanaged code, which is often dangerous.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|<span data-ttu-id="95f3e-112">検証なしで、コードは何でも実行できます。</span><span class="sxs-lookup"><span data-stu-id="95f3e-112">Without verification, the code can do anything.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|<span data-ttu-id="95f3e-113">無効な証拠でセキュリティ ポリシーをかいくぐることができます。</span><span class="sxs-lookup"><span data-stu-id="95f3e-113">Invalidated evidence can fool security policy.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|<span data-ttu-id="95f3e-114">セキュリティ ポリシーを変更する機能によって、セキュリティを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="95f3e-114">The ability to modify security policy can disable security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|<span data-ttu-id="95f3e-115">シリアル化を使用して、ユーザー補助機能のメカニズムを回避できます。</span><span class="sxs-lookup"><span data-stu-id="95f3e-115">The use of serialization can circumvent accessibility mechanisms.</span></span> <span data-ttu-id="95f3e-116">詳細については、「 [セキュリティとシリアル化](../../../docs/framework/misc/security-and-serialization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95f3e-116">For details, see [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md).</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|<span data-ttu-id="95f3e-117">現行プリンシパルを設定する機能によって、ロール ベースのセキュリティを欺くことができます。</span><span class="sxs-lookup"><span data-stu-id="95f3e-117">The ability to set the current principal can trick role-based security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|<span data-ttu-id="95f3e-118">スレッドにはセキュリティ状態が関連付けられているため、スレッドの操作は危険です。</span><span class="sxs-lookup"><span data-stu-id="95f3e-118">Manipulation of threads is dangerous because of the security state associated with threads.</span></span>|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|<span data-ttu-id="95f3e-119">プライベート メンバーを使用して、ユーザー補助機能のメカニズムを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="95f3e-119">Can use private members to defeat accessibility mechanisms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="95f3e-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="95f3e-120">See also</span></span>

- [<span data-ttu-id="95f3e-121">安全なコーディングのガイドライン</span><span class="sxs-lookup"><span data-stu-id="95f3e-121">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
