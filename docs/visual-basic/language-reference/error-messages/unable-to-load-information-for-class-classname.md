---
title: クラス '<classname>' の情報を読み込めません。
ms.date: 07/20/2015
f1_keywords:
- vbc30712
- bc30712
helpviewer_keywords:
- BC30712
ms.assetid: c7ffbd6d-05c6-4261-b44b-1bcd521bb350
ms.openlocfilehash: 42f31df7f4bc849374d8beb09e17394c3cdd5ec4
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318202"
---
# <a name="unable-to-load-information-for-class-classname"></a><span data-ttu-id="b1dac-102">クラスの情報を読み込めません\<classname >'</span><span class="sxs-lookup"><span data-stu-id="b1dac-102">Unable to load information for class '\<classname>'</span></span>
<span data-ttu-id="b1dac-103">無効なクラスに参照が行われました。</span><span class="sxs-lookup"><span data-stu-id="b1dac-103">A reference was made to a class that is not available.</span></span>  
  
 <span data-ttu-id="b1dac-104">**エラー ID:** BC30712</span><span class="sxs-lookup"><span data-stu-id="b1dac-104">**Error ID:** BC30712</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b1dac-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="b1dac-105">To correct this error</span></span>  
  
1. <span data-ttu-id="b1dac-106">クラスが定義されていると、名前のスペルが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b1dac-106">Verify that the class is defined and that you spelled the name correctly.</span></span>  
  
2. <span data-ttu-id="b1dac-107">モジュールで宣言されたいずれかのメンバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b1dac-107">Try accessing one of the members declared in the module.</span></span> <span data-ttu-id="b1dac-108">宣言されているモジュールがまだ読み込まれていないために、デバッグ環境ではメンバーを特定できないという場合もあります。</span><span class="sxs-lookup"><span data-stu-id="b1dac-108">In some cases, the debugging environment cannot locate members because the modules where they are declared have not been loaded yet.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1dac-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1dac-109">See also</span></span>

- [<span data-ttu-id="b1dac-110">Visual Studio でのデバッグ</span><span class="sxs-lookup"><span data-stu-id="b1dac-110">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
