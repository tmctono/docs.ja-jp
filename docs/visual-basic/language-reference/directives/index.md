---
title: ディレクティブ
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: b5e857198351b30c0d7a38dce1a9e6d1209b5258
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838144"
---
# <a name="directives-visual-basic"></a><span data-ttu-id="2e148-102">ディレクティブ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e148-102">Directives (Visual Basic)</span></span>

<span data-ttu-id="2e148-103">このセクションのトピックでは、Visual Basic ソース コードのコンパイラ ディレクティブについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2e148-103">The topics in this section document the Visual Basic source code compiler directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2e148-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2e148-104">In This Section</span></span>  

 <span data-ttu-id="2e148-105">[#Const ディレクティブ](../../../visual-basic/language-reference/directives/const-directive.md)--コンパイラ定数を定義します。</span><span class="sxs-lookup"><span data-stu-id="2e148-105">[#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md) -- Define a compiler constant</span></span>  
  
 <span data-ttu-id="2e148-106">[#ExternalSource ディレクティブ](../../../visual-basic/language-reference/directives/externalsource-directive.md)--ソース行とソース外部のテキストとの間のマッピングを示します。</span><span class="sxs-lookup"><span data-stu-id="2e148-106">[#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md) -- Indicate a mapping between source lines and text external to the source</span></span>  
  
 <span data-ttu-id="2e148-107">[#If...Then...#Else ディレクティブ](../../../visual-basic/language-reference/directives/if-then-else-directives.md)--選択したコードブロックをコンパイルします</span><span class="sxs-lookup"><span data-stu-id="2e148-107">[#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) -- Compile selected blocks of code</span></span>  
  
 <span data-ttu-id="2e148-108">[#Region ディレクティブ](../../../visual-basic/language-reference/directives/region-directive.md)--Visual Studio エディターでコードのセクションを折りたたんで非表示にします</span><span class="sxs-lookup"><span data-stu-id="2e148-108">[#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) -- Collapse and hide sections of code in the Visual Studio editor</span></span>  
  
 <span data-ttu-id="2e148-109">**#Disable、#Enable** --コードの領域に対して特定の警告を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="2e148-109">**#Disable, #Enable** -- Disable and enable specific warnings for regions of code.</span></span>  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 <span data-ttu-id="2e148-110">警告コードのコンマ区切りリストを無効および有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2e148-110">You can disable and enable a comma-separated list of warning codes too.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2e148-111">関連セクション</span><span class="sxs-lookup"><span data-stu-id="2e148-111">Related Sections</span></span>  

 [<span data-ttu-id="2e148-112">Visual Basic の言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="2e148-112">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
  