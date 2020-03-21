---
title: プログレスバー コントロールによって表示される値を設定する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: d295079a96ca19a4e4c98e113a3f3051c6403182
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141812"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a><span data-ttu-id="59896-102">方法 : Windows フォーム ProgressBar コントロールによって表示される値を設定する</span><span class="sxs-lookup"><span data-stu-id="59896-102">How to: Set the Value Displayed by the Windows Forms ProgressBar Control</span></span>
> [!IMPORTANT]
> <span data-ttu-id="59896-103"><xref:System.Windows.Forms.ToolStripProgressBar> コントロールは、<xref:System.Windows.Forms.ProgressBar> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.ProgressBar> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="59896-103">The <xref:System.Windows.Forms.ToolStripProgressBar> control replaces and adds functionality to the <xref:System.Windows.Forms.ProgressBar> control; however, the <xref:System.Windows.Forms.ProgressBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="59896-104">.NET Framework では、<xref:System.Windows.Forms.ProgressBar>コントロール内の特定の値を表示する方法が複数用意されています。</span><span class="sxs-lookup"><span data-stu-id="59896-104">The .NET Framework gives you several different ways to display a given value within the <xref:System.Windows.Forms.ProgressBar> control.</span></span> <span data-ttu-id="59896-105">どちらの方法を選択するかは、目の前のタスクや解決している問題によって異なります。</span><span class="sxs-lookup"><span data-stu-id="59896-105">Which approach you choose will depend on the task at hand or the problem you are solving.</span></span> <span data-ttu-id="59896-106">次の表に、選択できる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="59896-106">The following table shows the approaches you can choose.</span></span>  
  
|<span data-ttu-id="59896-107">アプローチ</span><span class="sxs-lookup"><span data-stu-id="59896-107">Approach</span></span>|<span data-ttu-id="59896-108">説明</span><span class="sxs-lookup"><span data-stu-id="59896-108">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="59896-109">コントロールの値を<xref:System.Windows.Forms.ProgressBar>直接設定します。</span><span class="sxs-lookup"><span data-stu-id="59896-109">Set the value of the <xref:System.Windows.Forms.ProgressBar> control directly.</span></span>|<span data-ttu-id="59896-110">この方法は、データ ソースからのレコードの読み取りなど、関連する項目の合計がわかっているタスクに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="59896-110">This approach is useful for tasks where you know the total of the item measured that will be involved, such as reading records from a data source.</span></span> <span data-ttu-id="59896-111">また、値を 1 回または 2 回だけ設定する必要がある場合は、簡単に設定できます。</span><span class="sxs-lookup"><span data-stu-id="59896-111">Additionally, if you only need to set the value once or twice, this is an easy way to do it.</span></span> <span data-ttu-id="59896-112">最後に、プログレスバーに表示される値を減らす必要がある場合は、このプロセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="59896-112">Finally, use this process if you need to decrease the value displayed by the progress bar.</span></span>|  
|<span data-ttu-id="59896-113">表示を<xref:System.Windows.Forms.ProgressBar>固定値で増やします。</span><span class="sxs-lookup"><span data-stu-id="59896-113">Increase the <xref:System.Windows.Forms.ProgressBar> display by a fixed value.</span></span>|<span data-ttu-id="59896-114">この方法は、経過時間や既知の合計から処理されたファイル数など、最小と最大の間の単純なカウントを表示する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="59896-114">This approach is useful when you are displaying a simple count between the minimum and maximum, such as elapsed time or the number of files that have been processed out of a known total.</span></span>|  
|<span data-ttu-id="59896-115">表示を<xref:System.Windows.Forms.ProgressBar>変化する値で増やします。</span><span class="sxs-lookup"><span data-stu-id="59896-115">Increase the <xref:System.Windows.Forms.ProgressBar> display by a value that varies.</span></span>|<span data-ttu-id="59896-116">この方法は、表示される値を別の金額で何度も変更する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="59896-116">This approach is useful when you need to change the displayed value a number of times in different amounts.</span></span> <span data-ttu-id="59896-117">たとえば、一連のファイルをディスクに書き込んでいるときに消費されるハード ディスク領域の量を示します。</span><span class="sxs-lookup"><span data-stu-id="59896-117">An example would be showing the amount of hard-disk space being consumed while writing a series of files to the disk.</span></span>|  
  
 <span data-ttu-id="59896-118">進行状況バーで表示される値を設定する最も直接的な方法は、プロパティ<xref:System.Windows.Forms.ProgressBar.Value%2A>を設定することです。</span><span class="sxs-lookup"><span data-stu-id="59896-118">The most direct way to set the value displayed by a progress bar is by setting the <xref:System.Windows.Forms.ProgressBar.Value%2A> property.</span></span> <span data-ttu-id="59896-119">これは、デザイン時または実行時に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="59896-119">This can be done either at design time or at run time.</span></span>  
  
