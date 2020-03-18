---
title: オープン ソース .NET ライブラリのガイダンス
description: 高品質の .NET ライブラリを作成するための開発者向けのベスト プラクティスとしての推奨事項。
ms.date: 10/17/2018
ms.openlocfilehash: 4c76dfae6ffc39df7f15381be64e33657067d79d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "76731427"
---
# <a name="open-source-library-guidance"></a><span data-ttu-id="46454-103">オープン ソース ライブラリのガイダンス</span><span class="sxs-lookup"><span data-stu-id="46454-103">Open-source library guidance</span></span>

<span data-ttu-id="46454-104">このガイドでは、高品質の .NET ライブラリを作成するための開発者向け推奨事項を説明します。</span><span class="sxs-lookup"><span data-stu-id="46454-104">This guidance provides recommendations for developers to create high-quality .NET libraries.</span></span> <span data-ttu-id="46454-105">このドキュメントでは、.NET ライブラリを構築するときの、"*方法*" ではなく、"*内容*" と "*理由*" について説明します。</span><span class="sxs-lookup"><span data-stu-id="46454-105">This documentation focuses on the *what* and the *why* when building a .NET library, not the *how*.</span></span>

<span data-ttu-id="46454-106">高品質のオープン ソースの .NET ライブラリの特徴:</span><span class="sxs-lookup"><span data-stu-id="46454-106">Aspects of high-quality open-source .NET libraries:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="46454-107">**包括的である** - 多くのプラットフォーム、プログラミング言語、アプリケーションをサポートするように、適切な .NET ライブラリで対応しています。</span><span class="sxs-lookup"><span data-stu-id="46454-107">**Inclusive** - Good .NET libraries strive to support many platforms, programming languages, and applications.</span></span>
> * <span data-ttu-id="46454-108">**安定している** - 適切な .NET ライブラリが .NET エコシステム内で共存しており、多くのライブラリを使用してビルドされたアプリケーション内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="46454-108">**Stable** - Good .NET libraries coexist in the .NET ecosystem, running in applications built with many libraries.</span></span>
> * <span data-ttu-id="46454-109">**進化するように設計されている** - .NET ライブラリは、既存のユーザーをサポートしながら、時間の経過と共に改善され進化します。</span><span class="sxs-lookup"><span data-stu-id="46454-109">**Designed to evolve** - .NET libraries should improve and evolve over time, while supporting existing users.</span></span>
> * <span data-ttu-id="46454-110">**デバッグできる** - .NET ライブラリでは、最新のツールを使用してユーザー向けの優れたデバッグ エクスペリエンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="46454-110">**Debuggable** - .NET libraries should use the latest tools to create a great debugging experience for users.</span></span>
> * <span data-ttu-id="46454-111">**信頼されている** - .NET ライブラリは、セキュリティのベスト プラクティスを使用して NuGet に発行することにより、開発者から信頼されています。</span><span class="sxs-lookup"><span data-stu-id="46454-111">**Trusted** - .NET libraries have developers' trust by publishing to NuGet using security best practices.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="46454-112">開始するには</span><span class="sxs-lookup"><span data-stu-id="46454-112">Get Started</span></span>](./get-started.md)

## <a name="types-of-recommendations"></a><span data-ttu-id="46454-113">推奨事項の種類</span><span class="sxs-lookup"><span data-stu-id="46454-113">Types of recommendations</span></span>

<span data-ttu-id="46454-114">各記事で 4 種類の推奨事項 (**実施**、**検討**、**回避**、**実施しない**) が提示されます。</span><span class="sxs-lookup"><span data-stu-id="46454-114">Each article presents four types of recommendations: **Do**, **Consider**, **Avoid**, and **Do not**.</span></span> <span data-ttu-id="46454-115">推奨事項の種類によって、その推奨設定にどの程度厳密に従う必要があるかが示されます。</span><span class="sxs-lookup"><span data-stu-id="46454-115">The type of recommendation indicates how strongly it should be followed.</span></span>

<span data-ttu-id="46454-116">**実施**の推奨事項にはほとんど常に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="46454-116">You should almost always follow a **Do** recommendation.</span></span> <span data-ttu-id="46454-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="46454-117">For example:</span></span>

<span data-ttu-id="46454-118">NuGet パッケージを使用してご利用のライブラリの配布を✔️ 実施してください。</span><span class="sxs-lookup"><span data-stu-id="46454-118">✔️ DO distribute your library using a NuGet package.</span></span>

<span data-ttu-id="46454-119">その一方で、**検討**推奨事項は、一般に実施する必要がありますが、ルールには正当な例外があり、ガイダンスに従っていないことを気する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="46454-119">On the other hand, **Consider** recommendations should generally be followed, but there are legitimate exceptions to the rule and you shouldn't feel bad about not following the guidance:</span></span>

<span data-ttu-id="46454-120">ご利用の NuGet パッケージのバージョンに [SemVer 2.0.0](https://semver.org/) を使用することを ✔️ 検討してください。</span><span class="sxs-lookup"><span data-stu-id="46454-120">✔️ CONSIDER using [SemVer 2.0.0](https://semver.org/) to version your NuGet package.</span></span>

<span data-ttu-id="46454-121">**回避**の推奨事項は一般には良いアイデアではありませんが、規則に違反することが効果的である場合があります。</span><span class="sxs-lookup"><span data-stu-id="46454-121">**Avoid** recommendations mention things that are generally not a good idea, but breaking the rule sometimes makes sense:</span></span>

<span data-ttu-id="46454-122">バージョンが正確である必要がある NuGet パッケージ参照は ❌ 回避してください。</span><span class="sxs-lookup"><span data-stu-id="46454-122">❌ AVOID NuGet package references that demand an exact version.</span></span>

<span data-ttu-id="46454-123">最後に、**実施しない**の推奨事項は、ほとんどの場合でやってはいけないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="46454-123">And finally, **Do not** recommendations indicate something you should almost never do:</span></span>

<span data-ttu-id="46454-124">ご利用のライブラリで、厳密な名前が指定されたバージョンおよび厳密でない名前が指定されたバージョンを ❌ 発行しないでください。</span><span class="sxs-lookup"><span data-stu-id="46454-124">❌ DO NOT publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="46454-125">たとえば、`Contoso.Api` と`Contoso.Api.StrongNamed` です。</span><span class="sxs-lookup"><span data-stu-id="46454-125">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="46454-126">次へ</span><span class="sxs-lookup"><span data-stu-id="46454-126">Next</span></span>](get-started.md)
