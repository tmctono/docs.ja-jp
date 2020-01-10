---
title: リスト項目の UI オートメーション要素の検索
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
ms.openlocfilehash: 2474edf95bf598ba9284b5f6ac36a9e0af1317a1
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741754"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="04c86-102">リスト項目の UI オートメーション要素の検索</span><span class="sxs-lookup"><span data-stu-id="04c86-102">Find a UI Automation Element for a List Item</span></span>
> [!NOTE]
> <span data-ttu-id="04c86-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="04c86-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="04c86-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]の最新情報については、「 [Windows Automation API: UI Automation (Windows のオートメーション API: UI オートメーション)](/windows/win32/winauto/entry-uiauto-win32)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04c86-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="04c86-105">このトピックでは、項目のインデックスがわかっている場合に、リスト内の項目の <xref:System.Windows.Automation.AutomationElement> を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="04c86-105">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04c86-106">例</span><span class="sxs-lookup"><span data-stu-id="04c86-106">Example</span></span>  
 <span data-ttu-id="04c86-107">次の例では、指定した項目をリストから取得する2つの方法を示します。1つは <xref:System.Windows.Automation.TreeWalker> を使用し、もう1つは <xref:System.Windows.Automation.AutomationElement.FindAll%2A>を使用します。</span><span class="sxs-lookup"><span data-stu-id="04c86-107">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="04c86-108">最初の手法は Win32 コントロールではより高速になる傾向がありますが、2番目の方法は Windows Presentation Foundation (WPF) コントロールではより高速です。</span><span class="sxs-lookup"><span data-stu-id="04c86-108">The first technique tends to be faster for Win32 controls, but the second is faster for Windows Presentation Foundation (WPF) controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="04c86-109">参照</span><span class="sxs-lookup"><span data-stu-id="04c86-109">See also</span></span>

- [<span data-ttu-id="04c86-110">UI オートメーション要素の取得</span><span class="sxs-lookup"><span data-stu-id="04c86-110">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
