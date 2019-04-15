---
ms.openlocfilehash: 38c35f3f6f2262d06409690d2326d9b982e1ec86
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235773"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a><span data-ttu-id="106bc-101">.NET Framework 1.1 および 2.0 からのマネージド ブラウザーでのコントロールのホストがブロックされる</span><span class="sxs-lookup"><span data-stu-id="106bc-101">Managed browser hosting controls from the .NET Framework 1.1 and 2.0 are blocked</span></span>

|   |   |
|---|---|
|<span data-ttu-id="106bc-102">説明</span><span class="sxs-lookup"><span data-stu-id="106bc-102">Details</span></span>|<span data-ttu-id="106bc-103">これらのコントロールのホストは、Internet Explorer でブロックされます。</span><span class="sxs-lookup"><span data-stu-id="106bc-103">Hosting these controls is blocked in Internet Explorer.</span></span>|
|<span data-ttu-id="106bc-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="106bc-104">Suggestion</span></span>|<span data-ttu-id="106bc-105">Internet Explorer では、マネージド ブラウザーを使用してコントロールをホストするアプリケーションは起動できません。</span><span class="sxs-lookup"><span data-stu-id="106bc-105">Internet Explorer will fail to launch an application that uses managed browser hosting controls.</span></span> <span data-ttu-id="106bc-106">以前の動作を復元するには、レジストリ サブキー <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> の EnableIEHosting 値を、x86 システム用および x64 システム上の 32 ビット プロセス用に <code>1</code> に設定し、レジストリ サブキー <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> の <code>EnableIEHosting</code> 値を x64 システム上の 64 ビット プロセス用に <code>1</code> に設定します。</span><span class="sxs-lookup"><span data-stu-id="106bc-106">The previous behavior can be restored by setting the EnableIEHosting value of the registry subkey <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> to <code>1</code> for x86 systems and for 32-bit processes on x64 systems, and by setting the <code>EnableIEHosting</code> value of the registry subkey <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> to <code>1</code> for 64-bit processes on x64 systems.</span></span>|
|<span data-ttu-id="106bc-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="106bc-107">Scope</span></span>|<span data-ttu-id="106bc-108">マイナー</span><span class="sxs-lookup"><span data-stu-id="106bc-108">Minor</span></span>|
|<span data-ttu-id="106bc-109">Version</span><span class="sxs-lookup"><span data-stu-id="106bc-109">Version</span></span>|<span data-ttu-id="106bc-110">4.5</span><span class="sxs-lookup"><span data-stu-id="106bc-110">4.5</span></span>|
|<span data-ttu-id="106bc-111">型</span><span class="sxs-lookup"><span data-stu-id="106bc-111">Type</span></span>|<span data-ttu-id="106bc-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="106bc-112">Runtime</span></span>|
