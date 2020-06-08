---
title: スタートアップ フォームが指定されていません。
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: 058deb1378ed9218274ae20c8340178f7c8fa58c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409908"
---
# <a name="a-startup-form-has-not-been-specified"></a><span data-ttu-id="79c39-102">スタートアップ フォームが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="79c39-102">A startup form has not been specified</span></span>

<span data-ttu-id="79c39-103">アプリケーションで <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> クラスが使用されていますが、スタートアップ フォームが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="79c39-103">The application uses the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class but does not specify the startup form.</span></span>  
  
 <span data-ttu-id="79c39-104">これは、プロジェクト デザイナーで **[アプリケーション フレームワークを有効にする]** チェック ボックスがオンになっていても、 **[スタートアップ フォーム]** が指定されていない場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="79c39-104">This can occur if the **Enable application framework** check box is selected in the project designer but the **Startup form** is not specified.</span></span> <span data-ttu-id="79c39-105">詳細については、「[[アプリケーション] ページ (プロジェクト デザイナー) (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79c39-105">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="79c39-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="79c39-106">To correct this error</span></span>  
  
1. <span data-ttu-id="79c39-107">アプリケーションのスタートアップ オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="79c39-107">Specify a startup object for the application.</span></span>  
  
     <span data-ttu-id="79c39-108">詳細については、「[[アプリケーション] ページ (プロジェクト デザイナー) (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79c39-108">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
2. <span data-ttu-id="79c39-109"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> メソッドをオーバーライドして、スタートアップ フォームに <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="79c39-109">Override the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> method to set the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> property to the startup form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79c39-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="79c39-110">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>
- [<span data-ttu-id="79c39-111">Visual Basic アプリケーション モデルの概要</span><span class="sxs-lookup"><span data-stu-id="79c39-111">Overview of the Visual Basic Application Model</span></span>](../../developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
