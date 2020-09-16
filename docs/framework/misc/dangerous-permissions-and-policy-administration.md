---
title: 危険なアクセス許可とポリシー管理
description: 「.NET でのさまざまな危険なアクセス許可へのリンク」を参照してください。 これらのアクセス許可は、信頼できるコードにのみ付与し、必要な場合にのみ指定する必要があります。
ms.date: 03/30/2017
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
ms.openlocfilehash: a2f4469590fea38924430b07eaf20d49f4dc46e9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556942"
---
# <a name="dangerous-permissions-and-policy-administration"></a><span data-ttu-id="f2e9c-104">危険なアクセス許可とポリシー管理</span><span class="sxs-lookup"><span data-stu-id="f2e9c-104">Dangerous Permissions and Policy Administration</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="f2e9c-105">.NET Framework がアクセス許可を提供する保護された操作のいくつかで、セキュリティ システムが回避されてしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f2e9c-105">Several of the protected operations for which the .NET Framework provides permissions can potentially allow the security system to be circumvented.</span></span> <span data-ttu-id="f2e9c-106">これらの危険なアクセス許可は信頼できるコードにのみ付与し、その付与は必要な場合に限る必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2e9c-106">These dangerous permissions should be given only to trustworthy code, and then only as necessary.</span></span> <span data-ttu-id="f2e9c-107">これらのアクセス許可が付与されると、通常、悪意のあるコードに対する防御策はありません。</span><span class="sxs-lookup"><span data-stu-id="f2e9c-107">There is usually no defense against malicious code if it is granted these permissions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2e9c-108">.NET Framework 4 では、.NET Framework セキュリティモデルと用語に重要な変更が加えられています。</span><span class="sxs-lookup"><span data-stu-id="f2e9c-108">In the .NET Framework 4, there have been important changes to the .NET Framework security model and terminology.</span></span> <span data-ttu-id="f2e9c-109">これらの変更の詳細については、「 [セキュリティの変更](/previous-versions/dotnet/framework/security/security-changes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2e9c-109">For more information about these changes, see [Security Changes](/previous-versions/dotnet/framework/security/security-changes).</span></span>  
  
 <span data-ttu-id="f2e9c-110">危険なアクセス許可については、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="f2e9c-110">The dangerous permissions are explained in the following table.</span></span>  
  
|<span data-ttu-id="f2e9c-111">権限</span><span class="sxs-lookup"><span data-stu-id="f2e9c-111">Permission</span></span>|<span data-ttu-id="f2e9c-112">潜在的なリスク</span><span class="sxs-lookup"><span data-stu-id="f2e9c-112">Potential risk</span></span>|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|<span data-ttu-id="f2e9c-113">マネージド コードからアンマネージド コードを呼び出せるようにしますが、これは大抵リスクを伴います。</span><span class="sxs-lookup"><span data-stu-id="f2e9c-113">Allows managed code to call into unmanaged code, which is often dangerous.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|<span data-ttu-id="f2e9c-114">検証なしで、コードは何でも実行できます。</span><span class="sxs-lookup"><span data-stu-id="f2e9c-114">Without verification, the code can do anything.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|<span data-ttu-id="f2e9c-115">無効な証拠でセキュリティ ポリシーをかいくぐることができます。</span><span class="sxs-lookup"><span data-stu-id="f2e9c-115">Invalidated evidence can fool security policy.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|<span data-ttu-id="f2e9c-116">セキュリティ ポリシーを変更する機能によって、セキュリティを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="f2e9c-116">The ability to modify security policy can disable security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|<span data-ttu-id="f2e9c-117">シリアル化を使用して、ユーザー補助機能のメカニズムを回避できます。</span><span class="sxs-lookup"><span data-stu-id="f2e9c-117">The use of serialization can circumvent accessibility mechanisms.</span></span> <span data-ttu-id="f2e9c-118">詳細については、「 [セキュリティとシリアル化](security-and-serialization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2e9c-118">For details, see [Security and Serialization](security-and-serialization.md).</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|<span data-ttu-id="f2e9c-119">現行プリンシパルを設定する機能によって、ロール ベースのセキュリティを欺くことができます。</span><span class="sxs-lookup"><span data-stu-id="f2e9c-119">The ability to set the current principal can trick role-based security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|<span data-ttu-id="f2e9c-120">スレッドにはセキュリティ状態が関連付けられているため、スレッドの操作は危険です。</span><span class="sxs-lookup"><span data-stu-id="f2e9c-120">Manipulation of threads is dangerous because of the security state associated with threads.</span></span>|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|<span data-ttu-id="f2e9c-121">プライベート メンバーを使用して、ユーザー補助機能のメカニズムを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f2e9c-121">Can use private members to defeat accessibility mechanisms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f2e9c-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2e9c-122">See also</span></span>

- [<span data-ttu-id="f2e9c-123">安全なコーディングのガイドライン</span><span class="sxs-lookup"><span data-stu-id="f2e9c-123">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
