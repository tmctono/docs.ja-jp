---
title: エンコード方式および Windows フォームのグローバリゼーション
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], lack of Unicode support
- DateTimePicker control [Windows Forms], lack of Unicode support
- TrackBar control [Windows Forms], lack of Unicode support
- ImageList component [Windows Forms], lack of Unicode support
- Unicode [Windows Forms]
- ToolBar control [Windows Forms], lack of Unicode support
- international applications [Windows Forms], character display
- StatusBar control [Windows Forms], lack of Unicode support
- MonthCalendar control [Windows Forms], lack of Unicode support
- international characters
- TabControl control [Windows Forms], lack of Unicode support
- Windows Forms, encoding
- TreeView control [Windows Forms], lack of Unicode support
- ProgressBar control [Windows Forms], Unicode-enabled forms
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: 22e8965d-a712-42b3-8167-3ee346bd70f9
ms.openlocfilehash: 60ca9f7ba2f716b5dab1b0276bc3cd07ddd8f65c
ms.sourcegitcommit: 878ca7550b653114c3968ef8906da2b3e60e3c7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736884"
---
# <a name="encoding-and-windows-forms-globalization"></a><span data-ttu-id="c4d18-102">エンコード方式および Windows フォームのグローバリゼーション</span><span class="sxs-lookup"><span data-stu-id="c4d18-102">Encoding and Windows Forms Globalization</span></span>

<span data-ttu-id="c4d18-103">Windows フォーム アプリケーションは、Unicode に完全対応しているため、プラットフォーム、プログラム、または言語に関係なく、文字がそれぞれ一意の数字で表されます。</span><span class="sxs-lookup"><span data-stu-id="c4d18-103">Windows Forms applications are entirely Unicode-enabled, meaning that each character is represented by a unique number, no matter what the platform, program, or language.</span></span> <span data-ttu-id="c4d18-104">Unicode の詳細については、 [unicode コンソーシアムの Web サイト](https://www.unicode.org)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4d18-104">For more information about Unicode, see the [Unicode consortium Web site](https://www.unicode.org).</span></span>

## <a name="benefits-of-unicode"></a><span data-ttu-id="c4d18-105">Unicode の利点</span><span class="sxs-lookup"><span data-stu-id="c4d18-105">Benefits of Unicode</span></span>

<span data-ttu-id="c4d18-106">Unicode 対応フォームの利点として、ヒンディー語などの Unicode 専用のスクリプトを操作できる点も含まれます。</span><span class="sxs-lookup"><span data-stu-id="c4d18-106">The benefits of Unicode-enabled forms include the ability to work with scripts that are Unicode-only, such as Hindi.</span></span> <span data-ttu-id="c4d18-107">さらに、1 つのフォームで複数の言語を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4d18-107">In addition, you can use multiple languages on a single form.</span></span> <span data-ttu-id="c4d18-108">Unicode では、すべての文字が 2 バイト長なので、2 バイト文字を表すために特別な作業は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c4d18-108">In Unicode, all characters are two bytes long, so no special effort is needed to represent double-byte characters.</span></span> <span data-ttu-id="c4d18-109">また、すべてのプラットフォームで動作する 1 つのコードのセットを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="c4d18-109">You can also write a single set of code that will work on all platforms.</span></span> <span data-ttu-id="c4d18-110">これは Visual Basic の以前のバージョンから変更されたものであり、Windows NT や Windows 98 などのプラットフォームごとに異なるコードを記述する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="c4d18-110">This is a change from previous versions of Visual Basic, in which you had to write different code for different platforms, such as Windows NT and Windows 98.</span></span>

<span data-ttu-id="c4d18-111">ただし、Windows 98 および Windows Millennium Edition では Unicode はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c4d18-111">However, certain controls do not support Unicode in Windows 98 and Windows Millennium Edition.</span></span> <span data-ttu-id="c4d18-112">これらのコントロールはすべて、コモンコントロールから継承され、ANSI として Windows コードページを使用してデータを処理します。</span><span class="sxs-lookup"><span data-stu-id="c4d18-112">These controls, all of which inherit from the common control, will process data with the Windows code pages, as ANSI.</span></span> <span data-ttu-id="c4d18-113">これらのコントロールは、<xref:System.Windows.Forms.TabControl>、<xref:System.Windows.Forms.ListView>、<xref:System.Windows.Forms.TreeView>、<xref:System.Windows.Forms.DateTimePicker>、<xref:System.Windows.Forms.MonthCalendar>、<xref:System.Windows.Forms.TrackBar>、<xref:System.Windows.Forms.ProgressBar>、<xref:System.Windows.Forms.ImageList>、<xref:System.Windows.Forms.ToolBar>、および <xref:System.Windows.Forms.StatusBar> です。</span><span class="sxs-lookup"><span data-stu-id="c4d18-113">These controls are: <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.DateTimePicker>, <xref:System.Windows.Forms.MonthCalendar>, <xref:System.Windows.Forms.TrackBar>, <xref:System.Windows.Forms.ProgressBar>, <xref:System.Windows.Forms.ImageList>, <xref:System.Windows.Forms.ToolBar>, and <xref:System.Windows.Forms.StatusBar>.</span></span> <span data-ttu-id="c4d18-114">その結果、前述のプラットフォーム上のこれらのコントロールで Unicode データを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="c4d18-114">As a result, you cannot display Unicode data in these controls on the listed platforms.</span></span> <span data-ttu-id="c4d18-115">たとえば、日本語の文字を英語版の Windows 98 オペレーティングシステムに表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="c4d18-115">For example, you cannot display Japanese characters on an English Windows 98 operating system.</span></span>

<span data-ttu-id="c4d18-116"><xref:System.Windows.Forms.ToolBar> コントロールと <xref:System.Windows.Forms.StatusBar> コントロールの Unicode 対応の代替手段として、これらの古いコントロールを置換する <xref:System.Windows.Forms.ToolStrip> コントロールと <xref:System.Windows.Forms.StatusStrip> コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="c4d18-116">For Unicode-aware alternatives to the <xref:System.Windows.Forms.ToolBar> and <xref:System.Windows.Forms.StatusBar> controls, use the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.StatusStrip> controls, which replace these older controls.</span></span> <span data-ttu-id="c4d18-117">アプリケーションの視覚要素の間で同様のルック アンド フィールを維持するには、メニューの表示に <xref:System.Windows.Forms.MainMenu> の代わりに <xref:System.Windows.Forms.MenuStrip> コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="c4d18-117">To maintain a similar look and feel between visual elements in your application, use the <xref:System.Windows.Forms.MenuStrip> control for rendering menus instead of <xref:System.Windows.Forms.MainMenu>.</span></span> <span data-ttu-id="c4d18-118"><xref:System.Windows.Forms.ToolStrip> と <xref:System.Windows.Forms.StatusStrip> のように、<xref:System.Windows.Forms.MenuStrip> も Unicode 文字を処理して表示することができます。</span><span class="sxs-lookup"><span data-stu-id="c4d18-118">Like <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.StatusStrip>, <xref:System.Windows.Forms.MenuStrip> can also process and display Unicode characters.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4d18-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4d18-119">See also</span></span>

- [<span data-ttu-id="c4d18-120">Windows フォームアプリケーションのグローバル化</span><span class="sxs-lookup"><span data-stu-id="c4d18-120">Globalizing Windows Forms applications</span></span>](globalizing-windows-forms.md)
