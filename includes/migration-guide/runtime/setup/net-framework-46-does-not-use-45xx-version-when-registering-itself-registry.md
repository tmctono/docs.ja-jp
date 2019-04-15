---
ms.openlocfilehash: ee5070a1a4c58d6c1282ba47c921436ca22722ff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234257"
---
### <a name="the-net-framework-46-does-not-use-a-45xx-version-when-registering-itself-in-the-registry"></a><span data-ttu-id="b4180-101">.NET Framework 4.6 は、自分自身をレジストリに登録するときに 4.5.x.x バージョンを使用しない</span><span class="sxs-lookup"><span data-stu-id="b4180-101">The .NET Framework 4.6 does not use a 4.5.x.x version when registering itself in the registry</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b4180-102">説明</span><span class="sxs-lookup"><span data-stu-id="b4180-102">Details</span></span>|<span data-ttu-id="b4180-103">予想されるように、.NET Framework 4.6 に対してレジストリ (<code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) に設定されるバージョン キーは、"4.5" ではなく "4.6" で始まります。</span><span class="sxs-lookup"><span data-stu-id="b4180-103">As one might expect, the version key set in the registry (at <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) for the .NET Framework 4.6 begins with '4.6', not '4.5'.</span></span> <span data-ttu-id="b4180-104">これらのレジストリ キーに依存してコンピューターにインストールされている .NET Framework のバージョンを特定するアプリは、4.6 が可能な新しいバージョンであり、前の 4.5.x リリースと互換性があることを認識するように、更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4180-104">Apps that depend on these registry keys to know which .NET Framework versions are installed on a machine should be updated to understand that 4.6 is a new possible version, and one that is compatible with previous 4.5.x releases.</span></span>|
|<span data-ttu-id="b4180-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="b4180-105">Suggestion</span></span>|<span data-ttu-id="b4180-106">4.5 のレジストリ キーを検索することによって .NET Framework 4.5 のインストールを調べるアプリを、4.6 も受け付けるように更新します。</span><span class="sxs-lookup"><span data-stu-id="b4180-106">Update apps probing for a .NET Framework 4.5 install by looking for 4.5 registry keys to also accept 4.6.</span></span>|
|<span data-ttu-id="b4180-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="b4180-107">Scope</span></span>|<span data-ttu-id="b4180-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="b4180-108">Edge</span></span>|
|<span data-ttu-id="b4180-109">Version</span><span class="sxs-lookup"><span data-stu-id="b4180-109">Version</span></span>|<span data-ttu-id="b4180-110">4.6</span><span class="sxs-lookup"><span data-stu-id="b4180-110">4.6</span></span>|
|<span data-ttu-id="b4180-111">型</span><span class="sxs-lookup"><span data-stu-id="b4180-111">Type</span></span>|<span data-ttu-id="b4180-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="b4180-112">Runtime</span></span>|
