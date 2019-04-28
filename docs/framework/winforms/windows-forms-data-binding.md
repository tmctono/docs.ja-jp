---
title: Windows フォームでのデータ バインディング
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms]
- Windows Forms, data binding
- data [Windows Forms], architecture
- Windows Forms controls, data binding
ms.assetid: c3826d8e-ea25-4ad4-a669-45bfb19192aa
ms.openlocfilehash: ed456807137e8cf7594bc50eb0eebb67b88e6b40
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61800114"
---
# <a name="windows-forms-data-binding"></a><span data-ttu-id="9f0c0-102">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="9f0c0-102">Windows Forms Data Binding</span></span>
<span data-ttu-id="9f0c0-103">Windows フォームでのデータ バインディングは、データ ソースの情報をフォーム上のコントロールで表示したり変更したりする手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-103">Data binding in Windows Forms gives you the means to display and make changes to information from a data source in controls on the form.</span></span> <span data-ttu-id="9f0c0-104">従来のデータ ソースに対してだけでなく、データを格納したほとんどすべての構造に対してバインドできます。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-104">You can bind to both traditional data sources as well as almost any structure that contains data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9f0c0-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9f0c0-105">In This Section</span></span>  
 [<span data-ttu-id="9f0c0-106">データ連結と Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="9f0c0-106">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)  
 <span data-ttu-id="9f0c0-107">Windows フォームのデータ バインディングの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-107">Provides an overview of data binding in Windows Forms.</span></span>  
  
 [<span data-ttu-id="9f0c0-108">Windows フォームがサポートするデータ ソース</span><span class="sxs-lookup"><span data-stu-id="9f0c0-108">Data Sources Supported by Windows Forms</span></span>](data-sources-supported-by-windows-forms.md)  
 <span data-ttu-id="9f0c0-109">Windows フォームで使用できるデータ ソースについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-109">Describes the data sources that can be used with Windows Forms.</span></span>  
  
 [<span data-ttu-id="9f0c0-110">データ連結に関連するインターフェイス</span><span class="sxs-lookup"><span data-stu-id="9f0c0-110">Interfaces Related to Data Binding</span></span>](interfaces-related-to-data-binding.md)  
 <span data-ttu-id="9f0c0-111">Windows フォームのデータ バインドで使用されるいくつかのインターフェイスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-111">Describes several of the interfaces used with Windows Forms data binding.</span></span>  
  
 [<span data-ttu-id="9f0c0-112">方法: Windows フォームでデータを移動します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-112">How to: Navigate Data in Windows Forms</span></span>](how-to-navigate-data-in-windows-forms.md)  
 <span data-ttu-id="9f0c0-113">データ ソースの項目間を移動する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-113">Shows how to navigate through items in a data source.</span></span>  
  
 [<span data-ttu-id="9f0c0-114">Windows フォーム データ バインドの変更通知</span><span class="sxs-lookup"><span data-stu-id="9f0c0-114">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)  
 <span data-ttu-id="9f0c0-115">Windows フォーム データ バインドの異なる種類の変更通知について説明します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-115">Describes different types of change notification for Windows Forms data binding.</span></span>  
  
 [<span data-ttu-id="9f0c0-116">方法: INotifyPropertyChanged インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-116">How to: Implement the INotifyPropertyChanged Interface</span></span>](how-to-implement-the-inotifypropertychanged-interface.md)  
 <span data-ttu-id="9f0c0-117"><xref:System.ComponentModel.INotifyPropertyChanged> インターフェイスを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-117">Shows how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="9f0c0-118">インターフェイスは、バインドしたコントロールを通してビジネス オブジェクトのプロパティの変更内容を通信します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-118">The interface  communicates to a bound control the property changes on a business object</span></span>  
  
 [<span data-ttu-id="9f0c0-119">方法: PropertyNameChanged パターンを適用します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-119">How to: Apply the PropertyNameChanged Pattern</span></span>](how-to-apply-the-propertynamechanged-pattern.md)  
 <span data-ttu-id="9f0c0-120">適用する方法を示しています、 *PropertyName*Changed パターンを Windows フォーム ユーザー コントロールのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-120">Shows how to apply the *PropertyName*Changed pattern to properties of a Windows Forms user control.</span></span>  
  
 [<span data-ttu-id="9f0c0-121">方法: ITypedList インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-121">How to: Implement the ITypedList Interface</span></span>](how-to-implement-the-itypedlist-interface.md)  
 <span data-ttu-id="9f0c0-122"><xref:System.ComponentModel.ITypedList> インターフェイスを実装して、バインドできるリストのスキーマを検出できるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-122">Shows how to enable discovery of the schema for a bindable list by implementing the <xref:System.ComponentModel.ITypedList> interface.</span></span>  
  
 [<span data-ttu-id="9f0c0-123">方法: IListSource インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-123">How to: Implement the IListSource Interface</span></span>](how-to-implement-the-ilistsource-interface.md)  
 <span data-ttu-id="9f0c0-124"><xref:System.ComponentModel.IListSource> インターフェイスを実装して、<xref:System.Collections.IList> を実装する代わりに別の場所からリストを提供する、バインドできるクラスを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-124">Shows how to implement the <xref:System.ComponentModel.IListSource> interface to create a bindable class does not implement <xref:System.Collections.IList>, but provides a list from another location.</span></span>  
  
 [<span data-ttu-id="9f0c0-125">方法: 複数のコントロールと同じデータ ソースにバインドが同期を維持</span><span class="sxs-lookup"><span data-stu-id="9f0c0-125">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>](multiple-controls-bound-to-data-source-synchronized.md)  
 <span data-ttu-id="9f0c0-126"><xref:System.Windows.Forms.BindingSource.BindingComplete> イベントを処理して、データ ソースにバインドされているすべてのコントロールの同期を保つ方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-126">Shows how to handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event to ensure all controls bound to a data source remain synchronized.</span></span>  
  
 [<span data-ttu-id="9f0c0-127">方法: 子テーブルの選択行が正しい位置に保持することを確認します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-127">How to: Ensure the Selected Row in a Child Table Remains at the Correct Position</span></span>](ensure-the-selected-row-in-a-child-table-correct.md)  
 <span data-ttu-id="9f0c0-128">親テーブルのフィールドが変更された場合に、子テーブルの選択行が変更されないことを保証する方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-128">Shows how to ensure the selected row of a child table does not change, when a change is made to a field of the parent table.</span></span>  
  
 <span data-ttu-id="9f0c0-129">参照してください[データ バインディングに関連するインターフェイス](interfaces-related-to-data-binding.md)、[方法。Windows フォームでデータを移動](how-to-navigate-data-in-windows-forms.md)、および[方法。Windows フォームに単純バインド コントロールを作成する](how-to-create-a-simple-bound-control-on-a-windows-form.md)します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-129">Also see [Interfaces Related to Data Binding](interfaces-related-to-data-binding.md), [How to: Navigate Data in Windows Forms](how-to-navigate-data-in-windows-forms.md), and [How to: Create a Simple-Bound Control on a Windows Form](how-to-create-a-simple-bound-control-on-a-windows-form.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9f0c0-130">参照</span><span class="sxs-lookup"><span data-stu-id="9f0c0-130">Reference</span></span>  
 <xref:System.Windows.Forms.Binding?displayProperty=nameWithType>  
 <span data-ttu-id="9f0c0-131">バインドできるコンポーネントとデータ ソースの間のバインディングを表すクラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-131">Describes the class that represents the binding between a bindable component and a data source.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType>  
 <span data-ttu-id="9f0c0-132">コントロールにバインドするためにデータ ソースをカプセル化するクラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-132">Describes the class that encapsulates a data source for binding to controls.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9f0c0-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f0c0-133">Related Sections</span></span>  
 [<span data-ttu-id="9f0c0-134">BindingSource コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9f0c0-134">BindingSource Component</span></span>](./controls/bindingsource-component.md)  
 <span data-ttu-id="9f0c0-135"><xref:System.Windows.Forms.BindingSource> コンポーネントの使用方法の例を示すトピックの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-135">Contains a list of topics that demonstrate how to use the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="9f0c0-136">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="9f0c0-136">DataGridView Control</span></span>](./controls/datagridview-control-windows-forms.md)  
 <span data-ttu-id="9f0c0-137">バインドできるデータ グリッド コントロールの使用方法の例を示すトピックの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-137">Provides a list of topics that demonstrate how to use a bindable datagrid control.</span></span>  
  
 <span data-ttu-id="9f0c0-138">参照してください[Visual Studio でのデータへのアクセス](/visualstudio/data-tools/accessing-data-in-visual-studio)します。</span><span class="sxs-lookup"><span data-stu-id="9f0c0-138">Also see [Accessing Data in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).</span></span>
