---
title: '軽減策: ポインター ベースのタッチおよびスタイラスのサポート'
description: .NET Framework 4.7 を対象とする WPF アプリで任意の WPF タッチまたはスタイラス スタックを有効にした場合の影響について説明します。
ms.date: 04/07/2017
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- WPF pointer-based touch and stylus stack
ms.assetid: f99126b5-c396-48f9-8233-8f36b4c9e717
ms.openlocfilehash: d0c0effeaa727c615dddc3b92cdd34aafde65705
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475425"
---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a><span data-ttu-id="164cd-103">軽減策:ポインター ベースのタッチおよびスタイラスのサポート</span><span class="sxs-lookup"><span data-stu-id="164cd-103">Mitigation: Pointer-based Touch and Stylus Support</span></span>

<span data-ttu-id="164cd-104">.NET Framework 4.7 を対象とし、Windows 10 Creators Update 以降の Windows システムで実行されている WPF アプリケーションは、オプションの `WM_POINTER` ベースの WPF タッチまたはスタイラスのスタックを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="164cd-104">WPF applications that target the .NET Framework 4.7 and are running on Windows starting with Windows 10 Creators Update can enable an optional `WM_POINTER`-based WPF touch/stylus stack.</span></span>

## <a name="impact"></a><span data-ttu-id="164cd-105">影響</span><span class="sxs-lookup"><span data-stu-id="164cd-105">Impact</span></span>

<span data-ttu-id="164cd-106">ポインター ベースのタッチ/スタイラス サポートを明示的に有効にしていない開発者は、WPF タッチ/スタイラス動作の変更を確認できません。</span><span class="sxs-lookup"><span data-stu-id="164cd-106">Developers who do not explicitly enable pointer-based touch/stylus support should see no change in WPF touch/stylus behavior.</span></span>

<span data-ttu-id="164cd-107">オプションの `WM_POINTER` ベースのタッチ/スタイラス スタックに関する現在の既知の問題を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="164cd-107">The following are current known issues with the optional `WM_POINTER`-based touch/stylus stack:</span></span>

- <span data-ttu-id="164cd-108">リアルタイム インクがサポートされない。</span><span class="sxs-lookup"><span data-stu-id="164cd-108">No support for real-time inking.</span></span>

   <span data-ttu-id="164cd-109">インクとスタイラス プラグインがまだ機能している間は、UI スレッドで処理されますが、パフォーマンスの低下につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="164cd-109">While inking and stylus plugins still work, they are processed on the UI thread, which can lead to poor performance.</span></span>

- <span data-ttu-id="164cd-110">プロモーションの変更により、タッチ/スタイラス イベントからマウス イベントに動作が変更される。</span><span class="sxs-lookup"><span data-stu-id="164cd-110">Behavioral changes due to changes in promotion from touch/stylus events to mouse events.</span></span>

  - <span data-ttu-id="164cd-111">操作の動作が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="164cd-111">Manipulation may behave differently.</span></span>

  - <span data-ttu-id="164cd-112">ドラッグ/ドロップでは、タッチ入力の適切なフィードバックが表示されません</span><span class="sxs-lookup"><span data-stu-id="164cd-112">Drag/Drop will not show appropriate feedback for touch input.</span></span> <span data-ttu-id="164cd-113">(これはスタイラス入力には影響しません)。</span><span class="sxs-lookup"><span data-stu-id="164cd-113">(This does not affect stylus input.)</span></span>

  - <span data-ttu-id="164cd-114">ドラッグ/ドロップは、タッチ/スタイラス イベントで開始できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="164cd-114">Drag/Drop can no longer be initiated on touch/stylus events.</span></span>

      <span data-ttu-id="164cd-115">そのため、マウス入力が検出されるまで、アプリケーションが応答しなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="164cd-115">This can potentially cause the application to become unresponsive until mouse input is detected.</span></span> <span data-ttu-id="164cd-116">代わりに、開発者はマウス イベントからドラッグ アンド ドロップを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="164cd-116">Instead, developers should initiate drag and drop from mouse events.</span></span>

## <a name="opting-in-to-wm_pointer-based-touchstylus-support"></a><span data-ttu-id="164cd-117">WM_POINTER ベースのタッチ/スタイラス サポートの有効化</span><span class="sxs-lookup"><span data-stu-id="164cd-117">Opting in to WM_POINTER-based touch/stylus support</span></span>

<span data-ttu-id="164cd-118">このスタックを有効にする開発者は、アプリケーションの *app.config* ファイルに以下を追加できます。</span><span class="sxs-lookup"><span data-stu-id="164cd-118">Developers who wish to enable this stack can add the following to their application's *app.config* file.</span></span>

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

<span data-ttu-id="164cd-119">このエントリを削除するか、その値を `false` に設定すると、このオプションのスタックがオフになります。</span><span class="sxs-lookup"><span data-stu-id="164cd-119">Removing this entry or setting its value to `false` turns this optional stack off.</span></span>

## <a name="see-also"></a><span data-ttu-id="164cd-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="164cd-120">See also</span></span>

- [<span data-ttu-id="164cd-121">アプリケーションの互換性</span><span class="sxs-lookup"><span data-stu-id="164cd-121">Application compatibility</span></span>](application-compatibility.md)
