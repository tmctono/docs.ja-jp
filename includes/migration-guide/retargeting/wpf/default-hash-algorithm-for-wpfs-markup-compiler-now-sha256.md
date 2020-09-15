---
ms.openlocfilehash: 4303b177ffe01328965c909a5a3809414fcead91
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614933"
---
### <a name="the-default-hash-algorithm-for-wpfs-markup-compiler-is-now-sha256"></a><span data-ttu-id="5c19a-101">WPF のマークアップ コンパイラの既定のハッシュ アルゴリズムが SHA256 になった</span><span class="sxs-lookup"><span data-stu-id="5c19a-101">The default hash algorithm for WPF's Markup Compiler is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="5c19a-102">説明</span><span class="sxs-lookup"><span data-stu-id="5c19a-102">Details</span></span>

<span data-ttu-id="5c19a-103">WPF マークアップ コンパイラでは、XAML マークアップ ファイルのコンパイル サービスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="5c19a-103">The WPF MarkupCompiler provides compilation services for XAML markup files.</span></span>  <span data-ttu-id="5c19a-104">.NET Framework 4.7.1 以前のバージョンでは、チェックサムで使用される既定のハッシュ アルゴリズムは SHA1 でした。</span><span class="sxs-lookup"><span data-stu-id="5c19a-104">In the .NET Framework 4.7.1 and earlier versions, the default hash algorithm used for checksums was SHA1.</span></span> <span data-ttu-id="5c19a-105">最近明らかになった SHA1 のセキュリティに関する懸念事項により、.NET Framework 4.7.2 以降では、この既定値は SHA256 に変更されています。</span><span class="sxs-lookup"><span data-stu-id="5c19a-105">Due to recent security concerns with SHA1, this default has been changed to SHA256 starting with the .NET Framework 4.7.2.</span></span>  <span data-ttu-id="5c19a-106">この変更は、コンパイル中のマークアップ ファイルのすべてのチェックサム生成に影響します。</span><span class="sxs-lookup"><span data-stu-id="5c19a-106">This change affects all checksum generation for markup files during compilation.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5c19a-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="5c19a-107">Suggestion</span></span>

<span data-ttu-id="5c19a-108">.NET Framework 4.7.2 以降を対象とし、SHA1 ハッシュの動作に戻す開発者は、以下の AppContext フラグを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c19a-108">A developer who targets .NET Framework 4.7.2 or greater and wants to revert to SHA1 hashing behavior must set the following AppContext flag.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

<span data-ttu-id="5c19a-109">.NET 4.7.2 より前のバージョンのフレームワークを対象とするときに SHA256 ハッシュを利用する開発者は、以下の AppContext フラグを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c19a-109">A developer who wants to utilize SHA256 hashing while targeting a framework version below .NET 4.7.2 must set the below AppContext flag.</span></span>  <span data-ttu-id="5c19a-110">インストールされている .NET Framework のバージョンは 4.7.2 以降である必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5c19a-110">Note that the installed version of the .NET Framework must be 4.7.2 or greater.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=false&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="5c19a-111">名前</span><span class="sxs-lookup"><span data-stu-id="5c19a-111">Name</span></span>    | <span data-ttu-id="5c19a-112">[値]</span><span class="sxs-lookup"><span data-stu-id="5c19a-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5c19a-113">スコープ</span><span class="sxs-lookup"><span data-stu-id="5c19a-113">Scope</span></span>   | <span data-ttu-id="5c19a-114">透明</span><span class="sxs-lookup"><span data-stu-id="5c19a-114">Transparent</span></span> |
| <span data-ttu-id="5c19a-115">バージョン</span><span class="sxs-lookup"><span data-stu-id="5c19a-115">Version</span></span> | <span data-ttu-id="5c19a-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="5c19a-116">4.7.2</span></span>       |
| <span data-ttu-id="5c19a-117">種類</span><span class="sxs-lookup"><span data-stu-id="5c19a-117">Type</span></span>    | <span data-ttu-id="5c19a-118">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="5c19a-118">Retargeting</span></span> |
