---
ms.openlocfilehash: 2aa424ff5e3308b730c22cb865993d4100f193cc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616272"
---
### <a name="workflow-xoml-file-checksums-changed-from-md5-to-sha256"></a><span data-ttu-id="cf5c4-101">ワークフロー XOML ファイルのチェックサムが MD5 から SHA256 に変更</span><span class="sxs-lookup"><span data-stu-id="cf5c4-101">Workflow XOML file checksums changed from MD5 to SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="cf5c4-102">説明</span><span class="sxs-lookup"><span data-stu-id="cf5c4-102">Details</span></span>

<span data-ttu-id="cf5c4-103">Visual Studio を使用した XOML ベースのワークフローのデバッグをサポートするため、XOML ファイルが含まれているワークフロー プロジェクトをビルドするときに、XOML ファイルのコンテンツのチェックサムが <xref:System.Workflow.ComponentModel.Compiler.WorkflowMarkupSourceAttribute.MD5Digest?displayProperty=nameWithType> 値として生成されたコードに含まれます。</span><span class="sxs-lookup"><span data-stu-id="cf5c4-103">To support debugging XOML-based workflows with Visual Studio, when workflow projects containing XOML files build, a checksum of the contents of the XOML file is included in the code generated as a <xref:System.Workflow.ComponentModel.Compiler.WorkflowMarkupSourceAttribute.MD5Digest?displayProperty=nameWithType> value.</span></span> <span data-ttu-id="cf5c4-104">.NET Framework 4.7.2 以前のバージョンでは、このチェックサムのハッシュで MD5 アルゴリズムが使用され、FIPS 対応システムで問題が発生していました。</span><span class="sxs-lookup"><span data-stu-id="cf5c4-104">In the .NET Framework 4.7.2 and earlier versions, this checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="cf5c4-105">.NET Framework 4.8 以降、使用されるアルゴリズムは SHA256 になります。</span><span class="sxs-lookup"><span data-stu-id="cf5c4-105">Starting with the .NET Framework 4.8, the algorithm used is SHA256.</span></span> <span data-ttu-id="cf5c4-106">WorkflowMarkupSourceAttribute.MD5Digest との互換性を確保するため、生成されたチェックサムの最初の 16 バイトのみが使用されます。これにより、デバッグ中に問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cf5c4-106">To be compatibile with the WorkflowMarkupSourceAttribute.MD5Digest, only the first 16 bytes of the generated checksum are used.This may cause problems during debugging.</span></span> <span data-ttu-id="cf5c4-107">プロジェクトの再ビルドが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cf5c4-107">You may need to re-build your project.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="cf5c4-108">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="cf5c4-108">Suggestion</span></span>

<span data-ttu-id="cf5c4-109">プロジェクトを再ビルドしても問題が解決しない場合は、`AppContext` スイッチ &quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot; を true に設定してみてください。コードでは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="cf5c4-109">If re-building your project does not solve the problem, try setting the `AppContext` switch &quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot; to true.In code:</span></span>

<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot;, true);&#13;&#10;</code></pre>

<span data-ttu-id="cf5c4-110">構成ファイルでは次のようになります (使用している MSBuild.exe の MSBuild.exe.config で行う必要があります)。</span><span class="sxs-lookup"><span data-stu-id="cf5c4-110">Or in a configuration file (this needs to be in MSBuild.exe.config for the MSBuild.exe that you are using):</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="cf5c4-111">名前</span><span class="sxs-lookup"><span data-stu-id="cf5c4-111">Name</span></span>    | <span data-ttu-id="cf5c4-112">[値]</span><span class="sxs-lookup"><span data-stu-id="cf5c4-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="cf5c4-113">スコープ</span><span class="sxs-lookup"><span data-stu-id="cf5c4-113">Scope</span></span>   | <span data-ttu-id="cf5c4-114">マイナー</span><span class="sxs-lookup"><span data-stu-id="cf5c4-114">Minor</span></span>       |
| <span data-ttu-id="cf5c4-115">バージョン</span><span class="sxs-lookup"><span data-stu-id="cf5c4-115">Version</span></span> | <span data-ttu-id="cf5c4-116">4.8</span><span class="sxs-lookup"><span data-stu-id="cf5c4-116">4.8</span></span>         |
| <span data-ttu-id="cf5c4-117">種類</span><span class="sxs-lookup"><span data-stu-id="cf5c4-117">Type</span></span>    | <span data-ttu-id="cf5c4-118">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="cf5c4-118">Retargeting</span></span> |