### <a name="to-set-the-progressbar-value-directly"></a><span data-ttu-id="59896-120">進行状況バーの値を直接設定するには</span><span class="sxs-lookup"><span data-stu-id="59896-120">To set the ProgressBar value directly</span></span>  
  
1. <span data-ttu-id="59896-121">コントロールと<xref:System.Windows.Forms.ProgressBar><xref:System.Windows.Forms.ProgressBar.Minimum%2A><xref:System.Windows.Forms.ProgressBar.Maximum%2A>値を設定します。</span><span class="sxs-lookup"><span data-stu-id="59896-121">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="59896-122">コードでは、コントロールの<xref:System.Windows.Forms.ProgressBar.Value%2A>プロパティを、設定した最小値と最大値の間の整数値に設定します。</span><span class="sxs-lookup"><span data-stu-id="59896-122">In code, set the control's <xref:System.Windows.Forms.ProgressBar.Value%2A> property to an integer value between the minimum and maximum values you have established.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="59896-123">プロパティによって確立された<xref:System.Windows.Forms.ProgressBar.Value%2A>境界の外にプロパティを<xref:System.Windows.Forms.ProgressBar.Minimum%2A><xref:System.Windows.Forms.ProgressBar.Maximum%2A>設定すると、コントロールは例外を<xref:System.ArgumentException>スローします。</span><span class="sxs-lookup"><span data-stu-id="59896-123">If you set the <xref:System.Windows.Forms.ProgressBar.Value%2A> property outside the boundaries established by the <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> properties, the control throws an <xref:System.ArgumentException> exception.</span></span>  
  
     <span data-ttu-id="59896-124">値を直接設定する方法を次のコード<xref:System.Windows.Forms.ProgressBar>例に示します。</span><span class="sxs-lookup"><span data-stu-id="59896-124">The following code example illustrates how to set the <xref:System.Windows.Forms.ProgressBar> value directly.</span></span> <span data-ttu-id="59896-125">このコードは、データ ソースからレコードを読み取り、データ レコードが読み取られるたびに進行状況バーとラベルを更新します。</span><span class="sxs-lookup"><span data-stu-id="59896-125">The code reads records from a data source and updates the progress bar and label every time a data record is read.</span></span> <span data-ttu-id="59896-126">この例では<xref:System.Windows.Forms.Label>、フォームにコントロール、<xref:System.Windows.Forms.ProgressBar>コントロール、および`CustomerRow``FirstName``LastName`フィールドとフィールドを呼び出す行を持つデータ テーブルが必要です。</span><span class="sxs-lookup"><span data-stu-id="59896-126">This example requires that your form has a <xref:System.Windows.Forms.Label> control, a <xref:System.Windows.Forms.ProgressBar> control, and a data table with a row called `CustomerRow` with `FirstName` and `LastName` fields.</span></span>  
  
    ```vb  
    Public Sub CreateNewRecords()  
       ' Sets the progress bar's Maximum property to  
       ' the total number of records to be created.  
       ProgressBar1.Maximum = 20  
  
       ' Creates a new record in the dataset.  
       ' NOTE: The code below will not compile, it merely  
       ' illustrates how the progress bar would be used.  
       Dim anyRow As CustomerRow = DatasetName.ExistingTable.NewRow  
       anyRow.FirstName = "Stephen"  
       anyRow.LastName = "James"  
       ExistingTable.Rows.Add(anyRow)  
  
       ' Increases the value displayed by the progress bar.  
       ProgressBar1.Value += 1  
       ' Updates the label to show that a record was read.  
       Label1.Text = "Records Read = " & ProgressBar1.Value.ToString()  
    End Sub  
    ```  
  
    ```csharp  
    public void createNewRecords()  
    {  
       // Sets the progress bar's Maximum property to  
       // the total number of records to be created.  
       progressBar1.Maximum = 20;  
  
       // Creates a new record in the dataset.  
       // NOTE: The code below will not compile, it merely  
       // illustrates how the progress bar would be used.  
       CustomerRow anyRow = DatasetName.ExistingTable.NewRow();  
       anyRow.FirstName = "Stephen";  
       anyRow.LastName = "James";  
       ExistingTable.Rows.Add(anyRow);  
  
       // Increases the value displayed by the progress bar.  
       progressBar1.Value += 1;  
       // Updates the label to show that a record was read.  
       label1.Text = "Records Read = " + progressBar1.Value.ToString();  
    }  
    ```  
  
     一定の間隔で進行する進行状況を表示する場合は、値を設定し、その間隔でコントロールの値を増やす<xref:System.Windows.Forms.ProgressBar>メソッドを呼び出すことができます。 <span data-ttu-id="59896-128">これは、進行状況を全体のパーセンテージとして測定していないタイマーやその他のシナリオに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="59896-128">This is useful for timers and other scenarios where you are not measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a><span data-ttu-id="59896-129">進行状況バーを固定値で増やすには</span><span class="sxs-lookup"><span data-stu-id="59896-129">To increase the progress bar by a fixed value</span></span>  
  
