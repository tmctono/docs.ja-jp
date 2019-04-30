---
title: 信頼できるセッション
ms.date: 03/30/2017
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
ms.openlocfilehash: 9a2cd06c4c5a73d9fb5c4c7f09632e10c3eb0d87
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991160"
---
# <a name="reliable-sessions"></a><span data-ttu-id="02ca3-102">信頼できるセッション</span><span class="sxs-lookup"><span data-stu-id="02ca3-102">Reliable Sessions</span></span>

<span data-ttu-id="02ca3-103">このセクションでは、どのような Windows Communication Foundation (WCF) 信頼できるセッションが、用途も、方法およびと 1 つを使用するバインド構成をサポートしのポインターのベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="02ca3-103">This section describes what a Windows Communication Foundation (WCF) reliable session is, what it's used for, how and when to use one, what binding configurations support it, and pointers on best practices.</span></span> <span data-ttu-id="02ca3-104">このセクションの重要なポイントと関連するトピックの詳細について、次の表にまとめます。</span><span class="sxs-lookup"><span data-stu-id="02ca3-104">The following table summarizes details about the essential points and related topics in this section.</span></span>

<span data-ttu-id="02ca3-105">信頼できるセッションが WCF には、エンドポイント間で送信されるメッセージが SOAP またはトランスポート中継ぎ局を介して転送して、1 回のみと、必要に応じて、送信された順序で配信されることを確認する機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="02ca3-105">The reliable session WCF provides features ensuring that messages sent between endpoints are transferred across SOAP or transport intermediaries and are delivered only once and, optionally, in the same order in which they were sent.</span></span>

<span data-ttu-id="02ca3-106">で WCF アプリケーションを信頼できるセッションを使用するには、既定またはオプションとして、信頼できるセッションをサポートして WCF でのシステム提供バインディングのいずれかを使用するか、セッションをサポートする独自のカスタム バインドを作成します。</span><span class="sxs-lookup"><span data-stu-id="02ca3-106">To use a reliable session with a WCF application, either use one of the system-provided bindings in WCF that support a reliable session by default or as an option, or create your own custom binding that supports the session.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="02ca3-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="02ca3-107">In This Section</span></span>

<span data-ttu-id="02ca3-108">[信頼できるセッションの概要](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)信頼できるセッションの説明に、信頼できるセッションをサポートする各種のバインディングを使用する場合とそのしくみ。</span><span class="sxs-lookup"><span data-stu-id="02ca3-108">[Reliable Sessions Overview](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) Describes reliable sessions, when to use them, the different bindings that support reliable sessions, and how they work.</span></span>

<span data-ttu-id="02ca3-109">[方法: Exchange のメッセージ内で、信頼できるセッション](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)構成に指定されたカスタム バインディングを使用して HTTP 経由で信頼できるセッションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="02ca3-109">[How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) Describes how to create a reliable session over HTTP using a custom binding specified in the configuration.</span></span>

<span data-ttu-id="02ca3-110">[方法: 信頼できるセッション内のメッセージをセキュリティで保護された](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md)信頼できるセッションをセキュリティで保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="02ca3-110">[How to: Secure Messages within Reliable Sessions](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) Describes how to secure a reliable session.</span></span>

<span data-ttu-id="02ca3-111">[方法: HTTPS でカスタム信頼できるセッション バインドを作成](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)HTTPS 経由で信頼できるセッションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="02ca3-111">[How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) Describes how to create a reliable session over HTTPS.</span></span>

<span data-ttu-id="02ca3-112">[信頼できるセッションのベスト プラクティス](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md)の信頼できるセッションの使用に関連するベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="02ca3-112">[Best Practices for Reliable Sessions](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) Describes some of the best practices associated with using a reliable session.</span></span>

## <a name="reference"></a><span data-ttu-id="02ca3-113">参照</span><span class="sxs-lookup"><span data-stu-id="02ca3-113">Reference</span></span>

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a><span data-ttu-id="02ca3-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="02ca3-114">See also</span></span>

- [<span data-ttu-id="02ca3-115">キューと信頼できるセッション</span><span class="sxs-lookup"><span data-stu-id="02ca3-115">Queues and Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
- [<span data-ttu-id="02ca3-116">セッション、インスタンス化、およびコンカレンシー</span><span class="sxs-lookup"><span data-stu-id="02ca3-116">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
