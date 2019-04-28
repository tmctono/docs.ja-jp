---
title: '方法: バインドされているターゲット プロパティからのバインディング オブジェクトの取得'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: 7c7392bc11af57b2e9f27e2302f36efb59d40e9d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61933407"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a><span data-ttu-id="5701e-102">方法: バインドされているターゲット プロパティからのバインディング オブジェクトの取得</span><span class="sxs-lookup"><span data-stu-id="5701e-102">How to: Get the Binding Object from a Bound Target Property</span></span>
<span data-ttu-id="5701e-103">この例では、データにバインドされているターゲット プロパティからバインディング オブジェクトを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5701e-103">This example shows how to obtain the binding object from a data-bound target property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5701e-104">例</span><span class="sxs-lookup"><span data-stu-id="5701e-104">Example</span></span>  
 <span data-ttu-id="5701e-105">取得するには、次を行うことができます、<xref:System.Windows.Data.Binding>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5701e-105">You can do the following to get the <xref:System.Windows.Data.Binding> object:</span></span>  
  
 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
>  <span data-ttu-id="5701e-106">ターゲット オブジェクトの複数のプロパティがデータ バインディングを使用している可能性があるため、バインディングの依存関係プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5701e-106">You must specify the dependency property for the binding you want because it is possible that more than one property of the target object is using data binding.</span></span>  
  
 <span data-ttu-id="5701e-107">また、取得できます、<xref:System.Windows.Data.BindingExpression>しの値を取得し、<xref:System.Windows.Data.BindingExpression.ParentBinding%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="5701e-107">Alternatively, you can get the <xref:System.Windows.Data.BindingExpression> and then get the value of the <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> property.</span></span>  
  
 <span data-ttu-id="5701e-108">コード例全体については、「[バインディングの検証のサンプル](https://go.microsoft.com/fwlink/?LinkID=159972)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5701e-108">For the complete example see [Binding Validation Sample](https://go.microsoft.com/fwlink/?LinkID=159972).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5701e-109">バインドがある場合、<xref:System.Windows.Data.MultiBinding>を使用して、 <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>します。</span><span class="sxs-lookup"><span data-stu-id="5701e-109">If your binding is a <xref:System.Windows.Data.MultiBinding>, use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>.</span></span> <span data-ttu-id="5701e-110">ある場合、<xref:System.Windows.Data.PriorityBinding>を使用して、 <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>します。</span><span class="sxs-lookup"><span data-stu-id="5701e-110">If it is a <xref:System.Windows.Data.PriorityBinding>, use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>.</span></span> <span data-ttu-id="5701e-111">ターゲット プロパティを使用してバインドされているかどうかがない場合、 <xref:System.Windows.Data.Binding>、 <xref:System.Windows.Data.MultiBinding>、または<xref:System.Windows.Data.PriorityBinding>、使用することができます<xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>します。</span><span class="sxs-lookup"><span data-stu-id="5701e-111">If you are uncertain whether the target property is bound using a <xref:System.Windows.Data.Binding>, a <xref:System.Windows.Data.MultiBinding>, or a <xref:System.Windows.Data.PriorityBinding>, you can use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5701e-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="5701e-112">See also</span></span>

- [<span data-ttu-id="5701e-113">コードでバインディングを作成する</span><span class="sxs-lookup"><span data-stu-id="5701e-113">Create a Binding in Code</span></span>](how-to-create-a-binding-in-code.md)
- [<span data-ttu-id="5701e-114">方法トピック</span><span class="sxs-lookup"><span data-stu-id="5701e-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
