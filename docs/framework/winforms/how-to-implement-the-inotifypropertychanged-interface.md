---
title: '方法: INotifyPropertyChanged インターフェイスを実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
ms.openlocfilehash: cfdfb22fd854a8f630243e0f612761c71cb778d8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225600"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a><span data-ttu-id="4e346-102">方法: INotifyPropertyChanged インターフェイスを実装する</span><span class="sxs-lookup"><span data-stu-id="4e346-102">How to: Implement the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="4e346-103">次のコード例は、実装する方法を示します、<xref:System.ComponentModel.INotifyPropertyChanged>インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="4e346-103">The following code example demonstrates how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="4e346-104">Windows フォーム データ バインディングで使用されているビジネス オブジェクトでこのインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="4e346-104">Implement this interface on business objects that are used in Windows Forms data binding.</span></span> <span data-ttu-id="4e346-105">実装された場合、インターフェイスは、ビジネス オブジェクトでプロパティの変更をバインドされたコントロールに通信します。</span><span class="sxs-lookup"><span data-stu-id="4e346-105">When implemented, the interface  communicates to a bound control the property changes on a business object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e346-106">例</span><span class="sxs-lookup"><span data-stu-id="4e346-106">Example</span></span>  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4e346-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e346-107">See also</span></span>

- [<span data-ttu-id="4e346-108">方法: PropertyNameChanged パターンを適用します。</span><span class="sxs-lookup"><span data-stu-id="4e346-108">How to: Apply the PropertyNameChanged Pattern</span></span>](how-to-apply-the-propertynamechanged-pattern.md)
- [<span data-ttu-id="4e346-109">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="4e346-109">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="4e346-110">方法: BindingSource と INotifyPropertyChanged インターフェイスを使用して変更通知を発生させる</span><span class="sxs-lookup"><span data-stu-id="4e346-110">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](./controls/raise-change-notifications--bindingsource.md)
- [<span data-ttu-id="4e346-111">Windows フォーム データ バインドの変更通知</span><span class="sxs-lookup"><span data-stu-id="4e346-111">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
