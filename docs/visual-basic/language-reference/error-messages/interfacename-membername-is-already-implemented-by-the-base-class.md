---
title: "'<interfacename>.<membername>' は、基本クラス '<baseclassname>' によって既に実装されています。 <type> の再実装と見なされます。"
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 64bd7771820c2a4073350b7a5189d3a32c4775be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921330"
---
# <a name="interfacenamemembername-is-already-implemented-by-the-base-class-baseclassname-re-implementation-of-type-assumed"></a><span data-ttu-id="2f477-103">'\<interfacename>.\<membername>' は、基本クラス '\<baseclassname>' によって既に実装されています。</span><span class="sxs-lookup"><span data-stu-id="2f477-103">'\<interfacename>.\<membername>' is already implemented by the base class '\<baseclassname>'.</span></span> <span data-ttu-id="2f477-104">\<type> の再実装と見なされます。</span><span class="sxs-lookup"><span data-stu-id="2f477-104">Re-implementation of \<type> assumed</span></span>
<span data-ttu-id="2f477-105">プロパティ、プロシージャ、または派生クラスでイベントを使用して、`Implements`句は既に基本クラスで実装されているインターフェイス メンバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="2f477-105">A property, procedure, or event in a derived class uses an `Implements` clause specifying an interface member that is already implemented in the base class.</span></span>  
  
 <span data-ttu-id="2f477-106">派生クラスでは、その基底クラスによって実装されているインターフェイス メンバーを再実装できます。</span><span class="sxs-lookup"><span data-stu-id="2f477-106">A derived class can reimplement an interface member that is implemented by its base class.</span></span> <span data-ttu-id="2f477-107">このことは、基底クラスの実装をオーバーライドすることとは異なります。</span><span class="sxs-lookup"><span data-stu-id="2f477-107">This is not the same as overriding the base class implementation.</span></span> <span data-ttu-id="2f477-108">詳細については、「 [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f477-108">For more information, see [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).</span></span>  
  
 <span data-ttu-id="2f477-109">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="2f477-109">By default, this message is a warning.</span></span> <span data-ttu-id="2f477-110">警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「[Visual Basic での警告の構成](/visualstudio/ide/configuring-warnings-in-visual-basic)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2f477-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="2f477-111">**エラー ID:** BC42015</span><span class="sxs-lookup"><span data-stu-id="2f477-111">**Error ID:** BC42015</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2f477-112">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="2f477-112">To correct this error</span></span>  
  
- <span data-ttu-id="2f477-113">インターフェイス メンバーを再実装する場合は、操作を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2f477-113">If you intend to reimplement the interface member, you do not need to take any action.</span></span> <span data-ttu-id="2f477-114">派生クラスのコードで使用しない限り、再実装されたメンバーにアクセスする、`MyBase`キーワードを基底クラスの実装にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2f477-114">Code in your derived class accesses the reimplemented member unless you use the `MyBase` keyword to access the base class implementation.</span></span>  
  
- <span data-ttu-id="2f477-115">インターフェイス メンバーを再実装しない場合は、プロパティ、プロシージャ、またはイベント宣言から、 `Implements` 句を削除します。</span><span class="sxs-lookup"><span data-stu-id="2f477-115">If you do not intend to reimplement the interface member, remove the `Implements` clause from the property, procedure, or event declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f477-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f477-116">See also</span></span>

- [<span data-ttu-id="2f477-117">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2f477-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
