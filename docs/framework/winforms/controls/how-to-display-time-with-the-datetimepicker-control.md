---
title: '方法: DateTimePicker コントロールを使用して時間を表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time [Windows Forms], displaying in DateTimePicker control
- examples [Windows Forms], DateTimePicker control
- DateTimePicker control [Windows Forms], displaying time
ms.assetid: 0c1c8b40-1b50-4301-a90c-39516775ccb1
ms.openlocfilehash: f1c1a0abaeddadb44b40d56eb2f8a28e4b58f4f5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651770"
---
# <a name="how-to-display-time-with-the-datetimepicker-control"></a><span data-ttu-id="cf201-102">方法: DateTimePicker コントロールを使用して時間を表示する</span><span class="sxs-lookup"><span data-stu-id="cf201-102">How to: Display Time with the DateTimePicker Control</span></span>
<span data-ttu-id="cf201-103">アプリケーションでユーザーが日付と時刻を選択して、指定された形式で日付と時刻を表示できるようにするには、<xref:System.Windows.Forms.DateTimePicker> コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf201-103">If you want your application to enable users to select a date and time, and to display that date and time in the specified format, use the <xref:System.Windows.Forms.DateTimePicker> control.</span></span> <span data-ttu-id="cf201-104">次の手順は、<xref:System.Windows.Forms.DateTimePicker> コントロールを使用して時刻を表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cf201-104">The following procedure shows how to use the <xref:System.Windows.Forms.DateTimePicker> control to display the time.</span></span>  
  
### <a name="to-display-the-time-with-the-datetimepicker-control"></a><span data-ttu-id="cf201-105">方法 : DateTimePicker コントロールを使用して時間を表示する</span><span class="sxs-lookup"><span data-stu-id="cf201-105">To display the time with the DateTimePicker control</span></span>  
  
1. <span data-ttu-id="cf201-106">
  <xref:System.Windows.Forms.DateTimePicker.Format%2A> プロパティを <xref:System.Windows.Forms.DateTimePickerFormat.Time> に設定します。</span><span class="sxs-lookup"><span data-stu-id="cf201-106">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to <xref:System.Windows.Forms.DateTimePickerFormat.Time></span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#2)]  
  
2. <span data-ttu-id="cf201-107">
  <xref:System.Windows.Forms.DateTimePicker> の <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> プロパティを `true\` に設定します。</span><span class="sxs-lookup"><span data-stu-id="cf201-107">Set the <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> property for the <xref:System.Windows.Forms.DateTimePicker> to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="cf201-108">例</span><span class="sxs-lookup"><span data-stu-id="cf201-108">Example</span></span>  
 <span data-ttu-id="cf201-109">次のコード サンプルは、ユーザーが時刻のみを選択できるようにする <xref:System.Windows.Forms.DateTimePicker> を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cf201-109">The following code sample shows how to create a <xref:System.Windows.Forms.DateTimePicker> that enables users to choose a time only.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cf201-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="cf201-110">Compiling the Code</span></span>  
 <span data-ttu-id="cf201-111">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cf201-111">This example requires:</span></span>  
  
- <span data-ttu-id="cf201-112">System、System.Data、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="cf201-112">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="cf201-113">コマンドラインからこの例を Visual Basic または Visual C# の構築方法の詳細については、[、コマンドラインからビルドする](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf201-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="cf201-114">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf201-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf201-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf201-115">See also</span></span>

- [<span data-ttu-id="cf201-116">DateTimePicker コントロール</span><span class="sxs-lookup"><span data-stu-id="cf201-116">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
