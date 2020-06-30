---
title: ディレクティブ
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: b5fcf3cb8801bc99dd2096c28cc41ebefeb34592
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "85503815"
---
# <a name="directives-visual-basic"></a><span data-ttu-id="5981b-102">ディレクティブ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5981b-102">Directives (Visual Basic)</span></span>

<span data-ttu-id="5981b-103">このセクションのトピックでは、Visual Basic ソース コードのコンパイラ ディレクティブについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5981b-103">The topics in this section document the Visual Basic source code compiler directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5981b-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5981b-104">In This Section</span></span>  

 <span data-ttu-id="5981b-105">[#Const ディレクティブ](const-directive.md) -- コンパイラ定数を定義します</span><span class="sxs-lookup"><span data-stu-id="5981b-105">[#Const Directive](const-directive.md) -- Define a compiler constant</span></span>  
  
 <span data-ttu-id="5981b-106">[#ExternalSource ディレクティブ](externalsource-directive.md) -- ソース行とソース外部のテキストのマッピングを指定します</span><span class="sxs-lookup"><span data-stu-id="5981b-106">[#ExternalSource Directive](externalsource-directive.md) -- Indicate a mapping between source lines and text external to the source</span></span>  
  
 <span data-ttu-id="5981b-107">[#If...Then...#Else ディレクティブ](if-then-else-directives.md) -- 選択したコード ブロックをコンパイルします</span><span class="sxs-lookup"><span data-stu-id="5981b-107">[#If...Then...#Else Directives](if-then-else-directives.md) -- Compile selected blocks of code</span></span>  
  
 <span data-ttu-id="5981b-108">[#Region ディレクティブ](region-directive.md) -- Visual Studio エディターでコードのセクションを折りたたんで非表示にします</span><span class="sxs-lookup"><span data-stu-id="5981b-108">[#Region Directive](region-directive.md) -- Collapse and hide sections of code in the Visual Studio editor</span></span>  
  
 <span data-ttu-id="5981b-109">**#Disable、#Enable** -- コードの領域に対して特定の警告を無効および有効にします。</span><span class="sxs-lookup"><span data-stu-id="5981b-109">**#Disable, #Enable** -- Disable and enable specific warnings for regions of code.</span></span>  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 <span data-ttu-id="5981b-110">警告コードのコンマ区切りリストを無効および有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5981b-110">You can disable and enable a comma-separated list of warning codes too.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5981b-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="5981b-111">Related Sections</span></span>  

 [<span data-ttu-id="5981b-112">Visual Basic の言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="5981b-112">Visual Basic Language Reference</span></span>](../index.md)  
  