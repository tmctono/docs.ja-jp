---
ms.openlocfilehash: 72d48d1daa85b6891c122f2fcc5279642253b926
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614836"
---
### <a name="workflow-checksums-changed-from-md5-to-sha1"></a><span data-ttu-id="40d87-101">ワークフローのチェックサムが MD5 から SHA1 に変更</span><span class="sxs-lookup"><span data-stu-id="40d87-101">Workflow checksums changed from MD5 to SHA1</span></span>

#### <a name="details"></a><span data-ttu-id="40d87-102">説明</span><span class="sxs-lookup"><span data-stu-id="40d87-102">Details</span></span>

<span data-ttu-id="40d87-103">Visual Studio によるデバッグをサポートするために、ワークフロー ランタイムによって、ハッシュ アルゴリズムを使用してワークフロー インスタンスのチェックサムが生成されます。</span><span class="sxs-lookup"><span data-stu-id="40d87-103">To support debugging with Visual Studio, the Workflow runtime generates a checksum for a workflow instance using a hashing algorithm.</span></span> <span data-ttu-id="40d87-104">.NET Framework 4.6.2 以前のバージョンでは、ワークフロー チェックサムのハッシュで MD5 アルゴリズムが使用され、FIPS 対応システムで問題が発生していました。</span><span class="sxs-lookup"><span data-stu-id="40d87-104">In the .NET Framework 4.6.2 and earlier versions, workflow checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="40d87-105">.NET Framework 4.7 以降、アルゴリズムは SHA1 になります。</span><span class="sxs-lookup"><span data-stu-id="40d87-105">Starting with the .NET Framework 4.7, the algorithm is SHA1.</span></span> <span data-ttu-id="40d87-106">コードによってチェックサムが永続化されている場合、互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="40d87-106">If your code has persisted these checksums, they will be incompatible.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="40d87-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="40d87-107">Suggestion</span></span>

<span data-ttu-id="40d87-108">チェックサム エラーに起因してコードでワークフロー インスタンスを読み込めない場合、`AppContext` スイッチ &quot;Switch.System.Activities.UseMD5ForWFDebugger&quot; を true に設定してみてください。下のコードをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="40d87-108">If your code is unable to load workflow instances due to a checksum failure, try setting the `AppContext` switch &quot;Switch.System.Activities.UseMD5ForWFDebugger&quot; to true.In code:</span></span>

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseMD5ForWFDebugger", true);
```

<span data-ttu-id="40d87-109">または、次のように構成します。</span><span class="sxs-lookup"><span data-stu-id="40d87-109">Or in configuration:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseMD5ForWFDebugger=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="40d87-110">名前</span><span class="sxs-lookup"><span data-stu-id="40d87-110">Name</span></span>    | <span data-ttu-id="40d87-111">値</span><span class="sxs-lookup"><span data-stu-id="40d87-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="40d87-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="40d87-112">Scope</span></span>   | <span data-ttu-id="40d87-113">マイナー</span><span class="sxs-lookup"><span data-stu-id="40d87-113">Minor</span></span>       |
| <span data-ttu-id="40d87-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="40d87-114">Version</span></span> | <span data-ttu-id="40d87-115">4.7</span><span class="sxs-lookup"><span data-stu-id="40d87-115">4.7</span></span>         |
| <span data-ttu-id="40d87-116">種類</span><span class="sxs-lookup"><span data-stu-id="40d87-116">Type</span></span>    | <span data-ttu-id="40d87-117">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="40d87-117">Retargeting</span></span> |
