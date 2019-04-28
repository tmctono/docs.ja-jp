---
title: "'<membername>' は、型 '<typename>' を <containertype> '<containertypename>' 経由でプロジェクトの外側に公開できません。"
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 16f579a05236ba8977a071cb08068be8e98799f8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921083"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a><span data-ttu-id="9931b-102">'\<membername >' の型を公開できません'\<typename >' 経由でプロジェクトの外部\<でフィルター処理します > '\<containertypename >'。</span><span class="sxs-lookup"><span data-stu-id="9931b-102">'\<membername>' cannot expose type '\<typename>' outside the project through \<containertype> '\<containertypename>'</span></span>
<span data-ttu-id="9931b-103">変数、プロシージャのパラメーター、または関数の戻り値が、そのコンテナーの外部に公開されているが、コンテナーの外に必ず公開しない型として宣言されています。</span><span class="sxs-lookup"><span data-stu-id="9931b-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="9931b-104">次のスケルトン コードは、このエラーが発生する状況を示しています。</span><span class="sxs-lookup"><span data-stu-id="9931b-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="9931b-105">宣言されている型`Protected`、 `Friend`、 `Protected Friend`、または`Private`その宣言コンテキストの外部アクセスを制限するためのものです。</span><span class="sxs-lookup"><span data-stu-id="9931b-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="9931b-106">データとして使用制限の少ない方のアクセス権を持つ変数の型はこの目的を倒すとします。</span><span class="sxs-lookup"><span data-stu-id="9931b-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="9931b-107">上記のスケルトン コード`exposedVar`は`Public`公開と`privateClass`にアクセス権のないコードにします。</span><span class="sxs-lookup"><span data-stu-id="9931b-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="9931b-108">**エラー ID:** BC30909</span><span class="sxs-lookup"><span data-stu-id="9931b-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9931b-109">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="9931b-109">To correct this error</span></span>  
  
- <span data-ttu-id="9931b-110">変数、プロシージャのパラメーター、または関数のアクセス レベルの変更は、少なくともそのデータ型のアクセス レベルと同程度に制限するように返します。</span><span class="sxs-lookup"><span data-stu-id="9931b-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9931b-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="9931b-111">See also</span></span>

- [<span data-ttu-id="9931b-112">Visual Basic でのアクセス レベル</span><span class="sxs-lookup"><span data-stu-id="9931b-112">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
