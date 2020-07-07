---
ms.openlocfilehash: 946e71f2f466664c8f9fcf4811288ce693a872eb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616270"
---
### <a name="workflow-xaml-checksums-for-symbols-changed-from-sha1-to-sha256"></a><span data-ttu-id="d7502-101">ワークフロー XAML のシンボルのチェックサムが SHA1 から SHA256 に変更</span><span class="sxs-lookup"><span data-stu-id="d7502-101">Workflow XAML checksums for symbols changed from SHA1 to SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="d7502-102">説明</span><span class="sxs-lookup"><span data-stu-id="d7502-102">Details</span></span>

<span data-ttu-id="d7502-103">Visual Studio によるデバッグをサポートするために、ワークフロー ランタイムによって、ハッシュ アルゴリズムを使用してワークフロー XAML ファイルのチェックサムが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d7502-103">To support debugging with Visual Studio, the Workflow runtime generates a checksum for a workflow XAML file using a hashing algorithm.</span></span> <span data-ttu-id="d7502-104">.NET Framework 4.6.2 以前のバージョンでは、ワークフロー チェックサムのハッシュで MD5 アルゴリズムが使用され、FIPS 対応システムで問題が発生していました。</span><span class="sxs-lookup"><span data-stu-id="d7502-104">In the .NET Framework 4.6.2 and earlier versions, workflow checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="d7502-105">.NET Framework 4.7 以降では、既定のアルゴリズムが SHA1 に変更されました。</span><span class="sxs-lookup"><span data-stu-id="d7502-105">Starting with the .NET Framework 4.7, the default algorithm was changed to SHA1.</span></span> <span data-ttu-id="d7502-106">.NET Framework 4.8 以降では、既定のアルゴリズムが SHA256 に変更されました。</span><span class="sxs-lookup"><span data-stu-id="d7502-106">Starting with the .NET Framework 4.8, the default algorithm was changed to SHA256.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d7502-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="d7502-107">Suggestion</span></span>

<span data-ttu-id="d7502-108">チェックサム エラーに起因して、コードでワークフロー インスタンスを読み込めないか、適切なシンボルを見つけられない場合、`AppContext` スイッチ "Switch.System.Activities.UseSHA1HashForDebuggerSymbols" を `true` に設定してみてください。</span><span class="sxs-lookup"><span data-stu-id="d7502-108">If your code is unable to load workflow instances or to find appropriate symbols due to a checksum failure, try setting the `AppContext` switch "Switch.System.Activities.UseSHA1HashForDebuggerSymbols" to `true`.</span></span> <span data-ttu-id="d7502-109">コードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d7502-109">In code:</span></span>

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseSHA1HashForDebuggerSymbols", true);
```

<span data-ttu-id="d7502-110">または、次のように構成します。</span><span class="sxs-lookup"><span data-stu-id="d7502-110">Or in configuration:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseSHA1HashForDebuggerSymbols=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="d7502-111">名前</span><span class="sxs-lookup"><span data-stu-id="d7502-111">Name</span></span>    | <span data-ttu-id="d7502-112">[値]</span><span class="sxs-lookup"><span data-stu-id="d7502-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d7502-113">スコープ</span><span class="sxs-lookup"><span data-stu-id="d7502-113">Scope</span></span>   | <span data-ttu-id="d7502-114">マイナー</span><span class="sxs-lookup"><span data-stu-id="d7502-114">Minor</span></span>       |
| <span data-ttu-id="d7502-115">バージョン</span><span class="sxs-lookup"><span data-stu-id="d7502-115">Version</span></span> | <span data-ttu-id="d7502-116">4.8</span><span class="sxs-lookup"><span data-stu-id="d7502-116">4.8</span></span>         |
| <span data-ttu-id="d7502-117">種類</span><span class="sxs-lookup"><span data-stu-id="d7502-117">Type</span></span>    | <span data-ttu-id="d7502-118">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="d7502-118">Retargeting</span></span> |
