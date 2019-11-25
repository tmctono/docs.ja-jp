---
title: '方法: シリアル ポートに接続されているモデムをダイヤルする'
ms.date: 07/20/2015
helpviewer_keywords:
- modems [Visual Basic], dialing
- serial ports [Visual Basic], dialing
- My.Computer.Ports object
ms.assetid: 3834db40-f431-45f1-b671-dc91787164b6
ms.openlocfilehash: febec0a8579d34f8ff59066da5b5aa59c1cce6b2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345636"
---
# <a name="how-to-dial-modems-attached-to-serial-ports-in-visual-basic"></a><span data-ttu-id="dcdcc-102">方法: Visual Basic で、シリアル ポートに接続されているモデムをダイヤルする</span><span class="sxs-lookup"><span data-stu-id="dcdcc-102">How to: Dial Modems Attached to Serial Ports in Visual Basic</span></span>

<span data-ttu-id="dcdcc-103">このトピックでは、Visual Basic で `My.Computer.Ports` を使用してモデムをダイヤルする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-103">This topic describes how to use `My.Computer.Ports` to dial a modem in Visual Basic.</span></span>  
  
 <span data-ttu-id="dcdcc-104">通常、モデムはコンピューターのいずれかのシリアル ポートに接続されています。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-104">Typically, the modem is connected to one of the serial ports on the computer.</span></span> <span data-ttu-id="dcdcc-105">アプリケーションがモデムとやり取りするには、適切なシリアル ポートにコマンドを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-105">For your application to communicate with the modem, it must send commands to the appropriate serial port.</span></span>  
  
### <a name="to-dial-a-modem"></a><span data-ttu-id="dcdcc-106">モデムをダイヤルするには</span><span class="sxs-lookup"><span data-stu-id="dcdcc-106">To dial a modem</span></span>  
  
1. <span data-ttu-id="dcdcc-107">モデムが接続されているシリアル ポートを確認します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-107">Determine which serial port the modem is connected to.</span></span> <span data-ttu-id="dcdcc-108">この例では、モデムが COM1 に接続されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-108">This example assumes the modem is on COM1.</span></span>  
  
2. <span data-ttu-id="dcdcc-109">`My.Computer.Ports.OpenSerialPort` メソッドを使用して、ポートへの参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-109">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="dcdcc-110">詳細については、<xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-110">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
     <span data-ttu-id="dcdcc-111">`Using` ブロックを使用すると、アプリケーションが例外を生成した場合でも、シリアル ポートを閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-111">The `Using` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="dcdcc-112">シリアル ポートを操作するコードはすべて、このブロックまたは `Try...Catch...Finally` ブロック内に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-112">All code that manipulates the serial port should appear within this block, or within a `Try...Catch...Finally` block.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#28)]  
  
3. <span data-ttu-id="dcdcc-113">コンピューターがモデムからの伝送を受け取る準備ができたことを示しよう `DtrEnable` プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-113">Set the `DtrEnable` property to indicate that the computer is ready to accept an incoming transmission from the modem.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#29)]  
  
4. <span data-ttu-id="dcdcc-114"><xref:System.IO.Ports.SerialPort.Write%2A> メソッドを使用して、ダイヤル コマンドと電話番号をシリアル ポート経由でモデムに送信します。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-114">Send the dial command and the phone number to the modem through the serial port by means of the <xref:System.IO.Ports.SerialPort.Write%2A> method.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#30)]  
  
## <a name="example"></a><span data-ttu-id="dcdcc-115">例</span><span class="sxs-lookup"><span data-stu-id="dcdcc-115">Example</span></span>  

 [!code-vb[VbVbalrMyComputer#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#27)]  
  
 <span data-ttu-id="dcdcc-116">このコード例は、IntelliSense コード スニペットとしても利用できます。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-116">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="dcdcc-117">コード スニペット ピッカーでは、これは **[接続とネットワーク]** にあります。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-117">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="dcdcc-118">詳細については、「[Code Snippets](/visualstudio/ide/code-snippets)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-118">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dcdcc-119">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="dcdcc-119">Compiling the Code</span></span>  

 <span data-ttu-id="dcdcc-120">この例では、<xref:System?displayProperty=nameWithType> 名前空間への参照が必要です。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-120">This example requires a reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="dcdcc-121">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="dcdcc-121">Robust Programming</span></span>  

 <span data-ttu-id="dcdcc-122">この例では、モデムが COM1 に接続されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-122">This example assumes the modem is connected to COM1.</span></span> <span data-ttu-id="dcdcc-123">コードによって、利用可能なシリアル ポートの一覧から、目的のポートをユーザーが選択できるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-123">We recommend that your code allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="dcdcc-124">詳細については、[Visual Basic で利用可能なシリアル ポートを表示する](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-124">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="dcdcc-125">この例では、アプリケーションが例外をスローした場合でもポートを閉じられるよう、`Using` ブロックを使用しています。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-125">This example uses a `Using` block to make sure that the application closes the port even if it throws an exception.</span></span> <span data-ttu-id="dcdcc-126">詳細については、「[sing ステートメント](../../../../visual-basic/language-reference/statements/using-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-126">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
 <span data-ttu-id="dcdcc-127">この例では、アプリケーションは、モデムをダイヤルした後でシリアル ポートを切断しています。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-127">In this example, the application disconnects the serial port after it dials the modem.</span></span> <span data-ttu-id="dcdcc-128">実際には、モデムとの間でデータの転送が必要となります。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-128">Realistically, you will want to transfer data to and from the modem.</span></span> <span data-ttu-id="dcdcc-129">詳細については、[シリアル ポートから文字列を受信する](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dcdcc-129">For more information, see [How to: Receive Strings From Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcdcc-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="dcdcc-130">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [<span data-ttu-id="dcdcc-131">方法: シリアル ポートに文字列を送信する</span><span class="sxs-lookup"><span data-stu-id="dcdcc-131">How to: Send Strings to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)
- [<span data-ttu-id="dcdcc-132">方法: シリアル ポートから文字列を受信する</span><span class="sxs-lookup"><span data-stu-id="dcdcc-132">How to: Receive Strings From Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)
- [<span data-ttu-id="dcdcc-133">方法: Visual Basic で利用可能なシリアル ポートを表示する</span><span class="sxs-lookup"><span data-stu-id="dcdcc-133">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
