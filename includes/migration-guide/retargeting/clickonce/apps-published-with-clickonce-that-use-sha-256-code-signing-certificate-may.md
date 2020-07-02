---
ms.openlocfilehash: 416590c7bd959eea011b7e7c5db48f22d349d0f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615661"
---
### <a name="apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a><span data-ttu-id="fb1c3-101">SHA-256 コード署名証明書を使用する ClickOnce で発行されたアプリケーションは、Windows 2003 では失敗することがある</span><span class="sxs-lookup"><span data-stu-id="fb1c3-101">Apps published with ClickOnce that use a SHA-256 code-signing certificate may fail on Windows 2003</span></span>

#### <a name="details"></a><span data-ttu-id="fb1c3-102">説明</span><span class="sxs-lookup"><span data-stu-id="fb1c3-102">Details</span></span>

<span data-ttu-id="fb1c3-103">この実行可能ファイルは SHA256 で署名されます。</span><span class="sxs-lookup"><span data-stu-id="fb1c3-103">The executable is signed with SHA256.</span></span> <span data-ttu-id="fb1c3-104">以前は、コード署名証明書が SHA-1 か SHA-256 に関係なく、SHA 1 で署名されました。</span><span class="sxs-lookup"><span data-stu-id="fb1c3-104">Previously, it was signed with SHA1 regardless of whether the code-signing certificate was SHA-1 or SHA-256.</span></span> <span data-ttu-id="fb1c3-105">この方法は、次の対象に適用されます。</span><span class="sxs-lookup"><span data-stu-id="fb1c3-105">This applies to:</span></span>

- <span data-ttu-id="fb1c3-106">Visual Studio 2012 以降でビルドされたすべてのアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="fb1c3-106">All applications built with Visual Studio 2012 or later.</span></span>
- <span data-ttu-id="fb1c3-107">.NET Framework 4.5 がインストールされているシステム上で、Visual Studio 2010 以前でビルドされたアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="fb1c3-107">Applications built with Visual Studio 2010 or earlier on systems with the .NET Framework 4.5 present.</span></span>
<span data-ttu-id="fb1c3-108">さらに、.NET Framework 4.5 以降が存在する場合、コンパイル対象となった .NET Framework のバージョンに関係なく、ClickOnce マニフェストはSHA-256 証明書の SHA 256 で署名されます。</span><span class="sxs-lookup"><span data-stu-id="fb1c3-108">In addition, if the .NET Framework 4.5 or later is present, the ClickOnce manifest is also signed with SHA-256 for SHA-256 certificates regardless of the .NET Framework version against which it was compiled.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fb1c3-109">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="fb1c3-109">Suggestion</span></span>

<span data-ttu-id="fb1c3-110">ClickOnce 実行可能ファイルの署名方法に関するこの変更は、Windows Server 2003 システムにのみ影響を及ぼします。これらのシステムには、KB 938397 をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb1c3-110">The change in signing the ClickOnce executable affects only Windows Server 2003 systems; they require that KB 938397 be installed.</span></span> <span data-ttu-id="fb1c3-111">アプリが .NET Framework 4.0 以前のバージョンをターゲットとしている場合でも、SHA-256 を使用したマニフェストの署名方法の変更により、.NET Framework 4.5 以降のバージョンに対するランタイム依存関係が導入されます。</span><span class="sxs-lookup"><span data-stu-id="fb1c3-111">The change in signing the manifest with SHA-256 even when an app targets the .NET Framework 4.0 or earlier versions introduces a runtime dependency on the .NET Framework 4.5 or a later version.</span></span>

| <span data-ttu-id="fb1c3-112">名前</span><span class="sxs-lookup"><span data-stu-id="fb1c3-112">Name</span></span>    | <span data-ttu-id="fb1c3-113">[値]</span><span class="sxs-lookup"><span data-stu-id="fb1c3-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fb1c3-114">スコープ</span><span class="sxs-lookup"><span data-stu-id="fb1c3-114">Scope</span></span>   | <span data-ttu-id="fb1c3-115">エッジ</span><span class="sxs-lookup"><span data-stu-id="fb1c3-115">Edge</span></span>        |
| <span data-ttu-id="fb1c3-116">バージョン</span><span class="sxs-lookup"><span data-stu-id="fb1c3-116">Version</span></span> | <span data-ttu-id="fb1c3-117">4.5</span><span class="sxs-lookup"><span data-stu-id="fb1c3-117">4.5</span></span>         |
| <span data-ttu-id="fb1c3-118">種類</span><span class="sxs-lookup"><span data-stu-id="fb1c3-118">Type</span></span>    | <span data-ttu-id="fb1c3-119">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="fb1c3-119">Retargeting</span></span> |
