---
title: マウスが存在しません
ms.date: 07/20/2015
f1_keywords:
- vbrMouse_NoMouseIsPresent
ms.assetid: 4472fd57-4217-4463-9d3c-dc4a8fe88f1b
ms.openlocfilehash: ceb850d98d29c232da304fbdfaddf5611714ef1a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078854"
---
# <a name="no-mouse-is-present"></a><span data-ttu-id="5a129-102">マウスが存在しません</span><span class="sxs-lookup"><span data-stu-id="5a129-102">No mouse is present</span></span>

<span data-ttu-id="5a129-103">`My.Computer.Mouse` オブジェクトのいずれかのプロパティが呼び出されましたが、コンピューターにマウスが接続されていないか、マウス ポートが取り付けられていません。</span><span class="sxs-lookup"><span data-stu-id="5a129-103">One of the properties of the `My.Computer.Mouse` object was called, but the computer has no mouse or mouse port installed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5a129-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="5a129-104">To correct this error</span></span>  
  
- <span data-ttu-id="5a129-105">`Try...Catch` オブジェクトのプロパティの呼び出しを、 `My.Computer.Mouse` ブロックで囲みます。</span><span class="sxs-lookup"><span data-stu-id="5a129-105">Add a `Try...Catch` block around the call to the property of the `My.Computer.Mouse` object.</span></span>  
  
     <span data-ttu-id="5a129-106">または</span><span class="sxs-lookup"><span data-stu-id="5a129-106">— or —</span></span>  
  
- <span data-ttu-id="5a129-107">マウスをコンピューターに取り付けます。</span><span class="sxs-lookup"><span data-stu-id="5a129-107">Install a mouse on the computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a129-108">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="5a129-108">See also</span></span>

- [<span data-ttu-id="5a129-109">My.Computer.Mouse</span><span class="sxs-lookup"><span data-stu-id="5a129-109">My.Computer.Mouse</span></span>](xref:Microsoft.VisualBasic.Devices.Mouse)
- [<span data-ttu-id="5a129-110">.NET での例外の処理とスロー</span><span class="sxs-lookup"><span data-stu-id="5a129-110">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="5a129-111">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="5a129-111">Try...Catch...Finally Statement</span></span>](../language-reference/statements/try-catch-finally-statement.md)
