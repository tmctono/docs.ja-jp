---
ms.openlocfilehash: 83d3f24680531d1e447f047151a28c98ce0da04b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620400"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a><span data-ttu-id="6a63c-101">.NET Framework 1.1 および 2.0 からのマネージド ブラウザーでのコントロールのホストがブロックされる</span><span class="sxs-lookup"><span data-stu-id="6a63c-101">Managed browser hosting controls from the .NET Framework 1.1 and 2.0 are blocked</span></span>

#### <a name="details"></a><span data-ttu-id="6a63c-102">説明</span><span class="sxs-lookup"><span data-stu-id="6a63c-102">Details</span></span>

<span data-ttu-id="6a63c-103">これらのコントロールのホストは、Internet Explorer でブロックされます。</span><span class="sxs-lookup"><span data-stu-id="6a63c-103">Hosting these controls is blocked in Internet Explorer.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6a63c-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="6a63c-104">Suggestion</span></span>

<span data-ttu-id="6a63c-105">Internet Explorer では、マネージド ブラウザーを使用してコントロールをホストするアプリケーションは起動できません。</span><span class="sxs-lookup"><span data-stu-id="6a63c-105">Internet Explorer will fail to launch an application that uses managed browser hosting controls.</span></span> <span data-ttu-id="6a63c-106">以前の動作を復元するには、レジストリ サブキー <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> の EnableIEHosting 値を、x86 システム用および x64 システム上の 32 ビット プロセス用に <code>1</code> に設定し、レジストリ サブキー <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> の <code>EnableIEHosting</code> 値を x64 システム上の 64 ビット プロセス用に <code>1</code> に設定します。</span><span class="sxs-lookup"><span data-stu-id="6a63c-106">The previous behavior can be restored by setting the EnableIEHosting value of the registry subkey <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> to <code>1</code> for x86 systems and for 32-bit processes on x64 systems, and by setting the <code>EnableIEHosting</code> value of the registry subkey <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> to <code>1</code> for 64-bit processes on x64 systems.</span></span>

| <span data-ttu-id="6a63c-107">名前</span><span class="sxs-lookup"><span data-stu-id="6a63c-107">Name</span></span>    | <span data-ttu-id="6a63c-108">[値]</span><span class="sxs-lookup"><span data-stu-id="6a63c-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6a63c-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="6a63c-109">Scope</span></span>   |<span data-ttu-id="6a63c-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="6a63c-110">Minor</span></span>|
|<span data-ttu-id="6a63c-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="6a63c-111">Version</span></span>|<span data-ttu-id="6a63c-112">4.5</span><span class="sxs-lookup"><span data-stu-id="6a63c-112">4.5</span></span>|
|<span data-ttu-id="6a63c-113">種類</span><span class="sxs-lookup"><span data-stu-id="6a63c-113">Type</span></span>|<span data-ttu-id="6a63c-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="6a63c-114">Runtime</span></span>|
