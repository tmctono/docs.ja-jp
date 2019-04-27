---
title: "'<constructorname>' の基本クラス '<baseclassname>' にある '<derivedclassname>' が古い形式に設定されているため、この 'Sub New' の最初のステートメントは、明示的な 'MyBase.New' または 'MyClass.New' への呼び出しでなければなりません: '<errormessage>'"
ms.date: 07/20/2015
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
ms.openlocfilehash: 89b6c241bb637f2efc6014c4640b3b463c4facfa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801882"
---
# <a name="first-statement-of-this-sub-new-must-be-an-explicit-call-to-mybasenew-or-myclassnew-because-the-constructorname-in-the-base-class-baseclassname-of-derivedclassname-is-marked-obsolete-errormessage"></a><span data-ttu-id="ef61d-102">この 'Sub New' の最初のステートメントは、ためには、'mybase.new' または 'myclass.new' の明示的な呼び出しにある必要があります、'\<ある >' の基底クラスの\<baseclassname >' の'\<derivedclassname >' 旧式とマークされて: '\<errormessage >'</span><span class="sxs-lookup"><span data-stu-id="ef61d-102">First statement of this 'Sub New' must be an explicit call to 'MyBase.New' or 'MyClass.New' because the '\<constructorname>' in the base class '\<baseclassname>' of '\<derivedclassname>' is marked obsolete: '\<errormessage>'</span></span>
<span data-ttu-id="ef61d-103">クラス コンストラクターが基底クラスのコンストラクターを明示的に呼び出さず、暗黙的な基底クラスのコンストラクターが <xref:System.ObsoleteAttribute> 属性およびエラーとして扱うことを示すディレクティブでマークされています。</span><span class="sxs-lookup"><span data-stu-id="ef61d-103">A class constructor does not explicitly call a base class constructor, and the implicit base class constructor is marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as an error.</span></span>  
  
 <span data-ttu-id="ef61d-104">派生クラスのコンス トラクターが基底クラスのコンス トラクターを呼び出さない場合、Visual Basic はパラメーターなしの基本クラス コンス トラクターへの暗黙の呼び出しを生成しようとします。</span><span class="sxs-lookup"><span data-stu-id="ef61d-104">When a derived class constructor does not call a base class constructor, Visual Basic attempts to generate an implicit call to a parameterless base class constructor.</span></span> <span data-ttu-id="ef61d-105">引数を指定せずに呼び出すことができる基底クラスにアクセス可能なコンス トラクターがない場合、Visual Basic は、暗黙の呼び出しを生成できません。</span><span class="sxs-lookup"><span data-stu-id="ef61d-105">If there is no accessible constructor in the base class that can be called without arguments, Visual Basic cannot generate an implicit call.</span></span> <span data-ttu-id="ef61d-106">この場合、必要なコンス トラクターがでマークされた、<xref:System.ObsoleteAttribute>属性は、Visual Basic で呼び出すことはできませんので。</span><span class="sxs-lookup"><span data-stu-id="ef61d-106">In this case, the required constructor is marked with the <xref:System.ObsoleteAttribute> attribute, so Visual Basic cannot call it.</span></span>  
  
 <span data-ttu-id="ef61d-107"><xref:System.ObsoleteAttribute> を適用することで、任意のプログラミング要素を使用しない要素としてマークできます。</span><span class="sxs-lookup"><span data-stu-id="ef61d-107">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="ef61d-108">これを行う場合は、属性の<xref:System.ObsoleteAttribute.IsError%2A> プロパティを `True` または `False`に設定できます。</span><span class="sxs-lookup"><span data-stu-id="ef61d-108">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="ef61d-109">`True`に設定した場合、コンパイラは要素を使用する試みをエラーとして扱います。</span><span class="sxs-lookup"><span data-stu-id="ef61d-109">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="ef61d-110">`False`に設定した場合、または既定値の `False`を使用した場合、コンパイラは要素を使用する試みに対して警告を発行します。</span><span class="sxs-lookup"><span data-stu-id="ef61d-110">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="ef61d-111">**エラー ID:** BC30920</span><span class="sxs-lookup"><span data-stu-id="ef61d-111">**Error ID:** BC30920</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ef61d-112">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="ef61d-112">To correct this error</span></span>  
  
1. <span data-ttu-id="ef61d-113">引用符で囲まれたエラー メッセージを確認し、適切な処理を行います。</span><span class="sxs-lookup"><span data-stu-id="ef61d-113">Examine the quoted error message and take appropriate action.</span></span>  
  
2. <span data-ttu-id="ef61d-114">`MyBase.New()` または `MyClass.New()` の呼び出しを `Sub New` の最初のステートメントとして派生クラスに含めます。</span><span class="sxs-lookup"><span data-stu-id="ef61d-114">Include a call to `MyBase.New()` or `MyClass.New()` as the first statement of the `Sub New` in the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef61d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef61d-115">See also</span></span>

- [<span data-ttu-id="ef61d-116">属性の概要</span><span class="sxs-lookup"><span data-stu-id="ef61d-116">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
