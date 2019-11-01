---
title: オートメーション エラーです。
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: 25c3b71eb818223c58ab17d9be885033a5d4ded0
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197035"
---
# <a name="automation-error"></a><span data-ttu-id="00e6a-102">オートメーション エラーです。</span><span class="sxs-lookup"><span data-stu-id="00e6a-102">Automation error</span></span>
<span data-ttu-id="00e6a-103">メソッドの実行中、またはオブジェクト変数のプロパティの取得中または設定中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="00e6a-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="00e6a-104">エラーは、オブジェクトを作成したアプリケーションによって報告されました。</span><span class="sxs-lookup"><span data-stu-id="00e6a-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="00e6a-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="00e6a-105">To correct this error</span></span>  
  
1. <span data-ttu-id="00e6a-106">`Err` オブジェクトのプロパティをチェックし、エラーの原因と性質を確認します。</span><span class="sxs-lookup"><span data-stu-id="00e6a-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2. <span data-ttu-id="00e6a-107">アクセス ステートメントの直前で `On Error Resume Next` ステートメントを使用し、アクセス ステートメントの直後のエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="00e6a-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00e6a-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="00e6a-108">See also</span></span>

- [<span data-ttu-id="00e6a-109">エラーの種類</span><span class="sxs-lookup"><span data-stu-id="00e6a-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="00e6a-110">ご意見</span><span class="sxs-lookup"><span data-stu-id="00e6a-110">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
