---
title: 機能フラグ
description: Azure アプリ構成を利用するクラウドネイティブアプリケーションで機能フラグを実装する
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: be4ab307069065975dc22d6bd984e12a2ea1457d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540466"
---
# <a name="feature-flags"></a><span data-ttu-id="8594a-103">機能フラグ</span><span class="sxs-lookup"><span data-stu-id="8594a-103">Feature flags</span></span>

<span data-ttu-id="8594a-104">第1章では、クラウドネイティブの速度と機敏性が非常に高くなっています。</span><span class="sxs-lookup"><span data-stu-id="8594a-104">In chapter 1, we affirmed that cloud native is much about speed and agility.</span></span> <span data-ttu-id="8594a-105">ユーザーは、迅速な応答性と革新的な機能を期待し、ダウンタイムをゼロにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8594a-105">Users expect rapid responsiveness, innovative features, and zero downtime.</span></span> <span data-ttu-id="8594a-106">`Feature flags` は、クラウドネイティブアプリケーションの俊敏性を向上させるための最新の展開手法です。</span><span class="sxs-lookup"><span data-stu-id="8594a-106">`Feature flags` are a modern deployment technique that helps increase agility for cloud-native applications.</span></span> <span data-ttu-id="8594a-107">新しい機能を運用環境に展開することはできますが、その可用性は制限されます。</span><span class="sxs-lookup"><span data-stu-id="8594a-107">They enable you to deploy new features into a production environment, but restrict their availability.</span></span> <span data-ttu-id="8594a-108">スイッチのフリックを使用すると、アプリを再起動したり新しいコードを展開したりせずに、特定のユーザーに対して新しい機能をアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="8594a-108">With the flick of a switch, you can activate a new feature for specific users without restarting the app or deploying new code.</span></span> <span data-ttu-id="8594a-109">これらは、新機能のリリースをコード配置から分離します。</span><span class="sxs-lookup"><span data-stu-id="8594a-109">They separate the release of new features from their code deployment.</span></span>

<span data-ttu-id="8594a-110">機能フラグは、実行時にユーザーの機能の可視性を制御する条件付きロジックに基づいて構築されます。</span><span class="sxs-lookup"><span data-stu-id="8594a-110">Feature flags are built upon conditional logic that control visibility of functionality for users at runtime.</span></span> <span data-ttu-id="8594a-111">最新のクラウドネイティブシステムでは、新しい機能を早い段階で運用環境にデプロイすることは一般的ですが、限定された対象ユーザーを使用してテストします。</span><span class="sxs-lookup"><span data-stu-id="8594a-111">In modern cloud-native systems, it's common to deploy new features into production early, but test them with a limited audience.</span></span> <span data-ttu-id="8594a-112">信頼度が高くなるにつれて、機能をより広範な対象ユーザーに段階的にロールアウトできます。</span><span class="sxs-lookup"><span data-stu-id="8594a-112">As confidence increases, the feature can be incrementally rolled out to wider audiences.</span></span>

<span data-ttu-id="8594a-113">機能フラグのその他のユースケースは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8594a-113">Other use cases for feature flags include:</span></span>

- <span data-ttu-id="8594a-114">Premium 機能を特定の顧客グループに限定して、より高いサブスクリプション料金を支払うことができます。</span><span class="sxs-lookup"><span data-stu-id="8594a-114">Restrict premium functionality to specific customer groups willing to pay higher subscription fees.</span></span>
- <span data-ttu-id="8594a-115">問題のある機能を迅速に非アクティブ化してシステムを安定化し、ロールバックや即時修正プログラムのリスクを回避します。</span><span class="sxs-lookup"><span data-stu-id="8594a-115">Stabilize a system by quickly deactivating a problem feature, avoiding the risks of a rollback or immediate hotfix.</span></span>
- <span data-ttu-id="8594a-116">ピーク時の使用期間中にリソース使用率が高いオプション機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="8594a-116">Disable an optional feature with high resource consumption during peak usage periods.</span></span>
- <span data-ttu-id="8594a-117">`experimental feature releases`小規模のユーザーセグメントに対して、実現可能性と人気度を検証します。</span><span class="sxs-lookup"><span data-stu-id="8594a-117">Conduct `experimental feature releases` to small user segments to validate feasibility and popularity.</span></span>

<span data-ttu-id="8594a-118">機能フラグも `trunk-based` 開発を促進します。</span><span class="sxs-lookup"><span data-stu-id="8594a-118">Feature flags also promote `trunk-based` development.</span></span> <span data-ttu-id="8594a-119">これは、開発者が1つの分岐の機能に対して共同作業を行うソース管理の分岐モデルです。</span><span class="sxs-lookup"><span data-stu-id="8594a-119">It's a source-control branching model where developers collaborate on features in a single branch.</span></span> <span data-ttu-id="8594a-120">この方法では、多数の実行時間の長い機能ブランチをマージするリスクと複雑さが最小限に抑えられます。</span><span class="sxs-lookup"><span data-stu-id="8594a-120">The approach minimizes the risk and complexity of merging large numbers of long-running feature branches.</span></span> <span data-ttu-id="8594a-121">機能は、アクティブ化されるまで使用できません。</span><span class="sxs-lookup"><span data-stu-id="8594a-121">Features are unavailable until activated.</span></span>

