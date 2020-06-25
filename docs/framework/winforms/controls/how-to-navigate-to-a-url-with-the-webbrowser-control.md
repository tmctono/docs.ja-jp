---
title: '方法: WebBrowser コントロールで URL に移動する'
description: Windows フォーム WebBrowser コントロールを使用して特定の URL に移動する方法について説明します。 また、新しいドキュメントが読み込まれるタイミングを確認する方法についても説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.Navigate
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- URLs [Windows Forms], navigating to
- WebBrowser control [Windows Forms], navigating to URLs
- examples [Windows Forms], WebBrowser control
ms.assetid: b3ec38cb-f509-4d0b-bd79-9f3611259c62
ms.openlocfilehash: e6ad360cc73a84ca040869832bb59d354cb78bd5
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325567"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a><span data-ttu-id="6b2f0-104">方法: WebBrowser コントロールで URL に移動する</span><span class="sxs-lookup"><span data-stu-id="6b2f0-104">How to: Navigate to a URL with the WebBrowser Control</span></span>
<span data-ttu-id="6b2f0-105">コントロールを特定の URL に移動する方法を次のコード例に示し <xref:System.Windows.Forms.WebBrowser> ます。</span><span class="sxs-lookup"><span data-stu-id="6b2f0-105">The following code example demonstrates how to navigate the <xref:System.Windows.Forms.WebBrowser> control to a specific URL.</span></span>

 <span data-ttu-id="6b2f0-106">新しいドキュメントが完全に読み込まれたことを確認するには、イベントを処理し <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> ます。</span><span class="sxs-lookup"><span data-stu-id="6b2f0-106">To determine when the new document is fully loaded, handle the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="6b2f0-107">このイベントのデモンストレーションについては、「[方法: WebBrowser コントロールで印刷](how-to-print-with-a-webbrowser-control.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b2f0-107">For a demonstration of this event, see [How to: Print with a WebBrowser Control](how-to-print-with-a-webbrowser-control.md).</span></span>

## <a name="example"></a><span data-ttu-id="6b2f0-108">例</span><span class="sxs-lookup"><span data-stu-id="6b2f0-108">Example</span></span>

```vb
Me.webBrowser1.Navigate("https://www.microsoft.com")
```

```csharp
this.webBrowser1.Navigate("https://www.microsoft.com");
```

## <a name="compiling-the-code"></a><span data-ttu-id="6b2f0-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="6b2f0-109">Compiling the Code</span></span>
 <span data-ttu-id="6b2f0-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b2f0-110">This example requires:</span></span>

- <span data-ttu-id="6b2f0-111">`webBrowser1` という名前の <xref:System.Windows.Forms.WebBrowser> コントロール。</span><span class="sxs-lookup"><span data-stu-id="6b2f0-111">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>

- <span data-ttu-id="6b2f0-112">`System` アセンブリおよび `System.Windows.Forms` アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="6b2f0-112">References to the `System` and `System.Windows.Forms` assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b2f0-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b2f0-113">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [<span data-ttu-id="6b2f0-114">WebBrowser コントロール</span><span class="sxs-lookup"><span data-stu-id="6b2f0-114">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
- [<span data-ttu-id="6b2f0-115">方法: WebBrowser コントロールを使用して印刷する</span><span class="sxs-lookup"><span data-stu-id="6b2f0-115">How to: Print with a WebBrowser Control</span></span>](how-to-print-with-a-webbrowser-control.md)
