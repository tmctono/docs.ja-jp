---
title: FontDialog コンポーネントの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
ms.openlocfilehash: 7f140807bf4b42e530302190042e729c59248e7f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789312"
---
# <a name="fontdialog-component-overview-windows-forms"></a><span data-ttu-id="d91ba-102">FontDialog コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="d91ba-102">FontDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="d91ba-103">Windows フォーム<xref:System.Windows.Forms.FontDialog>コンポーネントは構成済みのダイアログ ボックス、標準の Windows である**フォント** ダイアログ ボックスが、システムに現在インストールされているフォントを公開するために使用します。</span><span class="sxs-lookup"><span data-stu-id="d91ba-103">The Windows Forms <xref:System.Windows.Forms.FontDialog> component is a pre-configured dialog box, which is the standard Windows **Font** dialog box used to expose the fonts that are currently installed on the system.</span></span> <span data-ttu-id="d91ba-104">フォントの選択ダイアログ ボックスを構成する代わりに、シンプルなソリューションとして、Windows ベースのアプリケーション内で使用します。</span><span class="sxs-lookup"><span data-stu-id="d91ba-104">Use it within your Windows-based application as a simple solution for font selection in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="d91ba-105">既定では、ダイアログ ボックスに表示リスト ボックスのフォント、フォント スタイル、およびサイズです。取り消し線、下線; などの効果のチェック ボックススクリプトのドロップダウン リストフォントの表示方法のサンプルです。</span><span class="sxs-lookup"><span data-stu-id="d91ba-105">By default, the dialog box shows list boxes for Font, Font style, and Size; check boxes for effects like Strikeout and Underline; a drop-down list for Script; and a sample of how the font will appear.</span></span> <span data-ttu-id="d91ba-106">(スクリプトは、特定のフォントの使用可能な別の文字のスクリプトなど、ヘブライ語や日本語)。フォント ダイアログ ボックスを表示するには<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="d91ba-106">(Script refers to different character scripts that are available for a given font, for example, Hebrew or Japanese.) To display the font dialog box, call the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="d91ba-107">キー プロパティ</span><span class="sxs-lookup"><span data-stu-id="d91ba-107">Key Properties</span></span>  
 <span data-ttu-id="d91ba-108">コンポーネントには、さまざまな外観を構成するプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="d91ba-108">The component has a number of properties that configure its appearance.</span></span> <span data-ttu-id="d91ba-109">ダイアログ ボックスの選択項目を設定するプロパティは<xref:System.Windows.Forms.FontDialog.Font%2A>と<xref:System.Windows.Forms.FontDialog.Color%2A>します。</span><span class="sxs-lookup"><span data-stu-id="d91ba-109">The properties that set the dialog-box selections are <xref:System.Windows.Forms.FontDialog.Font%2A> and <xref:System.Windows.Forms.FontDialog.Color%2A>.</span></span> <span data-ttu-id="d91ba-110"><xref:System.Windows.Forms.FontDialog.Font%2A>プロパティは、フォント、スタイル、サイズ、スクリプト、および効果を設定します。 たとえば、`Arial, 10pt, style=Italic, Strikeout`します。</span><span class="sxs-lookup"><span data-stu-id="d91ba-110">The <xref:System.Windows.Forms.FontDialog.Font%2A> property sets the font, style, size, script, and effects; for example, `Arial, 10pt, style=Italic, Strikeout`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d91ba-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="d91ba-111">See also</span></span>

- <xref:System.Windows.Forms.FontDialog>
- [<span data-ttu-id="d91ba-112">FontDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d91ba-112">FontDialog Component</span></span>](fontdialog-component-windows-forms.md)
