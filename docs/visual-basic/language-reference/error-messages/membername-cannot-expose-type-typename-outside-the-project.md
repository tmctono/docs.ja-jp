---
title: "'<membername>' は、型 '<typename>' を <containertype> '<containertypename>' 経由でプロジェクトの外側に公開できません。"
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: ca67e74d7790352bd1842cb8a59fe1525af6e18c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700897"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a><span data-ttu-id="c5616-102">'\<membername > ' は \<containertype > '\<containertypename > ' 経由でプロジェクト外部の型 '\<typename > ' を公開できません</span><span class="sxs-lookup"><span data-stu-id="c5616-102">'\<membername>' cannot expose type '\<typename>' outside the project through \<containertype> '\<containertypename>'</span></span>
<span data-ttu-id="c5616-103">変数、プロシージャパラメーター、または関数の戻り値は、コンテナーの外部に公開されますが、コンテナーの外部に公開されてはならない型として宣言されています。</span><span class="sxs-lookup"><span data-stu-id="c5616-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="c5616-104">次のスケルトンコードは、このエラーを生成する状況を示しています。</span><span class="sxs-lookup"><span data-stu-id="c5616-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```vb  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="c5616-105">`Protected`、`Friend`、`Protected Friend`、または `Private` として宣言されている型は、宣言コンテキストの外部でアクセスが制限されていることを意図しています。</span><span class="sxs-lookup"><span data-stu-id="c5616-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="c5616-106">アクセス制限が低い変数のデータ型として使用すると、この目的が損なわれます。</span><span class="sxs-lookup"><span data-stu-id="c5616-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="c5616-107">上記のスケルトンコードでは、`exposedVar` は `Public` であり、アクセス権を持たないコードに `privateClass` を公開します。</span><span class="sxs-lookup"><span data-stu-id="c5616-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="c5616-108">**エラー ID:** BC30909</span><span class="sxs-lookup"><span data-stu-id="c5616-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c5616-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="c5616-109">To correct this error</span></span>  
  
- <span data-ttu-id="c5616-110">変数、プロシージャパラメーター、または関数のアクセスレベルを、少なくともそのデータ型のアクセスレベルと同じ制限以上になるように変更します。</span><span class="sxs-lookup"><span data-stu-id="c5616-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5616-111">参照</span><span class="sxs-lookup"><span data-stu-id="c5616-111">See also</span></span>

- [<span data-ttu-id="c5616-112">Visual Basic のアクセスレベル</span><span class="sxs-lookup"><span data-stu-id="c5616-112">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
