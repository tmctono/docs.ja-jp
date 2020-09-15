---
ms.openlocfilehash: 4d410811095786b33580d25f6c6eab3ac2f27148
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616104"
---
### <a name="resolveassemblyreference-task-now-warns-of-dependencies-with-the-wrong-architecture"></a><span data-ttu-id="724be-101">ResolveAssemblyReference タスクは、正しくないアーキテクチャとの依存関係に関する警告を表示するようになりました</span><span class="sxs-lookup"><span data-stu-id="724be-101">ResolveAssemblyReference task now warns of dependencies with the wrong architecture</span></span>

#### <a name="details"></a><span data-ttu-id="724be-102">説明</span><span class="sxs-lookup"><span data-stu-id="724be-102">Details</span></span>

<span data-ttu-id="724be-103">タスクは警告 MSB3270 を生成します。これは参照または依存関係がアプリのアーキテクチャと一致しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="724be-103">The task emits a warning, MSB3270, which indicates that a reference or any of its dependencies does not match the app's architecture.</span></span> <span data-ttu-id="724be-104">たとえば、`AnyCPU` オプションでコンパイルされたアプリに x86 参照が含まれる場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="724be-104">For example, this occurs if an app that was compiled with the `AnyCPU` option includes an x86 reference.</span></span> <span data-ttu-id="724be-105">このようなシナリオは、実行時にアプリでエラーが起こった場合に発生することがあります (この場合は、アプリが x64 プロセスとして配置されている場合)。</span><span class="sxs-lookup"><span data-stu-id="724be-105">Such a scenario could result in an app failure at run time (in this case, if the app is deployed as an x64 process).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="724be-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="724be-106">Suggestion</span></span>

<span data-ttu-id="724be-107">影響には 2 つの領域があります。</span><span class="sxs-lookup"><span data-stu-id="724be-107">There are two areas of impact:</span></span>

- <span data-ttu-id="724be-108">再コンパイルすると、アプリが MSBuild の以前のバージョンでコンパイルされたときには現れなかった警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="724be-108">Recompilation generates warnings that did not appear when the app was compiled under a previous version of MSBuild.</span></span> <span data-ttu-id="724be-109">ただし、警告はランタイム エラーの可能性のある原因を特定するため、調査と対処が必要です。</span><span class="sxs-lookup"><span data-stu-id="724be-109">However, because the warning identifies a possible source of runtime failure, it should be investigated and addressed.</span></span>
- <span data-ttu-id="724be-110">警告がエラーとして扱われると、アプリはコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="724be-110">If warnings are treated as errors, the app will fail to compile.</span></span>

| <span data-ttu-id="724be-111">名前</span><span class="sxs-lookup"><span data-stu-id="724be-111">Name</span></span>    | <span data-ttu-id="724be-112">[値]</span><span class="sxs-lookup"><span data-stu-id="724be-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="724be-113">スコープ</span><span class="sxs-lookup"><span data-stu-id="724be-113">Scope</span></span>   | <span data-ttu-id="724be-114">マイナー</span><span class="sxs-lookup"><span data-stu-id="724be-114">Minor</span></span>       |
| <span data-ttu-id="724be-115">バージョン</span><span class="sxs-lookup"><span data-stu-id="724be-115">Version</span></span> | <span data-ttu-id="724be-116">4.5.1</span><span class="sxs-lookup"><span data-stu-id="724be-116">4.5.1</span></span>       |
| <span data-ttu-id="724be-117">種類</span><span class="sxs-lookup"><span data-stu-id="724be-117">Type</span></span>    | <span data-ttu-id="724be-118">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="724be-118">Retargeting</span></span> |
