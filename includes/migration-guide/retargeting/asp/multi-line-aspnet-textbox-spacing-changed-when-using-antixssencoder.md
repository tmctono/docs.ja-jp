---
ms.openlocfilehash: 53860bb867522503c5cb9bd35e25fadd00a116a2
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609163"
---
### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a><span data-ttu-id="2dc6f-101">AntiXSSEncoder を使用するときの複数行の ASP.NET TextBox の間隔が変更</span><span class="sxs-lookup"><span data-stu-id="2dc6f-101">Multi-line ASP.NET TextBox spacing changed when using AntiXSSEncoder</span></span>

#### <a name="details"></a><span data-ttu-id="2dc6f-102">説明</span><span class="sxs-lookup"><span data-stu-id="2dc6f-102">Details</span></span>

<span data-ttu-id="2dc6f-103">.NET Framework 4.0 では、<xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=fullName> を使用する場合、ポストバックの複数行テキスト ボックスの行間に余分な行が挿入されました。</span><span class="sxs-lookup"><span data-stu-id="2dc6f-103">In .NET Framework 4.0, extra lines were inserted between lines of a multi-line text box on postback, if using the <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=fullName>.</span></span> <span data-ttu-id="2dc6f-104">.NET Framework 4.5 では、これらの余分な改行は含まれませんが、web アプリが .NET Framework 4.5 を対象としている場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="2dc6f-104">In .NET Framework 4.5, those extra line breaks are not included, but only if the web app is targeting .NET Framework 4.5</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2dc6f-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="2dc6f-105">Suggestion</span></span>

<span data-ttu-id="2dc6f-106">4\.0 の Web アプリの対象を .NET Framework 4.5 に変更すると、複数行テキスト ボックスが改善され、余分な改行が挿入されなくなります。</span><span class="sxs-lookup"><span data-stu-id="2dc6f-106">Be aware that 4.0 web apps retargeted to .NET Framework 4.5 may have multi-line text boxes improved to no longer insert extra line breaks.</span></span> <span data-ttu-id="2dc6f-107">これが望ましくない場合は、.NET Framework 4.0 を対象とすることによって、アプリを .NET Framework 4.5 で実行するときにも以前の動作が可能です。</span><span class="sxs-lookup"><span data-stu-id="2dc6f-107">If this is not desirable, the app  can have the old behavior when running on .NET Framework 4.5 by targeting the .NET Framework 4.0.</span></span>

| <span data-ttu-id="2dc6f-108">名前</span><span class="sxs-lookup"><span data-stu-id="2dc6f-108">Name</span></span>    | <span data-ttu-id="2dc6f-109">[値]</span><span class="sxs-lookup"><span data-stu-id="2dc6f-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2dc6f-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="2dc6f-110">Scope</span></span>   | <span data-ttu-id="2dc6f-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="2dc6f-111">Minor</span></span>       |
| <span data-ttu-id="2dc6f-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="2dc6f-112">Version</span></span> | <span data-ttu-id="2dc6f-113">4.5</span><span class="sxs-lookup"><span data-stu-id="2dc6f-113">4.5</span></span>         |
| <span data-ttu-id="2dc6f-114">種類</span><span class="sxs-lookup"><span data-stu-id="2dc6f-114">Type</span></span>    | <span data-ttu-id="2dc6f-115">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="2dc6f-115">Retargeting</span></span> |
