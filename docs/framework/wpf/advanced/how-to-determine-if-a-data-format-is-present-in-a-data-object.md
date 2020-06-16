---
title: '方法: データ形式がデータ オブジェクトに存在するかどうかを判別する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataFormats class [WPF]
- drag-and-drop [WPF], data formats present
- data formats [WPF], determining if present
ms.assetid: e487a454-c9fc-4e53-aeaa-c458d059ad4c
ms.openlocfilehash: 4cec733490e2a9dc5d54b3b253ac38a5090ac885
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776247"
---
# <a name="how-to-determine-if-a-data-format-is-present-in-a-data-object"></a><span data-ttu-id="23350-102">方法: データ形式がデータ オブジェクトに存在するかどうかを判別する</span><span class="sxs-lookup"><span data-stu-id="23350-102">How to: Determine if a Data Format is Present in a Data Object</span></span>
<span data-ttu-id="23350-103">次の例は、さまざまな <xref:System.Windows.DataObject.GetDataPresent%2A> メソッドのオーバーロードを使用して、特定のデータ形式がデータ オブジェクトに存在するかどうかのクエリを実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="23350-103">The following examples show how to use the various <xref:System.Windows.DataObject.GetDataPresent%2A> method overloads to query whether a particular data format is present in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23350-104">例</span><span class="sxs-lookup"><span data-stu-id="23350-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="23350-105">説明</span><span class="sxs-lookup"><span data-stu-id="23350-105">Description</span></span>  
 <span data-ttu-id="23350-106">次のコード例では、<xref:System.Windows.DataObject.GetDataPresent%28System.String%29> オーバーロードを使用して、記述子文字列によって特定のデータ形式が存在するかどうかのクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="23350-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to query for the presence of a particular data format by descriptor string.</span></span>  
  
### <a name="code"></a><span data-ttu-id="23350-107">コード</span><span class="sxs-lookup"><span data-stu-id="23350-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_string)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_string)]  
  
## <a name="example"></a><span data-ttu-id="23350-108">例</span><span class="sxs-lookup"><span data-stu-id="23350-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="23350-109">説明</span><span class="sxs-lookup"><span data-stu-id="23350-109">Description</span></span>  
 <span data-ttu-id="23350-110">次のコード例では、<xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> オーバーロードを使用して、型によって特定のデータ形式が存在するかどうかのクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="23350-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> overload to query for the presence of a particular data format by type.</span></span>  
  
### <a name="code"></a><span data-ttu-id="23350-111">コード</span><span class="sxs-lookup"><span data-stu-id="23350-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_type)]  
  
## <a name="example"></a><span data-ttu-id="23350-112">例</span><span class="sxs-lookup"><span data-stu-id="23350-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="23350-113">説明</span><span class="sxs-lookup"><span data-stu-id="23350-113">Description</span></span>  
 <span data-ttu-id="23350-114">次のコード例では、<xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> オーバーロードを使用して、記述子文字列によってデータのクエリを実行し、自動変換可能なデータ形式を扱う方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="23350-114">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to query for data by descriptor string, and specifying how to treat auto-convertible data formats.</span></span>  
  
### <a name="code"></a><span data-ttu-id="23350-115">コード</span><span class="sxs-lookup"><span data-stu-id="23350-115">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_autoconvert)]  
  
## <a name="see-also"></a><span data-ttu-id="23350-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="23350-116">See also</span></span>

- <xref:System.Windows.IDataObject>
