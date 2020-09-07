---
ms.openlocfilehash: 26facb645de175d7ef0432394fc2b84f59e8437d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496410"
---
### <a name="error-codes-for-maxrequestlength-or-maxreceivedmessagesize-are-different"></a><span data-ttu-id="61448-101">maxRequestLength または maxReceivedMessageSize のエラー コードが異なる</span><span class="sxs-lookup"><span data-stu-id="61448-101">Error codes for maxRequestLength or maxReceivedMessageSize are different</span></span>

#### <a name="details"></a><span data-ttu-id="61448-102">説明</span><span class="sxs-lookup"><span data-stu-id="61448-102">Details</span></span>

<span data-ttu-id="61448-103">Internet Information Services (IIS) または ASP.NET 開発サーバーでホストされており、maxRequestLength (ASP.NET の場合) または maxReceivedMessageSize (WCF の場合) を超える WCF Web サービスのメッセージに異なるエラー コードがあります。HTTP 状態コードは 400 (正しくない要求) から 413 (要求したエンティティが大きすぎます) に変更され、maxRequestLength または maxReceivedMessageSize 設定を超えるメッセージでは <xref:System.ServiceModel.ProtocolException?displayProperty=fullName> 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="61448-103">Messages in WCF web services hosted in Internet Information Services (IIS) or ASP.NET Development Server that exceed maxRequestLength (in ASP.NET) or maxReceivedMessageSize (in WCF) have different error codeThe HTTP status code has changed from 400 (Bad Request) to 413 (Request Entity Too Large), and messages that exceed either the maxRequestLength or the maxReceivedMessageSize setting throw a <xref:System.ServiceModel.ProtocolException?displayProperty=fullName> exception.</span></span> <span data-ttu-id="61448-104">これには、転送モードが Streamed である場合も含まれます。</span><span class="sxs-lookup"><span data-stu-id="61448-104">This includes cases in which the transfer mode is Streamed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="61448-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="61448-105">Suggestion</span></span>

<span data-ttu-id="61448-106">この変更により、メッセージ長が ASP.NET または WCF で許可されている制限を超えたときのデバッグが簡単になります。HTTP 400 状態コードに基づいて処理を実行するコードはすべて変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61448-106">This change facilitates debugging in cases where the message length exceeds the limits allowed by ASP.NET or WCF.You must modify any code that performs processing based on an HTTP 400 status code.</span></span>

| <span data-ttu-id="61448-107">名前</span><span class="sxs-lookup"><span data-stu-id="61448-107">Name</span></span>    | <span data-ttu-id="61448-108">[値]</span><span class="sxs-lookup"><span data-stu-id="61448-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="61448-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="61448-109">Scope</span></span>   |<span data-ttu-id="61448-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="61448-110">Edge</span></span>|
|<span data-ttu-id="61448-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="61448-111">Version</span></span>|<span data-ttu-id="61448-112">4.5</span><span class="sxs-lookup"><span data-stu-id="61448-112">4.5</span></span>|
|<span data-ttu-id="61448-113">種類</span><span class="sxs-lookup"><span data-stu-id="61448-113">Type</span></span>|<span data-ttu-id="61448-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="61448-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="61448-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="61448-115">Affected APIs</span></span>

<span data-ttu-id="61448-116">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="61448-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
