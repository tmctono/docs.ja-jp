---
ms.openlocfilehash: c7500550cd9714a9788a7dea68af04823f000f7f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614794"
---
### <a name="stack-traces-obtained-when-using-portable-pdbs-now-include-source-file-and-line-information-if-requested"></a><span data-ttu-id="cf3ed-101">ポータブル PDB の使用時に取得されるスタック トレースに、必要に応じてソース ファイルと行情報が含まれるようになった</span><span class="sxs-lookup"><span data-stu-id="cf3ed-101">Stack traces obtained when using portable PDBs now include source file and line information if requested</span></span>

#### <a name="details"></a><span data-ttu-id="cf3ed-102">説明</span><span class="sxs-lookup"><span data-stu-id="cf3ed-102">Details</span></span>

<span data-ttu-id="cf3ed-103">.NET Framework 4.7.2 以降では、ポータブル PDB の使用時に取得されるスタック トレースに、要求に応じてソース ファイルと行情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cf3ed-103">Starting with .NET Framework 4.7.2, stack traces obtained when using portable PDBs include source file and line information when requested.</span></span> <span data-ttu-id="cf3ed-104">.NET Framework 4.7.2 より前のバージョンでは、明示的に要求された場合でもポータブル PDB の使用時にソース ファイルと行情報は利用できません。</span><span class="sxs-lookup"><span data-stu-id="cf3ed-104">In versions prior to .NET Framework 4.7.2, source file and line information would be unavailable when using portable PDBs even if explicitly requested.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="cf3ed-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="cf3ed-105">Suggestion</span></span>

<span data-ttu-id="cf3ed-106">.NET Framework 4.7.2 を対象とするアプリケーションでは、望ましくない場合、`app.config` ファイルの `<runtime>` セクションに以下を追加することで、ポータブル PDB の使用時にソース ファイルと行情報の選択を解除できます。</span><span class="sxs-lookup"><span data-stu-id="cf3ed-106">For applications that target the .NET Framework 4.7.2, you can opt out of the source file and line information when using portable PDBs if it is not desirable by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=true" />
</runtime>
```

<span data-ttu-id="cf3ed-107">以前のバージョンの .NET Framework を対象とするが、.NET Framework 4.7.2 以降で実行するアプリケーションの場合は、`app.config` ファイルの `<runtime>` セクションに以下を追加することで、ポータブル PDB の使用時にソース ファイルと行情報を選択できます。</span><span class="sxs-lookup"><span data-stu-id="cf3ed-107">For applications that target earlier versions of the .NET Framework but run on the .NET Framework 4.7.2 or later, you can opt in to the source file and line information when using portable PDBs by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=false" />
</runtime>
```

| <span data-ttu-id="cf3ed-108">名前</span><span class="sxs-lookup"><span data-stu-id="cf3ed-108">Name</span></span>    | <span data-ttu-id="cf3ed-109">[値]</span><span class="sxs-lookup"><span data-stu-id="cf3ed-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="cf3ed-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="cf3ed-110">Scope</span></span>   | <span data-ttu-id="cf3ed-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="cf3ed-111">Edge</span></span>        |
| <span data-ttu-id="cf3ed-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="cf3ed-112">Version</span></span> | <span data-ttu-id="cf3ed-113">4.7.2</span><span class="sxs-lookup"><span data-stu-id="cf3ed-113">4.7.2</span></span>       |
| <span data-ttu-id="cf3ed-114">種類</span><span class="sxs-lookup"><span data-stu-id="cf3ed-114">Type</span></span>    | <span data-ttu-id="cf3ed-115">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="cf3ed-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="cf3ed-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="cf3ed-116">Affected APIs</span></span>

- <xref:System.Diagnostics.StackTrace.%23ctor(System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Int32,System.Boolean)>
