---
title: アプリケーション フォームへのアクセス
ms.date: 07/20/2015
helpviewer_keywords:
- forms [Visual Basic], communicating between
- application forms [Visual Basic], accessing
- forms [Visual Basic], accessing one from another
- My.Forms object
- forms [Visual Basic], accessing all open
ms.assetid: 9aaf5aaf-2012-4f97-89c7-6e62b9d17863
ms.openlocfilehash: 332b6a7563160528b6c17210170af0db6e9bc0e7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "74349239"
---
# <a name="accessing-application-forms-visual-basic"></a><span data-ttu-id="31c73-102">アプリケーション フォームへのアクセス (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31c73-102">Accessing Application Forms (Visual Basic)</span></span>

<span data-ttu-id="31c73-103">`My.Forms` オブジェクトは、アプリケーションのプロジェクトで宣言された各 Windows フォームのインスタンスに簡単にアクセスする方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="31c73-103">The `My.Forms` object provides an easy way to access an instance of each Windows Form declared in the application's project.</span></span> <span data-ttu-id="31c73-104">`My.Application` オブジェクトのプロパティを利用し、アプリケーションのスプラッシュ スクリーンとメイン フォームにアクセスし、アプリケーションのオープン フォームの一覧を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="31c73-104">You can also use properties of the `My.Application` object to access the application's splash screen and main form, and get a list of the application's open forms.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="31c73-105">処理手順</span><span class="sxs-lookup"><span data-stu-id="31c73-105">Tasks</span></span>  

 <span data-ttu-id="31c73-106">次の表に示すのは、アプリケーションのフォームにアクセスする方法を示す例です。</span><span class="sxs-lookup"><span data-stu-id="31c73-106">The following table lists examples showing how to access an application's forms.</span></span>  
  
|<span data-ttu-id="31c73-107">ターゲット</span><span class="sxs-lookup"><span data-stu-id="31c73-107">To</span></span>|<span data-ttu-id="31c73-108">参照先</span><span class="sxs-lookup"><span data-stu-id="31c73-108">See</span></span>|  
|---|---|  
|<span data-ttu-id="31c73-109">アプリケーションのあるフォームから別のフォームにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="31c73-109">Access one form from another form in an application.</span></span>|[<span data-ttu-id="31c73-110">My.Forms オブジェクト</span><span class="sxs-lookup"><span data-stu-id="31c73-110">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)|  
|<span data-ttu-id="31c73-111">アプリケーションのすべてのオープン フォームのタイトルを表示します。</span><span class="sxs-lookup"><span data-stu-id="31c73-111">Display the titles of all the application's open forms.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>|  
|<span data-ttu-id="31c73-112">アプリケーションの起動時に状態情報でスプラッシュ スクリーンを更新します。</span><span class="sxs-lookup"><span data-stu-id="31c73-112">Update the splash screen with status information as the application starts.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="31c73-113">参照</span><span class="sxs-lookup"><span data-stu-id="31c73-113">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>
- [<span data-ttu-id="31c73-114">My.Forms オブジェクト</span><span class="sxs-lookup"><span data-stu-id="31c73-114">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)
