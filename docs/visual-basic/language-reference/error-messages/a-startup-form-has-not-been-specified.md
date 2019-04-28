---
title: スタートアップ フォームが指定されていません。
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: 2bbae640ca65c95411cae24a9506fe2076b62cba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61751645"
---
# <a name="a-startup-form-has-not-been-specified"></a><span data-ttu-id="db107-102">スタートアップ フォームが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="db107-102">A startup form has not been specified</span></span>
<span data-ttu-id="db107-103">アプリケーションを使用して、<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>クラスが、スタートアップ フォームを指定しません。</span><span class="sxs-lookup"><span data-stu-id="db107-103">The application uses the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class but does not specify the startup form.</span></span>  
  
 <span data-ttu-id="db107-104">これは、場合に発生することができます、**アプリケーション フレームワークを有効にする**プロジェクト デザイナー チェック ボックスが選択されているが、**スタートアップ フォーム**が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="db107-104">This can occur if the **Enable application framework** check box is selected in the project designer but the **Startup form** is not specified.</span></span> <span data-ttu-id="db107-105">詳細については、「[[アプリケーション] ページ (プロジェクト デザイナー) (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db107-105">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="db107-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="db107-106">To correct this error</span></span>  
  
1. <span data-ttu-id="db107-107">アプリケーションのスタートアップ オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="db107-107">Specify a startup object for the application.</span></span>  
  
     <span data-ttu-id="db107-108">詳細については、「[[アプリケーション] ページ (プロジェクト デザイナー) (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db107-108">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
2. <span data-ttu-id="db107-109">上書き、<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>を設定するメソッド、<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>スタートアップ フォームのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="db107-109">Override the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> method to set the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> property to the startup form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db107-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="db107-110">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>
- [<span data-ttu-id="db107-111">Visual Basic アプリケーション モデルの概要</span><span class="sxs-lookup"><span data-stu-id="db107-111">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
