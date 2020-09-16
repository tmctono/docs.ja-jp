---
title: 'サービス : 1 秒あたりのセキュリティ検証と認証エラー'
ms.date: 03/30/2017
ms.assetid: 4af18009-e778-490b-9ba6-e76485285830
ms.openlocfilehash: f6dbf7f6da208bde3a9a380d50fd6caf68576f25
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90535912"
---
# <a name="service-security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="2fe97-102">サービス : 1 秒あたりのセキュリティ検証と認証エラー</span><span class="sxs-lookup"><span data-stu-id="2fe97-102">Service: Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="2fe97-103">カウンター名 : 1 秒あたりのセキュリティ検証と認証エラー</span><span class="sxs-lookup"><span data-stu-id="2fe97-103">Counter name: Security Validation and Authentication Failures Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2fe97-104">説明</span><span class="sxs-lookup"><span data-stu-id="2fe97-104">Description</span></span>  
 <span data-ttu-id="2fe97-105">このカウンターは、"承認されていないセキュリティ呼び出し" カウンターでカウントの対象とならないセキュリティ上の問題が原因でメッセージが拒否されるたびにインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="2fe97-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="2fe97-106">この問題には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="2fe97-106">Such problems include:</span></span>  
  
- <span data-ttu-id="2fe97-107">メッセージからクライアント トークンを読み取ることができない。</span><span class="sxs-lookup"><span data-stu-id="2fe97-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="2fe97-108">クライアント トークンが認証に失敗した (例 : 無効なパスワード)。</span><span class="sxs-lookup"><span data-stu-id="2fe97-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="2fe97-109">署名の検証に失敗した (例 : メッセージが改ざんされた)。</span><span class="sxs-lookup"><span data-stu-id="2fe97-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="2fe97-110">メッセージが以前のメッセージと重複する。この現象はリプレイ攻撃中に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="2fe97-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="2fe97-111">復号化に失敗した。</span><span class="sxs-lookup"><span data-stu-id="2fe97-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="2fe97-112">一部の必須要素 (タイムスタンプ、暗号化データ ブロックなど) がメッセージにない。</span><span class="sxs-lookup"><span data-stu-id="2fe97-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="2fe97-113">TLSNEGO/SPNEGO ハンドシェイク中にエラーが発生した。</span><span class="sxs-lookup"><span data-stu-id="2fe97-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="2fe97-114">このカウンターは、次の式を使用して計算された値を持つパフォーマンスカウンターの種類 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))です。</span><span class="sxs-lookup"><span data-stu-id="2fe97-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula,</span></span>  
  
 <span data-ttu-id="2fe97-115">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="2fe97-115">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
