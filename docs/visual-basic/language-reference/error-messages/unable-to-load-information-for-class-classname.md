---
title: クラス '<classname>' の情報を読み込めません。
ms.date: 07/20/2015
f1_keywords:
- vbc30712
- bc30712
helpviewer_keywords:
- BC30712
ms.assetid: c7ffbd6d-05c6-4261-b44b-1bcd521bb350
ms.openlocfilehash: 049db16875b14bc095e293d2a923917a9ec1d99b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814459"
---
# <a name="unable-to-load-information-for-class-classname"></a><span data-ttu-id="61354-102">クラスの情報を読み込めません\<classname >'</span><span class="sxs-lookup"><span data-stu-id="61354-102">Unable to load information for class '\<classname>'</span></span>
<span data-ttu-id="61354-103">無効なクラスに参照が行われました。</span><span class="sxs-lookup"><span data-stu-id="61354-103">A reference was made to a class that is not available.</span></span>  
  
 <span data-ttu-id="61354-104">**エラー ID:** BC30712</span><span class="sxs-lookup"><span data-stu-id="61354-104">**Error ID:** BC30712</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="61354-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="61354-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="61354-106">クラスが定義されていると、名前のスペルが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="61354-106">Verify that the class is defined and that you spelled the name correctly.</span></span>  
  
2.  <span data-ttu-id="61354-107">モジュールで宣言されたいずれかのメンバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="61354-107">Try accessing one of the members declared in the module.</span></span> <span data-ttu-id="61354-108">宣言されているモジュールがまだ読み込まれていないために、デバッグ環境ではメンバーを特定できないという場合もあります。</span><span class="sxs-lookup"><span data-stu-id="61354-108">In some cases, the debugging environment cannot locate members because the modules where they are declared have not been loaded yet.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61354-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="61354-109">See also</span></span>

- [<span data-ttu-id="61354-110">Visual Studio でのデバッグ</span><span class="sxs-lookup"><span data-stu-id="61354-110">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