## <a name="implementing-feature-flags"></a><span data-ttu-id="8594a-122">機能フラグの実装</span><span class="sxs-lookup"><span data-stu-id="8594a-122">Implementing feature flags</span></span>

<span data-ttu-id="8594a-123">主要な特徴フラグは、単純なへの参照です `decision object` 。</span><span class="sxs-lookup"><span data-stu-id="8594a-123">At its core, a feature flag is a reference to a simple `decision object`.</span></span> <span data-ttu-id="8594a-124">またはのブール値の状態を返し `on` `off` ます。</span><span class="sxs-lookup"><span data-stu-id="8594a-124">It returns a Boolean state of `on` or `off`.</span></span> <span data-ttu-id="8594a-125">通常、このフラグは、機能機能をカプセル化するコードブロックをラップします。</span><span class="sxs-lookup"><span data-stu-id="8594a-125">The flag typically wraps a block of code that encapsulates a feature capability.</span></span> <span data-ttu-id="8594a-126">フラグの状態によって、そのコードブロックが特定のユーザーに対して実行されるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="8594a-126">The state of the flag determines whether that code block executes for a given user.</span></span> <span data-ttu-id="8594a-127">図10-11 に実装を示します。</span><span class="sxs-lookup"><span data-stu-id="8594a-127">Figure 10-11 shows the implementation.</span></span>

```csharp
if (featureFlag) {
    // Run this code block if the featureFlag value is true
} else {
    // Run this code block if the featureFlag value is false
}
```

<span data-ttu-id="8594a-128">**図 10-11** -単純な機能フラグの実装。</span><span class="sxs-lookup"><span data-stu-id="8594a-128">**Figure 10-11** - Simple feature flag implementation.</span></span>

<span data-ttu-id="8594a-129">この方法では、機能コードから意思決定ロジックを分離する方法に注意してください。</span><span class="sxs-lookup"><span data-stu-id="8594a-129">Note how this approach separates the decision logic from the feature code.</span></span>

<span data-ttu-id="8594a-130">第1章では、「」について説明しました `Twelve-Factor App` 。</span><span class="sxs-lookup"><span data-stu-id="8594a-130">In chapter 1, we discussed the `Twelve-Factor App`.</span></span> <span data-ttu-id="8594a-131">構成設定をアプリケーションの実行可能コードから外部に保持することを推奨するガイダンスです。</span><span class="sxs-lookup"><span data-stu-id="8594a-131">The guidance recommended keeping configuration settings external from application executable code.</span></span> <span data-ttu-id="8594a-132">必要に応じて、外部ソースから設定を読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="8594a-132">When needed, settings can be read in from the external source.</span></span> <span data-ttu-id="8594a-133">機能フラグの構成値は、コードベースから独立している必要もあります。</span><span class="sxs-lookup"><span data-stu-id="8594a-133">Feature flag configuration values should also be independent from their codebase.</span></span> <span data-ttu-id="8594a-134">別のリポジトリに外部化するフラグを設定することにより、アプリケーションを変更して再デプロイしなくてもフラグの状態を変更できます。</span><span class="sxs-lookup"><span data-stu-id="8594a-134">By externalizing flag configuration in a separate repository, you can change flag state without modifying and redeploying the application.</span></span>