1. <span data-ttu-id="59896-130">コントロールと<xref:System.Windows.Forms.ProgressBar><xref:System.Windows.Forms.ProgressBar.Minimum%2A><xref:System.Windows.Forms.ProgressBar.Maximum%2A>値を設定します。</span><span class="sxs-lookup"><span data-stu-id="59896-130">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="59896-131">コントロールのプロパティを、<xref:System.Windows.Forms.ProgressBar.Step%2A>プログレス バーの表示値を増やす量を表す整数に設定します。</span><span class="sxs-lookup"><span data-stu-id="59896-131">Set the control's <xref:System.Windows.Forms.ProgressBar.Step%2A> property to an integer representing the amount to increase the progress bar's displayed value.</span></span>  
  
3. <span data-ttu-id="59896-132">プロパティに<xref:System.Windows.Forms.ProgressBar.PerformStep%2A>設定された金額で表示される値を変更するには、メソッド<xref:System.Windows.Forms.ProgressBar.Step%2A>を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="59896-132">Call the <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> method to change the value displayed by the amount set in the <xref:System.Windows.Forms.ProgressBar.Step%2A> property.</span></span>  
  
     <span data-ttu-id="59896-133">次のコード例は、進行状況バーがコピー操作でファイルの数を維持する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="59896-133">The following code example illustrates how a progress bar can maintain a count of the files in a copy operation.</span></span>  
  
     <span data-ttu-id="59896-134">次の例では、各ファイルがメモリに読み込まれると、進行状況バーとラベルが更新され、読み取られたファイルの合計が反映されます。</span><span class="sxs-lookup"><span data-stu-id="59896-134">In the following example, as each file is read into memory, the progress bar and label are updated to reflect the total files read.</span></span> <span data-ttu-id="59896-135">この例では、フォームにコントロールと<xref:System.Windows.Forms.Label>コントロールが含<xref:System.Windows.Forms.ProgressBar>まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="59896-135">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
    ```vb  
    Public Sub LoadFiles()  
       ' Sets the progress bar's minimum value to a number representing  
       ' no operations complete -- in this case, no files read.  
       ProgressBar1.Minimum = 0  
       ' Sets the progress bar's maximum value to a number representing  
       ' all operations complete -- in this case, all five files read.  
       ProgressBar1.Maximum = 5  
       ' Sets the Step property to amount to increase with each iteration.  
       ' In this case, it will increase by one with every file read.  
       ProgressBar1.Step = 1  
  
       ' Dimensions a counter variable.  
       Dim i As Integer  
       ' Uses a For...Next loop to iterate through the operations to be  
       ' completed. In this case, five files are to be copied into memory,  
       ' so the loop will execute 5 times.  
       For i = 0 To 4  
          ' Insert code to copy a file  
          ProgressBar1.PerformStep()  
          ' Update the label to show that a file was read.  
          Label1.Text = "# of Files Read = " & ProgressBar1.Value.ToString  
       Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void loadFiles()  
    {  
       // Sets the progress bar's minimum value to a number representing  
       // no operations complete -- in this case, no files read.  
       progressBar1.Minimum = 0;  
       // Sets the progress bar's maximum value to a number representing  
       // all operations complete -- in this case, all five files read.  
       progressBar1.Maximum = 5;  
       // Sets the Step property to amount to increase with each iteration.  
       // In this case, it will increase by one with every file read.  
       progressBar1.Step = 1;  
  
       // Uses a for loop to iterate through the operations to be  
       // completed. In this case, five files are to be copied into memory,  
       // so the loop will execute 5 times.  
       for (int i = 0; i <= 4; i++)  
       {  
          // Inserts code to copy a file  
          progressBar1.PerformStep();  
          // Updates the label to show that a file was read.  
          label1.Text = "# of Files Read = " + progressBar1.Value.ToString();  
       }  
    }  
    ```  
  
     最後に、進行状況バーによって表示される値を増やして、各増加が一意の量になるようにすることができます。 <span data-ttu-id="59896-137">これは、サイズの異なるファイルをハード ディスクに書き込んだり、進行状況を全体の割合として測定したりするなど、一連の一意の操作を追跡する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="59896-137">This is useful when you are keeping track of a series of unique operations, such as writing files of different sizes to a hard disk, or measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a><span data-ttu-id="59896-138">進行状況バーを動的な値で増やすには</span><span class="sxs-lookup"><span data-stu-id="59896-138">To increase the progress bar by a dynamic value</span></span>  
  
