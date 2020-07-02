---
ms.openlocfilehash: 150b98255b3075a8fe8cad60ce234206b788a5f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617186"
---
### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a><span data-ttu-id="df9b0-101">AntiXSSEncoder を使用するときの複数行の ASP.Net TextBox の間隔が変更</span><span class="sxs-lookup"><span data-stu-id="df9b0-101">Multi-line ASP.Net TextBox spacing changed when using AntiXSSEncoder</span></span>

#### <a name="details"></a><span data-ttu-id="df9b0-102">説明</span><span class="sxs-lookup"><span data-stu-id="df9b0-102">Details</span></span>

<span data-ttu-id="df9b0-103">.NET Framework 4.0 では、<xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=fullName> を使用する場合、ポストバックの複数行テキスト ボックスの行間に余分な行が挿入されました。</span><span class="sxs-lookup"><span data-stu-id="df9b0-103">In .NET Framework 4.0, extra lines were inserted between lines of a multi-line text box on postback, if using the <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=fullName>.</span></span> <span data-ttu-id="df9b0-104">.NET Framework 4.5 では、これらの余分な改行は含まれませんが、web アプリが .NET Framework 4.5 を対象としている場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-104">In .NET Framework 4.5, those extra line breaks are not included, but only if the web app is targeting .NET Framework 4.5</span></span>

#### <a name="suggestion"></a><span data-ttu-id="df9b0-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="df9b0-105">Suggestion</span></span>

<span data-ttu-id="df9b0-106">4\.0 の Web アプリの対象を .NET Framework 4.5 に変更すると、複数行テキスト ボックスが改善され、余分な改行が挿入されなくなります。</span><span class="sxs-lookup"><span data-stu-id="df9b0-106">Be aware that 4.0 web apps retargeted to .NET Framework 4.5 may have multi-line text boxes improved to no longer insert extra line breaks.</span></span> <span data-ttu-id="df9b0-107">これが望ましくない場合は、.NET Framework 4.0 を対象とすることによって、アプリを .NET Framework 4.5 で実行するときにも以前の動作が可能です。</span><span class="sxs-lookup"><span data-stu-id="df9b0-107">If this is not desirable, the app  can have the old behavior when running on .NET Framework 4.5 by targeting the .NET Framework 4.0.</span></span>

| <span data-ttu-id="df9b0-108">名前</span><span class="sxs-lookup"><span data-stu-id="df9b0-108">Name</span></span>    | <span data-ttu-id="df9b0-109">[値]</span><span class="sxs-lookup"><span data-stu-id="df9b0-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="df9b0-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="df9b0-110">Scope</span></span>   | <span data-ttu-id="df9b0-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="df9b0-111">Minor</span></span>       |
| <span data-ttu-id="df9b0-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="df9b0-112">Version</span></span> | <span data-ttu-id="df9b0-113">4.5</span><span class="sxs-lookup"><span data-stu-id="df9b0-113">4.5</span></span>         |
| <span data-ttu-id="df9b0-114">種類</span><span class="sxs-lookup"><span data-stu-id="df9b0-114">Type</span></span>    | <span data-ttu-id="df9b0-115">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="df9b0-115">Retargeting</span></span> |
