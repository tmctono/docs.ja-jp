---
title: アプリケーション フォームへのアクセス (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- forms [Visual Basic], communicating between
- application forms [Visual Basic], accessing
- forms [Visual Basic], accessing one from another
- My.Forms object
- forms [Visual Basic], accessing all open
ms.assetid: 9aaf5aaf-2012-4f97-89c7-6e62b9d17863
ms.openlocfilehash: 85de915f4dc9a79e0161411951062afbeb764513
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821687"
---
# <a name="accessing-application-forms-visual-basic"></a><span data-ttu-id="22a38-102">アプリケーション フォームへのアクセス (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22a38-102">Accessing Application Forms (Visual Basic)</span></span>
<span data-ttu-id="22a38-103">`My.Forms` オブジェクトは、アプリケーションのプロジェクトで宣言された各 Windows フォームのインスタンスに簡単にアクセスする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="22a38-103">The `My.Forms` object provides an easy way to access an instance of each Windows Form declared in the application's project.</span></span> <span data-ttu-id="22a38-104">`My.Application` オブジェクトのプロパティを利用し、アプリケーションのスプラッシュ スクリーンとメイン フォームにアクセスし、アプリケーションのオープン フォームの一覧を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="22a38-104">You can also use properties of the `My.Application` object to access the application's splash screen and main form, and get a list of the application's open forms.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="22a38-105">[タスク]</span><span class="sxs-lookup"><span data-stu-id="22a38-105">Tasks</span></span>  
 <span data-ttu-id="22a38-106">次の表に示すのは、アプリケーションのフォームにアクセスする方法を示す例です。</span><span class="sxs-lookup"><span data-stu-id="22a38-106">The following table lists examples showing how to access an application's forms.</span></span>  
  
|<span data-ttu-id="22a38-107">終了</span><span class="sxs-lookup"><span data-stu-id="22a38-107">To</span></span>|<span data-ttu-id="22a38-108">参照トピック</span><span class="sxs-lookup"><span data-stu-id="22a38-108">See</span></span>|  
|---|---|  
|<span data-ttu-id="22a38-109">アプリケーションのあるフォームから別のフォームにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="22a38-109">Access one form from another form in an application.</span></span>|[<span data-ttu-id="22a38-110">My.Forms オブジェクト</span><span class="sxs-lookup"><span data-stu-id="22a38-110">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)|  
|<span data-ttu-id="22a38-111">アプリケーションのすべてのオープン フォームのタイトルを表示します。</span><span class="sxs-lookup"><span data-stu-id="22a38-111">Display the titles of all the application's open forms.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>|  
|<span data-ttu-id="22a38-112">アプリケーションの起動時に状態情報でスプラッシュ スクリーンを更新します。</span><span class="sxs-lookup"><span data-stu-id="22a38-112">Update the splash screen with status information as the application starts.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="22a38-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="22a38-113">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>
- [<span data-ttu-id="22a38-114">My.Forms オブジェクト</span><span class="sxs-lookup"><span data-stu-id="22a38-114">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)