1. <span data-ttu-id="59896-139">コントロールと<xref:System.Windows.Forms.ProgressBar><xref:System.Windows.Forms.ProgressBar.Minimum%2A><xref:System.Windows.Forms.ProgressBar.Maximum%2A>値を設定します。</span><span class="sxs-lookup"><span data-stu-id="59896-139">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="59896-140">指定した<xref:System.Windows.Forms.ProgressBar.Increment%2A>整数で表示される値を変更するには、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="59896-140">Call the <xref:System.Windows.Forms.ProgressBar.Increment%2A> method to change the value displayed by an integer you specify.</span></span>  
  
     <span data-ttu-id="59896-141">次のコード例は、コピー操作中に使用されたディスク領域の量をプログレス バーで計算する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="59896-141">The following code example illustrates how a progress bar can calculate how much disk space has been used during a copy operation.</span></span>  
  
     <span data-ttu-id="59896-142">次の例では、各ファイルがハード ディスクに書き込まれると、プログレス バーとラベルが更新され、ハード ディスクの空き容量が反映されます。</span><span class="sxs-lookup"><span data-stu-id="59896-142">In the following example, as each file is written to the hard disk, the progress bar and label are updated to reflect the amount of hard-disk space available.</span></span> <span data-ttu-id="59896-143">この例では、フォームにコントロールと<xref:System.Windows.Forms.Label>コントロールが含<xref:System.Windows.Forms.ProgressBar>まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="59896-143">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
    ```vb  
    Public Sub ReadFiles()  
       ' Sets the progress bar's minimum value to a number
       ' representing the hard disk space before the files are read in.  
       ' You will most likely have to set this using a system call.  
       ' NOTE: The code below is meant to be an example and  
       ' will not compile.  
       ProgressBar1.Minimum = AvailableDiskSpace()  
       ' Sets the progress bar's maximum value to a number
       ' representing the total hard disk space.  
       ' You will most likely have to set this using a system call.  
       ' NOTE: The code below is meant to be an example
       ' and will not compile.  
       ProgressBar1.Maximum = TotalDiskSpace()  
  
       ' Dimension a counter variable.  
       Dim i As Integer  
       ' Uses a For...Next loop to iterate through the operations to be  
       ' completed. In this case, five files are to be written to the disk,  
       ' so it will execute the loop 5 times.  
       For i = 1 To 5  
          ' Insert code to read a file into memory and update file size.  
          ' Increases the progress bar's value based on the size of
          ' the file currently being written.  
          ProgressBar1.Increment(FileSize)  
          ' Updates the label to show available drive space.  
          Label1.Text = "Current Disk Space Used = " &_
          ProgressBar1.Value.ToString()  
       Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void readFiles()  
    {  
       // Sets the progress bar's minimum value to a number
       // representing the hard disk space before the files are read in.  
       // You will most likely have to set this using a system call.  
       // NOTE: The code below is meant to be an example and
       // will not compile.  
       progressBar1.Minimum = AvailableDiskSpace();  
       // Sets the progress bar's maximum value to a number
       // representing the total hard disk space.  
       // You will most likely have to set this using a system call.  
       // NOTE: The code below is meant to be an example
       // and will not compile.  
       progressBar1.Maximum = TotalDiskSpace();  
  
       // Uses a for loop to iterate through the operations to be  
       // completed. In this case, five files are to be written  
       // to the disk, so it will execute the loop 5 times.  
       for (int i = 1; i<= 5; i++)  
       {  
          // Insert code to read a file into memory and update file size.  
          // Increases the progress bar's value based on the size of
          // the file currently being written.  
          progressBar1.Increment(FileSize);  
          // Updates the label to show available drive space.  
          label1.Text = "Current Disk Space Used = " + progressBar1.Value.ToString();  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="59896-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="59896-144">See also</span></span>

- <xref:System.Windows.Forms.ProgressBar>
- <xref:System.Windows.Forms.ToolStripProgressBar>
- [<span data-ttu-id="59896-145">ProgressBar コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="59896-145">ProgressBar Control Overview</span></span>](progressbar-control-overview-windows-forms.md)
- [<span data-ttu-id="59896-146">ProgressBar コントロール</span><span class="sxs-lookup"><span data-stu-id="59896-146">ProgressBar Control</span></span>](progressbar-control-windows-forms.md)
