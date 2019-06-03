---
ms.openlocfilehash: 84f570cbbd97be79426e117d4c97ec182a397fd4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379560"
---
### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a><span data-ttu-id="6a84f-101">iPad はブラウザー機能になったため、カスタム機能ファイルでは使用できない</span><span class="sxs-lookup"><span data-stu-id="6a84f-101">IPad should not be used in custom capabilities file because it is now a browser capability</span></span>

|   |   |
|---|---|
|<span data-ttu-id="6a84f-102">説明</span><span class="sxs-lookup"><span data-stu-id="6a84f-102">Details</span></span>|<span data-ttu-id="6a84f-103">.NET Framework 4.5 以降では、iPad は既定の ASP.NET ブラウザー機能ファイルの識別子であるため、カスタム機能ファイルでは使用できません</span><span class="sxs-lookup"><span data-stu-id="6a84f-103">Beginning in .NET Framework 4.5, iPad is an identifier in the default ASP.NET browser capabilities file, so it should not be used in a custom capabilities file</span></span>|
|<span data-ttu-id="6a84f-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="6a84f-104">Suggestion</span></span>|<span data-ttu-id="6a84f-105">iPad 固有の機能が必要な場合は、ユーザー エージェントのマッチングで新しい &quot;IPad&quot; ID を生成するのではなく、定義済みのゲートウェイ refID &quot;IPad&quot; で機能を設定して、iPad の動作を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a84f-105">If iPad-specific capabilities are required, it is necessary to modify iPad behavior by setting capabilities on the pre-defined gateway refID &quot;IPad&quot; instead of by generating a new &quot;IPad&quot; ID by user agent matching.</span></span>|
|<span data-ttu-id="6a84f-106">スコープ</span><span class="sxs-lookup"><span data-stu-id="6a84f-106">Scope</span></span>|<span data-ttu-id="6a84f-107">エッジ</span><span class="sxs-lookup"><span data-stu-id="6a84f-107">Edge</span></span>|
|<span data-ttu-id="6a84f-108">Version</span><span class="sxs-lookup"><span data-stu-id="6a84f-108">Version</span></span>|<span data-ttu-id="6a84f-109">4.5</span><span class="sxs-lookup"><span data-stu-id="6a84f-109">4.5</span></span>|
|<span data-ttu-id="6a84f-110">型</span><span class="sxs-lookup"><span data-stu-id="6a84f-110">Type</span></span>|<span data-ttu-id="6a84f-111">ランタイム</span><span class="sxs-lookup"><span data-stu-id="6a84f-111">Runtime</span></span>|