<span data-ttu-id="8594a-135">[Azure アプリ構成](https://docs.microsoft.com/azure/azure-app-configuration/overview) では、機能フラグの一元的なリポジトリが提供されます。</span><span class="sxs-lookup"><span data-stu-id="8594a-135">[Azure App Configuration](https://docs.microsoft.com/azure/azure-app-configuration/overview) provides a centralized repository for feature flags.</span></span> <span data-ttu-id="8594a-136">この機能を使用すると、さまざまな種類の特徴フラグを定義し、その状態を迅速かつ自信を持って操作できます。</span><span class="sxs-lookup"><span data-stu-id="8594a-136">With it, you define different kinds of feature flags and manipulate their states quickly and confidently.</span></span> <span data-ttu-id="8594a-137">アプリ構成クライアントライブラリをアプリケーションに追加して、機能フラグの機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8594a-137">You add the App Configuration client libraries to your application to enable feature flag functionality.</span></span> <span data-ttu-id="8594a-138">さまざまなプログラミング言語フレームワークがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8594a-138">Various programming language frameworks are supported.</span></span>

<span data-ttu-id="8594a-139">機能フラグは、 [ASP.NET Core サービス](https://docs.microsoft.com/azure/azure-app-configuration/use-feature-flags-dotnet-core)に簡単に実装できます。</span><span class="sxs-lookup"><span data-stu-id="8594a-139">Feature flags can be easily implemented in an [ASP.NET Core service](https://docs.microsoft.com/azure/azure-app-configuration/use-feature-flags-dotnet-core).</span></span> <span data-ttu-id="8594a-140">.NET 機能管理ライブラリとアプリ構成プロバイダーをインストールすると、宣言によって機能フラグをコードに追加できます。</span><span class="sxs-lookup"><span data-stu-id="8594a-140">Installing the .NET Feature Management libraries and App Configuration provider enable you to declaratively add feature flags to your code.</span></span> <span data-ttu-id="8594a-141">属性を有効にすると、 `FeatureGate` コードベースで if ステートメントを手動で作成する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="8594a-141">They enable `FeatureGate` attributes so that you don't have to manually write if statements across your codebase.</span></span>

<span data-ttu-id="8594a-142">Startup クラスで構成すると、コントローラー、アクション、またはミドルウェアレベルで機能フラグ機能を追加できます。</span><span class="sxs-lookup"><span data-stu-id="8594a-142">Once configured in your Startup class, you can add feature flag functionality at the controller, action, or middleware level.</span></span> <span data-ttu-id="8594a-143">図10-12 は、コントローラーとアクションの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="8594a-143">Figure 10-12 presents controller and action implementation:</span></span>

```csharp
[FeatureGate(MyFeatureFlags.FeatureA)]
public class ProductController : Controller
{
    ...
}
```

```csharp
[FeatureGate(MyFeatureFlags.FeatureA)]
public IActionResult UpdateProductStatus()
{
    return ObjectResult(ProductDto);
}
```

<span data-ttu-id="8594a-144">**図 10-12** -コントローラーとアクションでの機能フラグの実装</span><span class="sxs-lookup"><span data-stu-id="8594a-144">**Figure 10-12** - Feature flag implementation in a controller and action.</span></span>

<span data-ttu-id="8594a-145">機能フラグが無効になっている場合、ユーザーには応答本文のない 404 (見つかりません) 状態コードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8594a-145">If a feature flag is disabled, the user will receive a 404 (Not Found) status code with no response body.</span></span>

<span data-ttu-id="8594a-146">機能フラグは、C# クラスに直接挿入することもできます。</span><span class="sxs-lookup"><span data-stu-id="8594a-146">Feature flags can also be injected directly into C# classes.</span></span> <span data-ttu-id="8594a-147">図10-13 は、機能フラグの挿入を示しています。</span><span class="sxs-lookup"><span data-stu-id="8594a-147">Figure 10-13 shows feature flag injection:</span></span>

```csharp
public class ProductController : Controller
{
    private readonly IFeatureManager _featureManager;

    public ProductController(IFeatureManager featureManager)
    {
        _featureManager = featureManager;
    }
}
```

<span data-ttu-id="8594a-148">**図 10-13** -クラスへの機能フラグの挿入</span><span class="sxs-lookup"><span data-stu-id="8594a-148">**Figure 10-13** - Feature flag injection into a class.</span></span>

<span data-ttu-id="8594a-149">機能管理ライブラリは、バックグラウンドで機能フラグのライフサイクルを管理します。</span><span class="sxs-lookup"><span data-stu-id="8594a-149">The Feature Management libraries manage the feature flag lifecycle behind the scenes.</span></span> <span data-ttu-id="8594a-150">たとえば、構成ストアへの呼び出しの数を最小限に抑えるために、ライブラリは指定された期間のフラグの状態をキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="8594a-150">For example, to minimize high numbers of calls to the configuration store, the libraries cache flag states for a specified duration.</span></span> <span data-ttu-id="8594a-151">要求の呼び出し中にフラグの状態の不変性を保証できます。</span><span class="sxs-lookup"><span data-stu-id="8594a-151">They can guarantee the immutability of flag states during a request call.</span></span> <span data-ttu-id="8594a-152">また、も提供 `Point-in-time snapshot` します。</span><span class="sxs-lookup"><span data-stu-id="8594a-152">They also offer a `Point-in-time snapshot`.</span></span> <span data-ttu-id="8594a-153">任意のキー値の履歴を再構築し、過去7日以内の任意の時点でその過去の値を提供できます。</span><span class="sxs-lookup"><span data-stu-id="8594a-153">You can reconstruct the history of any key-value and provide its past value at any moment within the previous seven days.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="8594a-154">[前へ](devops.md)
>[次へ](infrastructure-as-code.md)</span><span class="sxs-lookup"><span data-stu-id="8594a-154">[Previous](devops.md)
[Next](infrastructure-as-code.md)</span></span>
