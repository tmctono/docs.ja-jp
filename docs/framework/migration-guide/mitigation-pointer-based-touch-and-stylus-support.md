---
title: 軽減策:ポインター ベースのタッチおよびスタイラスのサポート
ms.date: 04/07/2017
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- WPF pointer-based touch and stylus stack
ms.assetid: f99126b5-c396-48f9-8233-8f36b4c9e717
ms.openlocfilehash: 6b3e8068be2f5ed82c483b760fe100ea0a751588
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457863"
---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a><span data-ttu-id="d0f44-102">軽減策:ポインター ベースのタッチおよびスタイラスのサポート</span><span class="sxs-lookup"><span data-stu-id="d0f44-102">Mitigation: Pointer-based Touch and Stylus Support</span></span>

<span data-ttu-id="d0f44-103">.NET Framework 4.7 を対象とし、Windows 10 Creators Update 以降の Windows システムで実行されている WPF アプリケーションは、オプションの `WM_POINTER` ベースの WPF タッチ/スタイラス スタックを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d0f44-103">WPF applications that target the .NET Framework 4.7 and are running on Windows Systems starting with Windows 10 Creators Update can enable an optional `WM_POINTER`-based WPF touch/stylus stack.</span></span>

## <a name="impact"></a><span data-ttu-id="d0f44-104">影響</span><span class="sxs-lookup"><span data-stu-id="d0f44-104">Impact</span></span>

<span data-ttu-id="d0f44-105">ポインター ベースのタッチ/スタイラス サポートを明示的に有効にしていない開発者は、WPF タッチ/スタイラス動作の変更を確認できません。</span><span class="sxs-lookup"><span data-stu-id="d0f44-105">Developers who do not explicitly enable pointer-based touch/stylus support should see no change in WPF touch/stylus behavior.</span></span>

<span data-ttu-id="d0f44-106">オプションの `WM_POINTER` ベースのタッチ/スタイラス スタックに関する現在の既知の問題を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="d0f44-106">The following are current known issues with the optional `WM_POINTER`-based touch/stylus stack:</span></span>

- <span data-ttu-id="d0f44-107">リアルタイム インクがサポートされない。</span><span class="sxs-lookup"><span data-stu-id="d0f44-107">No support for real-time inking.</span></span>

   <span data-ttu-id="d0f44-108">インクとスタイラス プラグインがまだ機能している間は、UI スレッドで処理されますが、パフォーマンスの低下につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d0f44-108">While inking and stylus plugins still work, they are processed on the UI thread, which can lead to poor performance.</span></span>

- <span data-ttu-id="d0f44-109">プロモーションの変更により、タッチ/スタイラス イベントからマウス イベントに動作が変更される。</span><span class="sxs-lookup"><span data-stu-id="d0f44-109">Behavioral changes due to changes in promotion from touch/stylus events to mouse events.</span></span>

  - <span data-ttu-id="d0f44-110">操作の動作が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d0f44-110">Manipulation may behave differently.</span></span>

  - <span data-ttu-id="d0f44-111">ドラッグ/ドロップでは、タッチ入力の適切なフィードバックが表示されません</span><span class="sxs-lookup"><span data-stu-id="d0f44-111">Drag/Drop will not show appropriate feedback for touch input.</span></span> <span data-ttu-id="d0f44-112">(これはスタイラス入力には影響しません)。</span><span class="sxs-lookup"><span data-stu-id="d0f44-112">(This does not affect stylus input.)</span></span>

  - <span data-ttu-id="d0f44-113">ドラッグ/ドロップは、タッチ/スタイラス イベントで開始できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d0f44-113">Drag/Drop can no longer be initiated on touch/stylus events.</span></span>

      <span data-ttu-id="d0f44-114">そのため、マウス入力が検出されるまで、アプリケーションが応答しなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d0f44-114">This can potentially cause the application to become unresponsive until mouse input is detected.</span></span> <span data-ttu-id="d0f44-115">代わりに、開発者はマウス イベントからドラッグ アンド ドロップを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0f44-115">Instead, developers should initiate drag and drop from mouse events.</span></span>

## <a name="opting-in-to-wm_pointer-based-touchstylus-support"></a><span data-ttu-id="d0f44-116">WM_POINTER ベースのタッチ/スタイラス サポートの有効化</span><span class="sxs-lookup"><span data-stu-id="d0f44-116">Opting in to WM_POINTER-based touch/stylus support</span></span>

<span data-ttu-id="d0f44-117">このスタックを有効にする開発者は、アプリケーションの app.config ファイルに次の行を追加できます。</span><span class="sxs-lookup"><span data-stu-id="d0f44-117">Developers who wish to enable this stack can add the following to their application's app.config file:</span></span>

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

<span data-ttu-id="d0f44-118">このエントリを削除するか、その値を `false` に設定すると、このオプションのスタックがオフになります。</span><span class="sxs-lookup"><span data-stu-id="d0f44-118">Removing this entry or setting its value to `false` turns this optional stack off.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0f44-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0f44-119">See also</span></span>

- [<span data-ttu-id="d0f44-120">アプリケーションの互換性</span><span class="sxs-lookup"><span data-stu-id="d0f44-120">Application compatibility</span></span>](application-compatibility.md)
