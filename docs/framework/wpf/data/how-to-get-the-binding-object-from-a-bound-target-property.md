---
title: '方法 : バインドされているターゲット プロパティからのバインディング オブジェクトの取得'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: c528515124898c7deb6114e620ce21766123ab3c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453053"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a><span data-ttu-id="d204c-102">方法 : バインドされているターゲット プロパティからのバインディング オブジェクトの取得</span><span class="sxs-lookup"><span data-stu-id="d204c-102">How to: Get the Binding Object from a Bound Target Property</span></span>
<span data-ttu-id="d204c-103">この例では、データにバインドされているターゲット プロパティからバインディング オブジェクトを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d204c-103">This example shows how to obtain the binding object from a data-bound target property.</span></span>

## <a name="example"></a><span data-ttu-id="d204c-104">例</span><span class="sxs-lookup"><span data-stu-id="d204c-104">Example</span></span>
 <span data-ttu-id="d204c-105"><xref:System.Windows.Data.Binding> オブジェクトを取得するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d204c-105">You can do the following to get the <xref:System.Windows.Data.Binding> object:</span></span>

 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]

> [!NOTE]
> <span data-ttu-id="d204c-106">ターゲット オブジェクトの複数のプロパティがデータ バインディングを使用している可能性があるため、バインディングの依存関係プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d204c-106">You must specify the dependency property for the binding you want because it is possible that more than one property of the target object is using data binding.</span></span>

 <span data-ttu-id="d204c-107">または、<xref:System.Windows.Data.BindingExpression> を取得し、<xref:System.Windows.Data.BindingExpression.ParentBinding%2A> プロパティの値を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="d204c-107">Alternatively, you can get the <xref:System.Windows.Data.BindingExpression> and then get the value of the <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> property.</span></span>

 <span data-ttu-id="d204c-108">コード例全体については、「[バインディングの検証のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d204c-108">For the complete example see [Binding Validation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).</span></span>

> [!NOTE]
> <span data-ttu-id="d204c-109">バインドが <xref:System.Windows.Data.MultiBinding>の場合は、<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A?displayProperty=nameWithType>を使用します。</span><span class="sxs-lookup"><span data-stu-id="d204c-109">If your binding is a <xref:System.Windows.Data.MultiBinding>, use <xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d204c-110"><xref:System.Windows.Data.PriorityBinding>の場合は、<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A?displayProperty=nameWithType>を使用します。</span><span class="sxs-lookup"><span data-stu-id="d204c-110">If it is a <xref:System.Windows.Data.PriorityBinding>, use <xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d204c-111">ターゲットプロパティが <xref:System.Windows.Data.Binding>、<xref:System.Windows.Data.MultiBinding>、または <xref:System.Windows.Data.PriorityBinding>を使用してバインドされているかどうかが不明な場合は、<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A?displayProperty=nameWithType>を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d204c-111">If you are uncertain whether the target property is bound using a <xref:System.Windows.Data.Binding>, a <xref:System.Windows.Data.MultiBinding>, or a <xref:System.Windows.Data.PriorityBinding>, you can use <xref:System.Windows.Data.BindingOperations.GetBindingBase%2A?displayProperty=nameWithType>.</span></span>

## <a name="see-also"></a><span data-ttu-id="d204c-112">参照</span><span class="sxs-lookup"><span data-stu-id="d204c-112">See also</span></span>

- [<span data-ttu-id="d204c-113">コードでバインディングを作成する</span><span class="sxs-lookup"><span data-stu-id="d204c-113">Create a Binding in Code</span></span>](how-to-create-a-binding-in-code.md)
- [<span data-ttu-id="d204c-114">データ バインドに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="d204c-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
