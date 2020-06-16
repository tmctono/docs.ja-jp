---
title: '方法: データ オブジェクト内のデータ形式の一覧を表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], listing data formats
- DataFormats class [WPF]
- data formats [WPF], listing
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
ms.openlocfilehash: f8230eac33a18a0d99cc757d54c2b901c1afe977
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62001495"
---
# <a name="how-to-list-the-data-formats-in-a-data-object"></a><span data-ttu-id="b2237-102">方法: データ オブジェクト内のデータ形式の一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="b2237-102">How to: List the Data Formats in a Data Object</span></span>
<span data-ttu-id="b2237-103">次の例では、<xref:System.Windows.DataObject.GetFormats%2A> メソッドのオーバーロードを使用して、データ オブジェクトで使用できる各データ形式を示す文字列の配列を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b2237-103">The following examples show how to use the <xref:System.Windows.DataObject.GetFormats%2A> method overloads get an array of strings denoting each data format that is available in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2237-104">例</span><span class="sxs-lookup"><span data-stu-id="b2237-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b2237-105">説明</span><span class="sxs-lookup"><span data-stu-id="b2237-105">Description</span></span>  
 <span data-ttu-id="b2237-106">次のコード例では、<xref:System.Windows.DataObject.GetFormats%2A> のオーバーロードを使用して、データ オブジェクトで使用できるすべてのデータ形式 (ネイティブと自動変換の両方) を示す文字列の配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="b2237-106">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting all data formats available in a data object (both native and auto-convertible).</span></span>  
  
### <a name="code"></a><span data-ttu-id="b2237-107">コード</span><span class="sxs-lookup"><span data-stu-id="b2237-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## <a name="example"></a><span data-ttu-id="b2237-108">例</span><span class="sxs-lookup"><span data-stu-id="b2237-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b2237-109">説明</span><span class="sxs-lookup"><span data-stu-id="b2237-109">Description</span></span>  
 <span data-ttu-id="b2237-110">次のコード例では、<xref:System.Windows.DataObject.GetFormats%2A> のオーバーロードを使用して、データ オブジェクトで使用できるデータ形式のみ (自動変換可能なデータ形式はフィルター処理済み) を示す文字列の配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="b2237-110">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting only data formats available in a data object (auto-convertible data formats are filtered).</span></span>  
  
### <a name="code"></a><span data-ttu-id="b2237-111">コード</span><span class="sxs-lookup"><span data-stu-id="b2237-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## <a name="see-also"></a><span data-ttu-id="b2237-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2237-112">See also</span></span>

- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="b2237-113">ドラッグ アンド ドロップの概要</span><span class="sxs-lookup"><span data-stu-id="b2237-113">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
