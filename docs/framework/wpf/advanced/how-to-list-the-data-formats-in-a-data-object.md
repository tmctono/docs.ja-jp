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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077746"
---
# <a name="how-to-list-the-data-formats-in-a-data-object"></a><span data-ttu-id="c576c-102">方法: データ オブジェクト内のデータ形式の一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="c576c-102">How to: List the Data Formats in a Data Object</span></span>
<span data-ttu-id="c576c-103">次の例を使用する方法を示して、<xref:System.Windows.DataObject.GetFormats%2A>メソッドのオーバー ロードは、各データ オブジェクトで使用できるデータ形式を示す文字列の配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="c576c-103">The following examples show how to use the <xref:System.Windows.DataObject.GetFormats%2A> method overloads get an array of strings denoting each data format that is available in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c576c-104">例</span><span class="sxs-lookup"><span data-stu-id="c576c-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c576c-105">説明</span><span class="sxs-lookup"><span data-stu-id="c576c-105">Description</span></span>  
 <span data-ttu-id="c576c-106">次のコード例を使用して、 <xref:System.Windows.DataObject.GetFormats%2A> (ネイティブおよび自動変換可能) は、データ オブジェクトで使用可能なすべてのデータ形式を示す文字列の配列を取得するオーバー ロードします。</span><span class="sxs-lookup"><span data-stu-id="c576c-106">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting all data formats available in a data object (both native and auto-convertible).</span></span>  
  
### <a name="code"></a><span data-ttu-id="c576c-107">コード</span><span class="sxs-lookup"><span data-stu-id="c576c-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## <a name="example"></a><span data-ttu-id="c576c-108">例</span><span class="sxs-lookup"><span data-stu-id="c576c-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c576c-109">説明</span><span class="sxs-lookup"><span data-stu-id="c576c-109">Description</span></span>  
 <span data-ttu-id="c576c-110">次のコード例を使用して、<xref:System.Windows.DataObject.GetFormats%2A>データ オブジェクト (自動変換できるデータの形式はフィルター処理) で使用可能なデータ形式だけを示す文字列の配列を取得するオーバー ロードします。</span><span class="sxs-lookup"><span data-stu-id="c576c-110">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting only data formats available in a data object (auto-convertible data formats are filtered).</span></span>  
  
### <a name="code"></a><span data-ttu-id="c576c-111">コード</span><span class="sxs-lookup"><span data-stu-id="c576c-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## <a name="see-also"></a><span data-ttu-id="c576c-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="c576c-112">See also</span></span>

- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="c576c-113">ドラッグ アンド ドロップの概要</span><span class="sxs-lookup"><span data-stu-id="c576c-113">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
