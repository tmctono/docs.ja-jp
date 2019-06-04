---
title: 部分信頼コードからのライブラリの使用
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], partially trusted code
- partially trusted code
- partial trust
- AllowPartiallyTrustedCallersAttribute attribute
- code access security, partially trusted code
- APTCA
ms.assetid: dd66cd4c-b087-415f-9c3e-94e3a1835f74
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6d858ef4c2f70c55b0a36e845f90d9a8e08f5e2d
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66487824"
---
# <a name="using-libraries-from-partially-trusted-code"></a><span data-ttu-id="68ffe-102">部分信頼コードからのライブラリの使用</span><span class="sxs-lookup"><span data-stu-id="68ffe-102">Using Libraries from Partially Trusted Code</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
> [!NOTE]
>  <span data-ttu-id="68ffe-103">このトピックでは、厳密な名前付きアセンブリの動作に対処しにのみ適用されます[レベル 1](../../../docs/framework/misc/security-transparent-code-level-1.md)アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="68ffe-103">This topic addresses the behavior of strong-named assemblies and applies only to [Level 1](../../../docs/framework/misc/security-transparent-code-level-1.md) assemblies.</span></span> <span data-ttu-id="68ffe-104">[透過的セキュリティ コード、レベル 2](../../../docs/framework/misc/security-transparent-code-level-2.md)厳密な名前でアセンブリ、.NET Framework 4 以降を受けません。</span><span class="sxs-lookup"><span data-stu-id="68ffe-104">[Security-Transparent Code, Level 2](../../../docs/framework/misc/security-transparent-code-level-2.md) assemblies in the .NET Framework 4 or later are not affected by strong names.</span></span> <span data-ttu-id="68ffe-105">セキュリティ システムへの変更の詳細については、次を参照してください。[セキュリティ変更](../../../docs/framework/security/security-changes.md)します。</span><span class="sxs-lookup"><span data-stu-id="68ffe-105">For more information about changes to the security system, see [Security Changes](../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="68ffe-106">ホストまたはサンドボックスから不完全な信頼を受けているアプリケーションは、ライブラリの作成者が <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 属性を使用して具体的に許可しない限り、共有マネージド ライブラリを呼び出せません。</span><span class="sxs-lookup"><span data-stu-id="68ffe-106">Applications that receive less than full trust from their host or sandbox are not allowed to call shared managed libraries unless the library writer specifically allows them to through the use of the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute.</span></span> <span data-ttu-id="68ffe-107">そのため、アプリケーションの作成者は、ライブラリによっては部分的に信頼されたコンテキストから使用できないことを認識する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68ffe-107">Therefore, application writers must be aware that some libraries will not be available to them from a partially trusted context.</span></span> <span data-ttu-id="68ffe-108">既定では、すべてのコードで実行する部分的に信頼された[サンド ボックス](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)ではありません。 完全信頼アセンブリの一覧が部分的に信頼されているとします。</span><span class="sxs-lookup"><span data-stu-id="68ffe-108">By default, all code that executes in a partial-trust [sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md) and is not in the list of full-trust assemblies is partially trusted.</span></span> <span data-ttu-id="68ffe-109">部分的に信頼されたコンテキストからコードを実行する、または部分的に信頼されたコードによってコードが呼び出されることはないと考えられる場合は、このセクションの情報を考慮する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="68ffe-109">If you do not expect your code to be executed from a partially trusted context or to be called by partially trusted code, you do not have to be concerned about the information in this section.</span></span> <span data-ttu-id="68ffe-110">ただし、部分的に信頼されたコードと対話する必要があるコード、または部分的に信頼されたコンテキストから操作するコードを記述する場合は、次の要因を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68ffe-110">However, if you write code that must interact with partially trusted code or operate from a partially trusted context, you should consider the following factors:</span></span>  
  
- <span data-ttu-id="68ffe-111">ライブラリは、複数のアプリケーションで共有するために、厳密な名前で署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68ffe-111">Libraries must be signed with a strong name in order to be shared by multiple applications.</span></span> <span data-ttu-id="68ffe-112">厳密な名前を使用すると、コードをグローバル アセンブリ キャッシュに配置したり、サンドボックス化する <xref:System.AppDomain> の完全信頼一覧に追加したりできます。また、コンシューマーは、実際にあなたが発信する特定のモバイル コードを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="68ffe-112">Strong names allow your code to be placed in the global assembly cache or added to the full-trust list of a sandboxing <xref:System.AppDomain>, and allow consumers to verify that a particular piece of mobile code actually originates from you.</span></span>  
  
- <span data-ttu-id="68ffe-113">既定では、厳密な名前[レベル 1](../../../docs/framework/misc/security-transparent-code-level-1.md)共有ライブラリを暗黙的な実行[LinkDemand](../../../docs/framework/misc/link-demands.md)完全でライブラリの作成者が何もすることを自動的に信頼します。</span><span class="sxs-lookup"><span data-stu-id="68ffe-113">By default, strong-named [Level 1](../../../docs/framework/misc/security-transparent-code-level-1.md) shared libraries perform an implicit [LinkDemand](../../../docs/framework/misc/link-demands.md) for full trust automatically, without the library writer having to do anything.</span></span>  
  
- <span data-ttu-id="68ffe-114">呼び出し元に完全な信頼がないにもかかわらず、このようなライブラリを呼び出そうとする場合、ランタイムは <xref:System.Security.SecurityException> をスローします。これにより、呼び出し元はライブラリにリンクできなくなります。</span><span class="sxs-lookup"><span data-stu-id="68ffe-114">If a caller does not have full trust but still tries to call such a library, the runtime throws a <xref:System.Security.SecurityException> and the caller is not allowed to link to the library.</span></span>  
  
- <span data-ttu-id="68ffe-115">自動を無効にするには**LinkDemand**からスローされる例外を防ぐため、配置することができます、 **AllowPartiallyTrustedCallersAttribute**共有アセンブリのスコープに属性ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="68ffe-115">In order to disable the automatic **LinkDemand** and prevent the exception from being thrown, you can place the **AllowPartiallyTrustedCallersAttribute** attribute on the assembly scope of a shared library.</span></span> <span data-ttu-id="68ffe-116">この属性により、部分的に信頼されたマネージド コードからライブラリを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="68ffe-116">This attribute allows your libraries to be called from partially trusted managed code.</span></span>  
  
- <span data-ttu-id="68ffe-117">それでも、この属性を持つライブラリへのアクセスが許可されている部分的に信頼されたコードは、<xref:System.AppDomain> が定義する追加の制約を受けます。</span><span class="sxs-lookup"><span data-stu-id="68ffe-117">Partially trusted code that is granted access to a library with this attribute is still subject to further restrictions defined by the <xref:System.AppDomain>.</span></span>  
  
- <span data-ttu-id="68ffe-118">部分的に信頼されたコードがないライブラリを呼び出すことのプログラムによる方法はありません、 **AllowPartiallyTrustedCallersAttribute**属性。</span><span class="sxs-lookup"><span data-stu-id="68ffe-118">There is no programmatic way for partially trusted code to call a library that does not have the **AllowPartiallyTrustedCallersAttribute** attribute.</span></span>  
  
 <span data-ttu-id="68ffe-119">特定のアプリケーションをプライベートなライブラリは、厳密な名前を必要としない、または**AllowPartiallyTrustedCallersAttribute**属性し、悪意のあるコード、アプリケーションの外部から参照できません。</span><span class="sxs-lookup"><span data-stu-id="68ffe-119">Libraries that are private to a specific application do not require a strong name or the **AllowPartiallyTrustedCallersAttribute** attribute and cannot be referenced by potentially malicious code outside the application.</span></span> <span data-ttu-id="68ffe-120">このようなコードは、部分的に信頼されたモバイル コードの意図的または意図的でない誤使用から保護されています。開発者は追加で何かをする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="68ffe-120">Such code is protected against intentional or unintentional misuse by partially trusted mobile code without the developer having to do anything extra.</span></span>  
  
 <span data-ttu-id="68ffe-121">次の種類のコードについて、部分的に信頼されたコードによる使用を明示的に有効にすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="68ffe-121">You should consider explicitly enabling use by partially trusted code for the following types of code:</span></span>  
  
- <span data-ttu-id="68ffe-122">セキュリティの脆弱性を入念にテストされているし、で説明されているガイドラインに準拠しているがコードを[安全なコーディングのガイドライン](../../../docs/standard/security/secure-coding-guidelines.md)します。</span><span class="sxs-lookup"><span data-stu-id="68ffe-122">Code that has been diligently tested for security vulnerabilities and is in compliance with the guidelines described in [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md).</span></span>  
  
- <span data-ttu-id="68ffe-123">部分的に信頼されたシナリオ用に特に記述された厳密な名前のコード ライブラリ。</span><span class="sxs-lookup"><span data-stu-id="68ffe-123">Strong-named code libraries that are specifically written for partially trusted scenarios.</span></span>  
  
- <span data-ttu-id="68ffe-124">インターネットからダウンロードしたコードによって呼び出される、厳密な名前で署名された (部分的に信頼された、または完全に信頼された) すべてのコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="68ffe-124">Any components (whether partially or fully trusted) signed with a strong name that will be called by code that is downloaded from the Internet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68ffe-125">.NET Framework クラス ライブラリのいくつかのクラスにはありません、 **AllowPartiallyTrustedCallersAttribute**属性し、部分的に信頼されたコードから呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="68ffe-125">Some classes in the .NET Framework class library do not have the **AllowPartiallyTrustedCallersAttribute** attribute and cannot be called by partially trusted code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68ffe-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="68ffe-126">See also</span></span>

- [<span data-ttu-id="68ffe-127">コード アクセス セキュリティ</span><span class="sxs-lookup"><span data-stu-id="68ffe-127">Code Access Security</span></span>](../../../docs/framework/misc/code-access-security.md)
