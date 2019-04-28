---
title: -removeintchecks
ms.date: 03/13/2018
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
ms.openlocfilehash: c086a031d5cef4563a6769e7683dcb1110b8fe49
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788766"
---
# <a name="-removeintchecks"></a><span data-ttu-id="55672-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="55672-102">-removeintchecks</span></span>
<span data-ttu-id="55672-103">オーバーフロー エラーのオンまたはオフ、整数演算のチェックをオンにします。</span><span class="sxs-lookup"><span data-stu-id="55672-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55672-104">構文</span><span class="sxs-lookup"><span data-stu-id="55672-104">Syntax</span></span>  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="55672-105">引数</span><span class="sxs-lookup"><span data-stu-id="55672-105">Arguments</span></span>  
  
|<span data-ttu-id="55672-106">用語</span><span class="sxs-lookup"><span data-stu-id="55672-106">Term</span></span>|<span data-ttu-id="55672-107">定義</span><span class="sxs-lookup"><span data-stu-id="55672-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="55672-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="55672-108">`+` &#124; `-`</span></span>|<span data-ttu-id="55672-109">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="55672-109">Optional.</span></span> <span data-ttu-id="55672-110">`-removeintchecks-`オプションは、すべての整数の計算でオーバーフロー エラーをチェックするコンパイラ。</span><span class="sxs-lookup"><span data-stu-id="55672-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="55672-111">既定値は `-removeintchecks-` です。</span><span class="sxs-lookup"><span data-stu-id="55672-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="55672-112">指定する`-removeintchecks`または`-removeintchecks+`エラー チェックを防止しより高速の整数の計算を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="55672-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="55672-113">ただし、エラー チェックを行わないと、エラーを発生させず不適切な結果を格納できるデータ型の容量がオーバーフローした場合。</span><span class="sxs-lookup"><span data-stu-id="55672-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="55672-114">Visual Studio 統合開発環境で-removeintchecks を設定するには</span><span class="sxs-lookup"><span data-stu-id="55672-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="55672-115">1.**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="55672-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="55672-116">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55672-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="55672-117">2.**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="55672-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="55672-118">3.**[詳細設定]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="55672-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="55672-119">4.値を変更、**整数オーバーフローのチェックを解除**ボックス。</span><span class="sxs-lookup"><span data-stu-id="55672-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="55672-120">例</span><span class="sxs-lookup"><span data-stu-id="55672-120">Example</span></span>  
 <span data-ttu-id="55672-121">次のコードのコンパイル`Test.vb`し整数オーバーフロー エラー チェックをオフにします。</span><span class="sxs-lookup"><span data-stu-id="55672-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="55672-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="55672-122">See also</span></span>

- [<span data-ttu-id="55672-123">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="55672-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="55672-124">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="55672-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
