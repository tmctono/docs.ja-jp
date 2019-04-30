---
title: '方法: ページからウィンドウのタイトルを設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: 55444de6c61107979307b94910ba944e7001cf9e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054004"
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a><span data-ttu-id="0387d-102">方法: ページからウィンドウのタイトルを設定する</span><span class="sxs-lookup"><span data-stu-id="0387d-102">How to: Set the Title of a Window from a Page</span></span>
<span data-ttu-id="0387d-103">この例は、ウィンドウのタイトルを設定する方法を示しています、<xref:System.Windows.Controls.Page>がホストされています。</span><span class="sxs-lookup"><span data-stu-id="0387d-103">This example shows how to set the title of the window in which a <xref:System.Windows.Controls.Page> is hosted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0387d-104">例</span><span class="sxs-lookup"><span data-stu-id="0387d-104">Example</span></span>  
 <span data-ttu-id="0387d-105">ページを設定してそれをホストしているウィンドウのタイトルを変更することができます、<xref:System.Windows.Controls.Page.WindowTitle%2A>プロパティ、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="0387d-105">A page can change the title of the window that is hosting it by setting the <xref:System.Windows.Controls.Page.WindowTitle%2A> property, like so:</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
>  <span data-ttu-id="0387d-106">設定、<xref:System.Windows.Controls.Page.Title%2A>ページのプロパティには、ウィンドウのタイトルの値は変わりません。</span><span class="sxs-lookup"><span data-stu-id="0387d-106">Setting the <xref:System.Windows.Controls.Page.Title%2A> property of a page does not change the value of the window title.</span></span> <span data-ttu-id="0387d-107">代わりに、<xref:System.Windows.Controls.Page.Title%2A>ナビゲーション履歴にページ エントリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0387d-107">Instead, <xref:System.Windows.Controls.Page.Title%2A> specifies the name of a page entry in navigation history.</span></span>
