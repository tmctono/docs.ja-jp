---
title: Windows フォーム DataGridView コントロールでのデータ入力
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], data entry
- data entry [Windows Forms], dataGridView control
- data grids [Windows Forms], data entry
ms.assetid: 4a6d4676-d4e7-4b0e-9c22-50ce65ffe0d6
ms.openlocfilehash: e3022ceddd9fab5610a0856b5e3273d8c046a5fa
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719740"
---
# <a name="data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="7f8e6-102">Windows フォーム DataGridView コントロールでのデータ入力</span><span class="sxs-lookup"><span data-stu-id="7f8e6-102">Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="7f8e6-103">`DataGridView`コントロールはユーザーを追加またはコントロール内のデータを変更する方法を変更できるのいくつかの機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="7f8e6-103">The `DataGridView` control provides several features that let you change how users add or modify data in the control.</span></span> <span data-ttu-id="7f8e6-104">たとえば、行うことができますデータ エントリより効率的なユーザーに警告するエラーが発生したときに、新しい行の既定値を提供することで。</span><span class="sxs-lookup"><span data-stu-id="7f8e6-104">For example, you can make data entry more efficient by providing default values for new rows and by alerting users when errors occur.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7f8e6-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7f8e6-105">In This Section</span></span>  
 [<span data-ttu-id="7f8e6-106">方法: Windows フォームの DataGridView コントロールの編集モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="7f8e6-106">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>](how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="7f8e6-107">ユーザーがセルの編集を開始する方法を変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f8e6-107">Describes how to change the way users start editing cells.</span></span>  
  
 [<span data-ttu-id="7f8e6-108">方法: Windows フォームの DataGridView コントロール内の新しい行の既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="7f8e6-108">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>](specify-default-values-for-new-rows-in-the-datagrid.md)  
 <span data-ttu-id="7f8e6-109">データ エントリの時間を節約する新しいレコードの行を事前に設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f8e6-109">Describes how to prepopulate the row for new records to save data-entry time.</span></span>  
  
 [<span data-ttu-id="7f8e6-110">Windows フォーム DataGridView コントロールにおける新規レコード行の使用</span><span class="sxs-lookup"><span data-stu-id="7f8e6-110">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="7f8e6-111">詳細を非表示に、その外観をカスタマイズする方法のおよびとの関連の情報を含む新しいレコードの行について説明します、<xref:System.Windows.Forms.DataGridView.Rows%2A>コレクション。</span><span class="sxs-lookup"><span data-stu-id="7f8e6-111">Describes the row for new records in detail, including information on hiding it, on customizing its appearance, and on how it relates to the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span>  
  
 [<span data-ttu-id="7f8e6-112">チュートリアル: Windows フォームの DataGridView コントロールのデータの検証</span><span class="sxs-lookup"><span data-stu-id="7f8e6-112">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="7f8e6-113">データ エントリの形式エラーを防ぐためにユーザー入力を検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f8e6-113">Describes how to validate user input to prevent data-entry formatting errors.</span></span>  
  
 [<span data-ttu-id="7f8e6-114">チュートリアル: Windows フォームの DataGridView コントロールでのデータ入力中に発生したエラーの処理</span><span class="sxs-lookup"><span data-stu-id="7f8e6-114">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 <span data-ttu-id="7f8e6-115">ユーザーが新しい値をコミットしようとしたときに、データ ソースから送信されるデータ エントリ エラーを処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f8e6-115">Describes how to handle data-entry errors that originate from the data source when the user attempts to commit a new value.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7f8e6-116">参照</span><span class="sxs-lookup"><span data-stu-id="7f8e6-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="7f8e6-117">
  <xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。</span><span class="sxs-lookup"><span data-stu-id="7f8e6-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="7f8e6-118">リファレンス ドキュメントを提供、<xref:System.Windows.Forms.DataGridView.EditMode%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="7f8e6-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.EditMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>  
 <span data-ttu-id="7f8e6-119">リファレンス ドキュメントを提供、<xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>イベント。</span><span class="sxs-lookup"><span data-stu-id="7f8e6-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataError?displayProperty=nameWithType>  
 <span data-ttu-id="7f8e6-120">リファレンス ドキュメントを提供、<xref:System.Windows.Forms.DataGridView.DataError>イベント。</span><span class="sxs-lookup"><span data-stu-id="7f8e6-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataError> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellValidating?displayProperty=nameWithType>  
 <span data-ttu-id="7f8e6-121">リファレンス ドキュメントを提供、<xref:System.Windows.Forms.DataGridView.CellValidating>イベント。</span><span class="sxs-lookup"><span data-stu-id="7f8e6-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellValidating> event.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7f8e6-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f8e6-122">Related Sections</span></span>  
 [<span data-ttu-id="7f8e6-123">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="7f8e6-123">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="7f8e6-124">手動または外部データ ソースからのコントロールにデータを設定する方法を説明するトピックを提供します。</span><span class="sxs-lookup"><span data-stu-id="7f8e6-124">Provides topics that describe how to populate the control with data either manually or from an external data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f8e6-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f8e6-125">See also</span></span>
- [<span data-ttu-id="7f8e6-126">DataGridView コントロール</span><span class="sxs-lookup"><span data-stu-id="7f8e6-126">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="7f8e6-127">Windows フォーム DataGridView コントロールの列型</span><span class="sxs-lookup"><span data-stu-id="7f8e6-127">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
