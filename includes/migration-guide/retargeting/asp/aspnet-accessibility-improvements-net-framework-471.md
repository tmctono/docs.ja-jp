---
ms.openlocfilehash: 418bcdca1e9a325894891d7b0e080ce035e2d1b4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614684"
---
### <a name="aspnet-accessibility-improvements-in-net-framework-471"></a><span data-ttu-id="7382b-101">.NET Framework 4.7.1 の ASP.NET アクセシビリティ機能の強化</span><span class="sxs-lookup"><span data-stu-id="7382b-101">ASP.NET Accessibility Improvements in .NET Framework 4.7.1</span></span>

#### <a name="details"></a><span data-ttu-id="7382b-102">説明</span><span class="sxs-lookup"><span data-stu-id="7382b-102">Details</span></span>

<span data-ttu-id="7382b-103">.NET Framework 4.7.1 以降、ASP.NET のお客様のサポートを改善する目的で、ASP.NET Web コントロールによる Visual Studio のアクセシビリティ テクノロジの処理方法が向上しています。</span><span class="sxs-lookup"><span data-stu-id="7382b-103">Starting with the .NET Framework 4.7.1, ASP.NET has improved how ASP.NET Web Controls work with accessibility technology in Visual Studio to better support ASP.NET customers.</span></span>  <span data-ttu-id="7382b-104">この機能強化には次の変更内容が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7382b-104">These include the following changes:</span></span>

- <span data-ttu-id="7382b-105">[詳細の表示] ウィザードの [フィールドの追加] ダイアログや ListView ウィザードの [ListView の構成] ダイアログなど、コントロールで不足していた UI アクセシビリティ パターンを実装するための変更。</span><span class="sxs-lookup"><span data-stu-id="7382b-105">Changes to implement missing UI accessibility patterns in controls, like the Add Field dialog in the Details View wizard, or the Configure ListView dialog of the ListView wizard.</span></span>
- <span data-ttu-id="7382b-106">データ ページャー フィールド エディターなど、ハイ コントラスト モードでの表示を改善するための変更。</span><span class="sxs-lookup"><span data-stu-id="7382b-106">Changes to improve the display in High Contrast mode, like the Data Pager Fields Editor.</span></span>
- <span data-ttu-id="7382b-107">DataPager コントロールの [ページャーのフィールドを編集] ウィザードの [フィールド] ダイアログ、[ObjectContext の構成] ダイアログ、[データ ソースの構成] ウィザードの [データの選択の構成] ダイアログなど、キーボードの操作性を改善するための変更。</span><span class="sxs-lookup"><span data-stu-id="7382b-107">Changes to improve the keyboard navigation experiences for controls, like the Fields dialog in the Edit Pager Fields wizard of the DataPager control, the Configure ObjectContext dialog, or the Configure Data Selection dialog of the Configure Data Source wizard.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7382b-108">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="7382b-108">Suggestion</span></span>

<span data-ttu-id="7382b-109">**以上の変更を選択する方法と選択しない方法** Visual Studio デザイナーの場合、.NET Framework 4.7.1 以降で実行しなければ、以上の変更から改善を得ることはありません。</span><span class="sxs-lookup"><span data-stu-id="7382b-109">**How to opt in or out of these changes** In order for the Visual Studio Designer to benefit from these changes, it must run on the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="7382b-110">Web アプリケーションの場合、次のいずれかの手法をとることで、以上の変更によって機能が強化されます。</span><span class="sxs-lookup"><span data-stu-id="7382b-110">The web application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="7382b-111">Visual Studio 2017 15.3 以降をインストールする。このバージョンからは既定で、次の項目にある AppContext スイッチで新しいアクセシビリティ機能に対応しています。</span><span class="sxs-lookup"><span data-stu-id="7382b-111">Install Visual Studio 2017 15.3 or later, which supports the new accessibility features with the following AppContext Switch by default.</span></span>
- <span data-ttu-id="7382b-112">下の例のように、devenv.exe.config ファイルの `<runtime>` セクションに `Switch.UseLegacyAccessibilityFeatures` AppContext スイッチを追加し、それを `false` に設定することで、以前のアクセシビリティ動作を無効にする。</span><span class="sxs-lookup"><span data-stu-id="7382b-112">Opt out of the legacy accessibility behaviors by adding the `Switch.UseLegacyAccessibilityFeatures` AppContext switch to the `<runtime>` section in the devenv.exe.config file and setting it to `false`, as the following example shows.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
<runtime>
...
<!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false'  -->
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
...
</runtime>
</configuration>
```

<span data-ttu-id="7382b-113">.NET Framework 4.7.1 以降を対象とするアプリケーションで以前のアクセシビリティ動作を残す場合、この AppContext スイッチを明示的に `true` に設定することで以前のアクセシビリティ機能を選択できます。</span><span class="sxs-lookup"><span data-stu-id="7382b-113">Applications that target the .NET Framework 4.7.1 or later and want to preserve the legacy accessibility behavior can opt in to the use of legacy accessibility features by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="7382b-114">名前</span><span class="sxs-lookup"><span data-stu-id="7382b-114">Name</span></span>    | <span data-ttu-id="7382b-115">[値]</span><span class="sxs-lookup"><span data-stu-id="7382b-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7382b-116">スコープ</span><span class="sxs-lookup"><span data-stu-id="7382b-116">Scope</span></span>   | <span data-ttu-id="7382b-117">マイナー</span><span class="sxs-lookup"><span data-stu-id="7382b-117">Minor</span></span>       |
| <span data-ttu-id="7382b-118">バージョン</span><span class="sxs-lookup"><span data-stu-id="7382b-118">Version</span></span> | <span data-ttu-id="7382b-119">4.7.1</span><span class="sxs-lookup"><span data-stu-id="7382b-119">4.7.1</span></span>       |
| <span data-ttu-id="7382b-120">種類</span><span class="sxs-lookup"><span data-stu-id="7382b-120">Type</span></span>    | <span data-ttu-id="7382b-121">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="7382b-121">Retargeting</span></span> |
