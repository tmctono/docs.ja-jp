---
title: ディレクティブ
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: d76e10ad5ce8ad3accdc84f97146e0816048d8f3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343802"
---
# <a name="directives-visual-basic"></a><span data-ttu-id="8e1b9-102">ディレクティブ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e1b9-102">Directives (Visual Basic)</span></span>

<span data-ttu-id="8e1b9-103">このセクションのトピックでは、Visual Basic ソース コードのコンパイラ ディレクティブについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8e1b9-103">The topics in this section document the Visual Basic source code compiler directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8e1b9-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8e1b9-104">In This Section</span></span>  

 <span data-ttu-id="8e1b9-105">[#Const ディレクティブ](../../../visual-basic/language-reference/directives/const-directive.md)--コンパイラ定数を定義します。</span><span class="sxs-lookup"><span data-stu-id="8e1b9-105">[#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md) -- Define a compiler constant</span></span>  
  
 <span data-ttu-id="8e1b9-106">[#ExternalSource ディレクティブ](../../../visual-basic/language-reference/directives/externalsource-directive.md)--ソース行とソース外部のテキストとの間のマッピングを示します。</span><span class="sxs-lookup"><span data-stu-id="8e1b9-106">[#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md) -- Indicate a mapping between source lines and text external to the source</span></span>  
  
 <span data-ttu-id="8e1b9-107">[#If...次に... #Else ディレクティブ](../../../visual-basic/language-reference/directives/if-then-else-directives.md)--選択したコードブロックをコンパイルします</span><span class="sxs-lookup"><span data-stu-id="8e1b9-107">[#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) -- Compile selected blocks of code</span></span>  
  
 <span data-ttu-id="8e1b9-108">[#Region ディレクティブ](../../../visual-basic/language-reference/directives/region-directive.md)--Visual Studio エディターでコードのセクションを折りたたんで非表示にします</span><span class="sxs-lookup"><span data-stu-id="8e1b9-108">[#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) -- Collapse and hide sections of code in the Visual Studio editor</span></span>  
  
 <span data-ttu-id="8e1b9-109">**#Disable、#Enable** --コードの領域に対して特定の警告を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="8e1b9-109">**#Disable, #Enable** -- Disable and enable specific warnings for regions of code.</span></span>  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 <span data-ttu-id="8e1b9-110">警告コードのコンマ区切りリストを無効および有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8e1b9-110">You can disable and enable a comma-separated list of warning codes too.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8e1b9-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e1b9-111">Related Sections</span></span>  

 [<span data-ttu-id="8e1b9-112">Visual Basic の言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="8e1b9-112">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
  
 [<span data-ttu-id="8e1b9-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8e1b9-113">Visual Basic</span></span>](../../../visual-basic/index.md)
