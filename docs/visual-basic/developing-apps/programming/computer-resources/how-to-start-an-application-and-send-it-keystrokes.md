---
title: '方法: アプリケーションを起動してキーストロークを送る ‐ Visual Basic'
ms.date: 10/23/2019
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
ms.openlocfilehash: 033999c07bb5839a264122b2ca330916bdf844b8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "72919391"
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a><span data-ttu-id="5724c-102">方法: アプリケーションを起動してキーストロークを送る ‐ Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5724c-102">How to: start an application and send it keystrokes (Visual Basic)</span></span>

<span data-ttu-id="5724c-103">この例では、<xref:Microsoft.VisualBasic.Interaction.Shell%2A> メソッドを使用してメモ帳アプリケーションを起動した後、[My.Computer.Keyboard.SendKeys](xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A) メソッドを使用してキーストロークを送信することで、文を印刷します。</span><span class="sxs-lookup"><span data-stu-id="5724c-103">This example uses the <xref:Microsoft.VisualBasic.Interaction.Shell%2A> method to start the Notepad application and then prints a sentence by sending keystrokes using the [My.Computer.Keyboard.SendKeys](xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A) method.</span></span>

## <a name="example"></a><span data-ttu-id="5724c-104">例</span><span class="sxs-lookup"><span data-stu-id="5724c-104">Example</span></span>

[!code-vb[VbVbalrMyComputer#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#25)]

## <a name="robust-programming"></a><span data-ttu-id="5724c-105">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="5724c-105">Robust programming</span></span>

<span data-ttu-id="5724c-106">要求されたプロセス ID のアプリケーションが見つからない場合には、<xref:System.ArgumentException> 例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="5724c-106">An <xref:System.ArgumentException> exception is raised if an application with the requested process identifier cannot be found.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="5724c-107">.NET Framework のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="5724c-107">.NET Framework Security</span></span>

<span data-ttu-id="5724c-108">`Shell` 関数の呼び出しには完全な信頼が必要です (<xref:System.Security.SecurityException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="5724c-108">The call to the `Shell` function requires full trust (<xref:System.Security.SecurityException> class).</span></span>

## <a name="see-also"></a><span data-ttu-id="5724c-109">参照</span><span class="sxs-lookup"><span data-stu-id="5724c-109">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
