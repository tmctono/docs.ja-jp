---
ms.openlocfilehash: c9d6111edcfeec6852f23cc0768833de32e61022
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235550"
---
### <a name="error-codes-for-maxrequestlength-or-maxreceivedmessagesize-are-different"></a><span data-ttu-id="202ea-101">maxRequestLength または maxReceivedMessageSize のエラー コードが異なる</span><span class="sxs-lookup"><span data-stu-id="202ea-101">Error codes for maxRequestLength or maxReceivedMessageSize are different</span></span>

|   |   |
|---|---|
|<span data-ttu-id="202ea-102">説明</span><span class="sxs-lookup"><span data-stu-id="202ea-102">Details</span></span>|<span data-ttu-id="202ea-103">Internet Information Services (IIS) または ASP.NET 開発サーバーでホストされており、maxRequestLength (ASP.NET の場合) または maxReceivedMessageSize (WCF の場合) を超える WCF Web サービスのメッセージに異なるエラー コードがあります。HTTP 状態コードは 400 (正しくない要求) から 413 (要求したエンティティが大きすぎます) に変更され、maxRequestLength または maxReceivedMessageSize 設定を超えるメッセージでは <xref:System.ServiceModel.ProtocolException?displayProperty=name> 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="202ea-103">Messages in WCF web services hosted in Internet Information Services (IIS) or ASP.NET Development Server that exceed maxRequestLength (in ASP.NET) or maxReceivedMessageSize (in WCF) have different error codeThe HTTP status code has changed from 400 (Bad Request) to 413 (Request Entity Too Large), and messages that exceed either the maxRequestLength or the maxReceivedMessageSize setting throw a <xref:System.ServiceModel.ProtocolException?displayProperty=name> exception.</span></span> <span data-ttu-id="202ea-104">これには、転送モードが Streamed である場合も含まれます。</span><span class="sxs-lookup"><span data-stu-id="202ea-104">This includes cases in which the transfer mode is Streamed.</span></span>|
|<span data-ttu-id="202ea-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="202ea-105">Suggestion</span></span>|<span data-ttu-id="202ea-106">この変更により、メッセージ長が ASP.NET または WCF で許可されている制限を超えたときのデバッグが簡単になります。HTTP 400 状態コードに基づいて処理を実行するコードはすべて変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="202ea-106">This change facilitates debugging in cases where the message length exceeds the limits allowed by ASP.NET or WCF.You must modify any code that performs processing based on an HTTP 400 status code.</span></span>|
|<span data-ttu-id="202ea-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="202ea-107">Scope</span></span>|<span data-ttu-id="202ea-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="202ea-108">Edge</span></span>|
|<span data-ttu-id="202ea-109">Version</span><span class="sxs-lookup"><span data-stu-id="202ea-109">Version</span></span>|<span data-ttu-id="202ea-110">4.5</span><span class="sxs-lookup"><span data-stu-id="202ea-110">4.5</span></span>|
|<span data-ttu-id="202ea-111">型</span><span class="sxs-lookup"><span data-stu-id="202ea-111">Type</span></span>|<span data-ttu-id="202ea-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="202ea-112">Runtime</span></span>|
