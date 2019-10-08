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
ms.openlocfilehash: bea6ca24ea6da9000267e754d52fe0ca152f7d7f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005228"
---
# <a name="-removeintchecks"></a><span data-ttu-id="6c1eb-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="6c1eb-102">-removeintchecks</span></span>
<span data-ttu-id="6c1eb-103">整数演算のオンまたはオフのオーバーフローエラーチェックをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="6c1eb-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c1eb-104">構文</span><span class="sxs-lookup"><span data-stu-id="6c1eb-104">Syntax</span></span>  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6c1eb-105">引数</span><span class="sxs-lookup"><span data-stu-id="6c1eb-105">Arguments</span></span>  
  
|<span data-ttu-id="6c1eb-106">項目</span><span class="sxs-lookup"><span data-stu-id="6c1eb-106">Term</span></span>|<span data-ttu-id="6c1eb-107">定義</span><span class="sxs-lookup"><span data-stu-id="6c1eb-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="6c1eb-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="6c1eb-108">`+` &#124; `-`</span></span>|<span data-ttu-id="6c1eb-109">任意。</span><span class="sxs-lookup"><span data-stu-id="6c1eb-109">Optional.</span></span> <span data-ttu-id="6c1eb-110">@No__t-0 オプションを指定すると、コンパイラはすべての整数計算でオーバーフローエラーをチェックします。</span><span class="sxs-lookup"><span data-stu-id="6c1eb-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="6c1eb-111">既定値は `-removeintchecks-` です。</span><span class="sxs-lookup"><span data-stu-id="6c1eb-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="6c1eb-112">@No__t-0 または `-removeintchecks+` を指定すると、エラーチェックが行われず、整数計算が高速になります。</span><span class="sxs-lookup"><span data-stu-id="6c1eb-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="6c1eb-113">ただし、エラーチェックが行われず、データ型の容量がオーバーフローした場合は、エラーが発生することなく誤った結果が格納される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c1eb-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="6c1eb-114">Visual Studio 統合開発環境で-removeintchecks を設定するには</span><span class="sxs-lookup"><span data-stu-id="6c1eb-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="6c1eb-115">1. **ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="6c1eb-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="6c1eb-116">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c1eb-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="6c1eb-117">2. **[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c1eb-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="6c1eb-118">3. **[詳細設定]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c1eb-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="6c1eb-119">4。[**整数オーバーフローを削除**する] チェックボックスの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="6c1eb-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6c1eb-120">例</span><span class="sxs-lookup"><span data-stu-id="6c1eb-120">Example</span></span>  
 <span data-ttu-id="6c1eb-121">次のコードは、`Test.vb` をコンパイルし、整数オーバーフローエラーチェックをオフにします。</span><span class="sxs-lookup"><span data-stu-id="6c1eb-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c1eb-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c1eb-122">See also</span></span>

- [<span data-ttu-id="6c1eb-123">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="6c1eb-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="6c1eb-124">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="6c1eb-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
