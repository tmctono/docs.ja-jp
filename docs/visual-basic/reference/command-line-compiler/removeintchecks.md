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
ms.openlocfilehash: ec4722cb7088819dae95ca1b7cbc1469d957a7aa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400475"
---
# <a name="-removeintchecks"></a><span data-ttu-id="02ce5-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="02ce5-102">-removeintchecks</span></span>
<span data-ttu-id="02ce5-103">整数演算のオーバーフロー エラー チェックをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="02ce5-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02ce5-104">構文</span><span class="sxs-lookup"><span data-stu-id="02ce5-104">Syntax</span></span>  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="02ce5-105">引数</span><span class="sxs-lookup"><span data-stu-id="02ce5-105">Arguments</span></span>  
  
|<span data-ttu-id="02ce5-106">用語</span><span class="sxs-lookup"><span data-stu-id="02ce5-106">Term</span></span>|<span data-ttu-id="02ce5-107">定義</span><span class="sxs-lookup"><span data-stu-id="02ce5-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="02ce5-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="02ce5-108">`+` &#124; `-`</span></span>|<span data-ttu-id="02ce5-109">任意。</span><span class="sxs-lookup"><span data-stu-id="02ce5-109">Optional.</span></span> <span data-ttu-id="02ce5-110">`-removeintchecks-` オプションを指定すると、すべての整数計算について、オーバーフロー エラーの有無がコンパイラでチェックされます。</span><span class="sxs-lookup"><span data-stu-id="02ce5-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="02ce5-111">既定値は、`-removeintchecks-` です。</span><span class="sxs-lookup"><span data-stu-id="02ce5-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="02ce5-112">`-removeintchecks` または `-removeintchecks+` を指定すると、エラー チェックが行われず、整数計算を高速にすることができます。</span><span class="sxs-lookup"><span data-stu-id="02ce5-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="02ce5-113">ただし、エラー チェックが行われず、データ型の容量がオーバーフローした場合は、エラーが発生することなく誤った結果が格納される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="02ce5-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="02ce5-114">Visual Studio 統合開発環境で -removeintchecks を設定するには</span><span class="sxs-lookup"><span data-stu-id="02ce5-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="02ce5-115">1.**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="02ce5-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="02ce5-116">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02ce5-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="02ce5-117">2. **[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="02ce5-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="02ce5-118">3. **[詳細設定]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="02ce5-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="02ce5-119">4. **[整数オーバーフローのチェックを解除]** ボックスの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="02ce5-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="02ce5-120">例</span><span class="sxs-lookup"><span data-stu-id="02ce5-120">Example</span></span>  
 <span data-ttu-id="02ce5-121">次のコードでは、`Test.vb` がコンパイルされ、整数オーバーフロー エラーのチェックがオフにされます。</span><span class="sxs-lookup"><span data-stu-id="02ce5-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="02ce5-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="02ce5-122">See also</span></span>

- [<span data-ttu-id="02ce5-123">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="02ce5-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="02ce5-124">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="02ce5-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
