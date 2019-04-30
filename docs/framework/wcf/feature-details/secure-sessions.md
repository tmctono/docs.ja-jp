---
title: セキュリティで保護されたセッション
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
ms.openlocfilehash: 8f5cf9a965951bcc1049c2e96ae6cfa80b0113ba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61990978"
---
# <a name="secure-sessions"></a><span data-ttu-id="07fa5-102">セキュリティで保護されたセッション</span><span class="sxs-lookup"><span data-stu-id="07fa5-102">Secure Sessions</span></span>
<span data-ttu-id="07fa5-103">Windows Communication Foundation (WCF) の機能とは、送信された順序でメッセージを受信することを保証する信頼できるセッションです。</span><span class="sxs-lookup"><span data-stu-id="07fa5-103">A feature of Windows Communication Foundation (WCF) is reliable sessions that guarantee messages are received in the order they were sent.</span></span> <span data-ttu-id="07fa5-104">このセクションの各トピックでは、信頼できるセッションを作成する際に考慮する必要のあるセキュリティへの影響について説明します。</span><span class="sxs-lookup"><span data-stu-id="07fa5-104">The topics in this section discuss the security implications to consider when creating a reliable session.</span></span> <span data-ttu-id="07fa5-105">信頼できるセッションの詳細については、次を参照してください。[を使用してセッション](../../../../docs/framework/wcf/using-sessions.md)します。</span><span class="sxs-lookup"><span data-stu-id="07fa5-105">For more information about reliable sessions, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07fa5-106">Windows XP で偽装が必要な場合は、ステートフルなセキュリティ コンテキスト トークン (SCT: Security Context Token) を使用しない、セキュリティで保護されたセッションを使用します。</span><span class="sxs-lookup"><span data-stu-id="07fa5-106">When impersonation is required on Windows XP, use a secure session without a stateful security context token (SCT).</span></span> <span data-ttu-id="07fa5-107">ステートフルな SCT が偽装と共に使用されると、<xref:System.InvalidOperationException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="07fa5-107">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="07fa5-108">詳細については、次を参照してください。[サポートされていないシナリオ](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)します。</span><span class="sxs-lookup"><span data-stu-id="07fa5-108">For more information, see [Unsupported Scenarios](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="07fa5-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="07fa5-109">In This Section</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="07fa5-110">セキュリティ保護されたメッセージ交換とセッション</span><span class="sxs-lookup"><span data-stu-id="07fa5-110">Secure Conversations and Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)|<span data-ttu-id="07fa5-111">セキュリティで保護されたメッセージ交換とセキュリティで保護されたセッションは、同じ意味で使用されます。</span><span class="sxs-lookup"><span data-stu-id="07fa5-111">Secure conversations and secure sessions are synonymous.</span></span> <span data-ttu-id="07fa5-112">ここでは、セキュリティで保護されたメッセージ交換のしくみ、およびこのパターンを使用する状況と理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="07fa5-112">This topic explains the way a secure conversation works, and when and why to use the pattern.</span></span>|  
|[<span data-ttu-id="07fa5-113">方法: セキュリティで保護されたセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="07fa5-113">How to: Create a Secure Session</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md)|<span data-ttu-id="07fa5-114">セキュリティで保護されたセッションの基本的な作成手順を説明するチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="07fa5-114">Walks through of the basics of creating a secure session.</span></span>|  
|[<span data-ttu-id="07fa5-115">方法: セキュリティ コンテキストを作成、セキュリティで保護されたセッションのトークン</span><span class="sxs-lookup"><span data-stu-id="07fa5-115">How to: Create a Security Context Token for a Secure Session</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)|<span data-ttu-id="07fa5-116">クライアントの状態とセッションを保持する Web ファームを作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="07fa5-116">Walks through the steps of creating a Web farm that will maintain state and sessions with clients.</span></span>|  
|[<span data-ttu-id="07fa5-117">セキュリティで保護されたセッションに関するセキュリティの検討</span><span class="sxs-lookup"><span data-stu-id="07fa5-117">Security Considerations for Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)|<span data-ttu-id="07fa5-118">セキュリティで保護されたセッションに関する特別な考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="07fa5-118">Describes special considerations for secure sessions.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="07fa5-119">参照</span><span class="sxs-lookup"><span data-stu-id="07fa5-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="07fa5-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="07fa5-120">Related Sections</span></span>  
 [<span data-ttu-id="07fa5-121">セッション、インスタンス化、およびコンカレンシー</span><span class="sxs-lookup"><span data-stu-id="07fa5-121">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
  
 [<span data-ttu-id="07fa5-122">サービスの設計と実装</span><span class="sxs-lookup"><span data-stu-id="07fa5-122">Designing and Implementing Services</span></span>](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="07fa5-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="07fa5-123">See also</span></span>

- [<span data-ttu-id="07fa5-124">方法: メッセージ リプレイ検出を有効にします。</span><span class="sxs-lookup"><span data-stu-id="07fa5-124">How to: Enable Message Replay Detection</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)
- [<span data-ttu-id="07fa5-125">リプレイ攻撃</span><span class="sxs-lookup"><span data-stu-id="07fa5-125">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
- [<span data-ttu-id="07fa5-126">方法: セッションを必要とするサービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="07fa5-126">How to: Create a Service That Requires Sessions</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
