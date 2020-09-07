---
ms.openlocfilehash: a9011514c7c4393ec44de2c7fae88768cdccf435
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496860"
---
### <a name="the-net-framework-46-does-not-use-a-45xx-version-when-registering-itself-in-the-registry"></a><span data-ttu-id="831a6-101">.NET Framework 4.6 は、自分自身をレジストリに登録するときに 4.5.x.x バージョンを使用しない</span><span class="sxs-lookup"><span data-stu-id="831a6-101">The .NET Framework 4.6 does not use a 4.5.x.x version when registering itself in the registry</span></span>

#### <a name="details"></a><span data-ttu-id="831a6-102">説明</span><span class="sxs-lookup"><span data-stu-id="831a6-102">Details</span></span>

<span data-ttu-id="831a6-103">予想されるように、.NET Framework 4.6 に対してレジストリ (<code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) に設定されるバージョン キーは、"4.5" ではなく "4.6" で始まります。</span><span class="sxs-lookup"><span data-stu-id="831a6-103">As one might expect, the version key set in the registry (at <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) for the .NET Framework 4.6 begins with '4.6', not '4.5'.</span></span> <span data-ttu-id="831a6-104">これらのレジストリ キーに依存してコンピューターにインストールされている .NET Framework のバージョンを特定するアプリは、4.6 が可能な新しいバージョンであり、前の 4.5.x リリースと互換性があることを認識するように、更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="831a6-104">Apps that depend on these registry keys to know which .NET Framework versions are installed on a machine should be updated to understand that 4.6 is a new possible version, and one that is compatible with previous 4.5.x releases.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="831a6-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="831a6-105">Suggestion</span></span>

<span data-ttu-id="831a6-106">4\.5 のレジストリ キーを検索することによって .NET Framework 4.5 のインストールを調べるアプリを、4.6 も受け付けるように更新します。</span><span class="sxs-lookup"><span data-stu-id="831a6-106">Update apps probing for a .NET Framework 4.5 install by looking for 4.5 registry keys to also accept 4.6.</span></span>

| <span data-ttu-id="831a6-107">名前</span><span class="sxs-lookup"><span data-stu-id="831a6-107">Name</span></span>    | <span data-ttu-id="831a6-108">値</span><span class="sxs-lookup"><span data-stu-id="831a6-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="831a6-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="831a6-109">Scope</span></span>   |<span data-ttu-id="831a6-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="831a6-110">Edge</span></span>|
|<span data-ttu-id="831a6-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="831a6-111">Version</span></span>|<span data-ttu-id="831a6-112">4.6</span><span class="sxs-lookup"><span data-stu-id="831a6-112">4.6</span></span>|
|<span data-ttu-id="831a6-113">種類</span><span class="sxs-lookup"><span data-stu-id="831a6-113">Type</span></span>|<span data-ttu-id="831a6-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="831a6-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="831a6-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="831a6-115">Affected APIs</span></span>

<span data-ttu-id="831a6-116">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="831a6-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
