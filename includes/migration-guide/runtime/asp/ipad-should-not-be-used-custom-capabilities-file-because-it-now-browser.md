---
ms.openlocfilehash: 84f570cbbd97be79426e117d4c97ec182a397fd4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235538"
---
### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a><span data-ttu-id="d9317-101">iPad はブラウザー機能になったため、カスタム機能ファイルでは使用できない</span><span class="sxs-lookup"><span data-stu-id="d9317-101">IPad should not be used in custom capabilities file because it is now a browser capability</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d9317-102">説明</span><span class="sxs-lookup"><span data-stu-id="d9317-102">Details</span></span>|<span data-ttu-id="d9317-103">.NET Framework 4.5 以降では、iPad は既定の ASP.NET ブラウザー機能ファイルの識別子であるため、カスタム機能ファイルでは使用できません</span><span class="sxs-lookup"><span data-stu-id="d9317-103">Beginning in .NET Framework 4.5, iPad is an identifier in the default ASP.NET browser capabilities file, so it should not be used in a custom capabilities file</span></span>|
|<span data-ttu-id="d9317-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="d9317-104">Suggestion</span></span>|<span data-ttu-id="d9317-105">iPad 固有の機能が必要な場合は、ユーザー エージェントのマッチングで新しい &quot;IPad&quot; ID を生成するのではなく、定義済みのゲートウェイ refID &quot;IPad&quot; で機能を設定して、iPad の動作を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9317-105">If iPad-specific capabilities are required, it is necessary to modify iPad behavior by setting capabilities on the pre-defined gateway refID &quot;IPad&quot; instead of by generating a new &quot;IPad&quot; ID by user agent matching.</span></span>|
|<span data-ttu-id="d9317-106">スコープ</span><span class="sxs-lookup"><span data-stu-id="d9317-106">Scope</span></span>|<span data-ttu-id="d9317-107">エッジ</span><span class="sxs-lookup"><span data-stu-id="d9317-107">Edge</span></span>|
|<span data-ttu-id="d9317-108">Version</span><span class="sxs-lookup"><span data-stu-id="d9317-108">Version</span></span>|<span data-ttu-id="d9317-109">4.5</span><span class="sxs-lookup"><span data-stu-id="d9317-109">4.5</span></span>|
|<span data-ttu-id="d9317-110">型</span><span class="sxs-lookup"><span data-stu-id="d9317-110">Type</span></span>|<span data-ttu-id="d9317-111">ランタイム</span><span class="sxs-lookup"><span data-stu-id="d9317-111">Runtime</span></span>|
