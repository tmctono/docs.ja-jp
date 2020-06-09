---
title: セキュリティで保護されたセッション
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
ms.openlocfilehash: cb02adc7514e27175088e7664b12e45bc8ca5cd9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590086"
---
# <a name="secure-sessions"></a><span data-ttu-id="5ddf7-102">セキュリティで保護されたセッション</span><span class="sxs-lookup"><span data-stu-id="5ddf7-102">Secure Sessions</span></span>
<span data-ttu-id="5ddf7-103">Windows Communication Foundation (WCF) の機能は、メッセージが送信された順序で受信されることを保証する信頼できるセッションです。</span><span class="sxs-lookup"><span data-stu-id="5ddf7-103">A feature of Windows Communication Foundation (WCF) is reliable sessions that guarantee messages are received in the order they were sent.</span></span> <span data-ttu-id="5ddf7-104">このセクションの各トピックでは、信頼できるセッションを作成する際に考慮する必要のあるセキュリティへの影響について説明します。</span><span class="sxs-lookup"><span data-stu-id="5ddf7-104">The topics in this section discuss the security implications to consider when creating a reliable session.</span></span> <span data-ttu-id="5ddf7-105">信頼できるセッションの詳細については、「[セッションの使用](../using-sessions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ddf7-105">For more information about reliable sessions, see [Using Sessions](../using-sessions.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5ddf7-106">Windows XP で偽装が必要な場合は、ステートフルなセキュリティ コンテキスト トークン (SCT: Security Context Token) を使用しない、セキュリティで保護されたセッションを使用します。</span><span class="sxs-lookup"><span data-stu-id="5ddf7-106">When impersonation is required on Windows XP, use a secure session without a stateful security context token (SCT).</span></span> <span data-ttu-id="5ddf7-107">ステートフル SCT が偽装と共に使用されると、<xref:System.InvalidOperationException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="5ddf7-107">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="5ddf7-108">詳細については、「サポートされ[ないシナリオ](unsupported-scenarios.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ddf7-108">For more information, see [Unsupported Scenarios](unsupported-scenarios.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5ddf7-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5ddf7-109">In This Section</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="5ddf7-110">セキュリティ保護されたメッセージ交換とセッション</span><span class="sxs-lookup"><span data-stu-id="5ddf7-110">Secure Conversations and Secure Sessions</span></span>](secure-conversations-and-secure-sessions.md)|<span data-ttu-id="5ddf7-111">セキュリティで保護されたメッセージ交換とセキュリティで保護されたセッションは、同じ意味で使用されます。</span><span class="sxs-lookup"><span data-stu-id="5ddf7-111">Secure conversations and secure sessions are synonymous.</span></span> <span data-ttu-id="5ddf7-112">ここでは、セキュリティで保護されたメッセージ交換のしくみ、およびこのパターンを使用する状況と理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="5ddf7-112">This topic explains the way a secure conversation works, and when and why to use the pattern.</span></span>|  
|[<span data-ttu-id="5ddf7-113">方法: セキュリティで保護されたセッションを作成する</span><span class="sxs-lookup"><span data-stu-id="5ddf7-113">How to: Create a Secure Session</span></span>](how-to-create-a-secure-session.md)|<span data-ttu-id="5ddf7-114">セキュリティで保護されたセッションの基本的な作成手順を説明するチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="5ddf7-114">Walks through of the basics of creating a secure session.</span></span>|  
|[<span data-ttu-id="5ddf7-115">方法: セキュリティで保護されたセッションに対しセキュリティ コンテキスト トークンを作成する</span><span class="sxs-lookup"><span data-stu-id="5ddf7-115">How to: Create a Security Context Token for a Secure Session</span></span>](how-to-create-a-security-context-token-for-a-secure-session.md)|<span data-ttu-id="5ddf7-116">クライアントの状態とセッションを保持する Web ファームを作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="5ddf7-116">Walks through the steps of creating a Web farm that will maintain state and sessions with clients.</span></span>|  
|[<span data-ttu-id="5ddf7-117">セキュリティで保護されたセッションに関するセキュリティの検討</span><span class="sxs-lookup"><span data-stu-id="5ddf7-117">Security Considerations for Secure Sessions</span></span>](security-considerations-for-secure-sessions.md)|<span data-ttu-id="5ddf7-118">セキュリティで保護されたセッションに関する特別な考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="5ddf7-118">Describes special considerations for secure sessions.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="5ddf7-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ddf7-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="5ddf7-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ddf7-120">Related Sections</span></span>  
 [<span data-ttu-id="5ddf7-121">セッション、インスタンス化、およびコンカレンシー</span><span class="sxs-lookup"><span data-stu-id="5ddf7-121">Sessions, Instancing, and Concurrency</span></span>](sessions-instancing-and-concurrency.md)  
  
 [<span data-ttu-id="5ddf7-122">サービスの設計と実装</span><span class="sxs-lookup"><span data-stu-id="5ddf7-122">Designing and Implementing Services</span></span>](../designing-and-implementing-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="5ddf7-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ddf7-123">See also</span></span>

- [<span data-ttu-id="5ddf7-124">方法: メッセージ リプレイ検出を有効にする</span><span class="sxs-lookup"><span data-stu-id="5ddf7-124">How to: Enable Message Replay Detection</span></span>](how-to-enable-message-replay-detection.md)
- [<span data-ttu-id="5ddf7-125">リプレイ攻撃</span><span class="sxs-lookup"><span data-stu-id="5ddf7-125">Replay Attacks</span></span>](replay-attacks.md)
- [<span data-ttu-id="5ddf7-126">方法: セッションを必要とするサービスを作成する</span><span class="sxs-lookup"><span data-stu-id="5ddf7-126">How to: Create a Service That Requires Sessions</span></span>](how-to-create-a-service-that-requires-sessions.md)
