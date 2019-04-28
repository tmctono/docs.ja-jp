---
title: 単一インスタンスのスタートアップに必要なオペレーティング システムのリソースが取得できないため、予期しないエラーが発生しました。
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_CantGetMemoryMappedFile
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
ms.openlocfilehash: 9aa7ba0babe0a89942e320a76e07c05162b31700
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61751619"
---
# <a name="an-unexpected-error-has-occurred-because-an-operating-system-resource-required-for-single-instance-startup-cannot-be-acquired"></a><span data-ttu-id="16a88-102">単一インスタンスのスタートアップに必要なオペレーティング システムのリソースが取得できないため、予期しないエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="16a88-102">An unexpected error has occurred because an operating system resource required for single instance startup cannot be acquired</span></span>
<span data-ttu-id="16a88-103">アプリケーションは、必要なオペレーティング システムのリソースを取得できませんでした。</span><span class="sxs-lookup"><span data-stu-id="16a88-103">The application could not acquire a necessary operating system resource.</span></span> <span data-ttu-id="16a88-104">この問題の考えられる原因の一部は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="16a88-104">Some of the possible causes for this problem are:</span></span>  
  
- <span data-ttu-id="16a88-105">指定されたオペレーティング システム オブジェクトを作成するためのアクセス許可がアプリケーションにない。</span><span class="sxs-lookup"><span data-stu-id="16a88-105">The application does not have permissions to create named operating-system objects.</span></span>  
  
- <span data-ttu-id="16a88-106">メモリ マップト ファイルを作成するためのアクセス許可が共通言語ランタイムにない。</span><span class="sxs-lookup"><span data-stu-id="16a88-106">The common language runtime does not have permissions to create memory-mapped files.</span></span>  
  
- <span data-ttu-id="16a88-107">アプリケーションからオペレーティング システム オブジェクトにアクセスする必要があるが、別のプロセスがそれを使用している。</span><span class="sxs-lookup"><span data-stu-id="16a88-107">The application needs to access an operating-system object, but another process is using it.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="16a88-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="16a88-108">To correct this error</span></span>  
  
1. <span data-ttu-id="16a88-109">指定されたオペレーティング システム オブジェクトを作成するための十分なアクセス許可がアプリケーションにあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="16a88-109">Check that the application has sufficient permissions to create named operating-system objects.</span></span>  
  
2. <span data-ttu-id="16a88-110">メモリ マップト ファイルを作成するための十分なアクセス許可が共通言語ランタイムにあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="16a88-110">Check that the common language runtime has sufficient permissions to create memory-mapped files.</span></span>  
  
3. <span data-ttu-id="16a88-111">コンピューターを再起動して、元のインスタンス アプリケーションへの接続に必要なリソースを使用している可能性のあるプロセスをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="16a88-111">Restart the computer to clear any process that may be using the resource needed to connect to the original instance application.</span></span>  
  
4. <span data-ttu-id="16a88-112">エラーが発生した状況を記録して、マイクロソフト プロダクト サポート サービスにご連絡ください。</span><span class="sxs-lookup"><span data-stu-id="16a88-112">Note the circumstances under which the error occurred, and call Microsoft Product Support Services</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16a88-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="16a88-113">See also</span></span>

- <span data-ttu-id="16a88-114">[[アプリケーション] ページ (プロジェクト デザイナー)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="16a88-114">[Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)</span></span>
- [<span data-ttu-id="16a88-115">デバッガーの基本事項</span><span class="sxs-lookup"><span data-stu-id="16a88-115">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)
- [<span data-ttu-id="16a88-116">ご意見</span><span class="sxs-lookup"><span data-stu-id="16a88-116">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
