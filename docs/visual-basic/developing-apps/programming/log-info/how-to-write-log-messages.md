---
title: '方法: ログ メッセージを書き込む'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, writing log messages
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
ms.openlocfilehash: 28c5fe77e2711dfcac96e621a90fb9506eb74775
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410050"
---
# <a name="how-to-write-log-messages-visual-basic"></a><span data-ttu-id="fc0d9-102">方法: ログ メッセージを書き込む (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc0d9-102">How to: Write Log Messages (Visual Basic)</span></span>

<span data-ttu-id="fc0d9-103">`My.Application.Log` オブジェクトおよび `My.Log` オブジェクトを使用すると、アプリケーションに関する情報をログに記録できます。</span><span class="sxs-lookup"><span data-stu-id="fc0d9-103">You can use the `My.Application.Log` and `My.Log` objects to log information about your application.</span></span> <span data-ttu-id="fc0d9-104">この例では、 `My.Application.Log.WriteEntry` メソッドを使用してトレース情報をログに記録する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fc0d9-104">This example shows how to use the `My.Application.Log.WriteEntry` method to log tracing information.</span></span>

<span data-ttu-id="fc0d9-105">例外情報をログに記録するには、`My.Application.Log.WriteException` メソッドを使います。方法については、「[方法 : 例外をログに記録する](how-to-log-exceptions.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fc0d9-105">For logging exception information, use the `My.Application.Log.WriteException` method; see [How to: Log Exceptions](how-to-log-exceptions.md).</span></span>

## <a name="example"></a><span data-ttu-id="fc0d9-106">例</span><span class="sxs-lookup"><span data-stu-id="fc0d9-106">Example</span></span>

<span data-ttu-id="fc0d9-107">この例では、 `My.Application.Log.WriteEntry` メソッドを使用してトレース情報を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="fc0d9-107">This example uses the `My.Application.Log.WriteEntry` method to write out the trace information.</span></span>

[!code-vb[VbVbalrMyApplicationLog#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#11)]

## <a name="net-framework-security"></a><span data-ttu-id="fc0d9-108">.NET Framework のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="fc0d9-108">.NET Framework Security</span></span>

<span data-ttu-id="fc0d9-109">ログに書き込むデータに、ユーザーのパスワードなどの機密情報が含まれないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="fc0d9-109">Make sure the data you write to the log does not include sensitive information such as user passwords.</span></span> <span data-ttu-id="fc0d9-110">詳しくは、「[アプリケーション ログの使用](working-with-application-logs.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fc0d9-110">For more information, see [Working with Application Logs](working-with-application-logs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fc0d9-111">参照</span><span class="sxs-lookup"><span data-stu-id="fc0d9-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="fc0d9-112">アプリケーション ログの使用</span><span class="sxs-lookup"><span data-stu-id="fc0d9-112">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="fc0d9-113">方法 : 例外をログに記録する</span><span class="sxs-lookup"><span data-stu-id="fc0d9-113">How to: Log Exceptions</span></span>](how-to-log-exceptions.md)
- [<span data-ttu-id="fc0d9-114">チュートリアル : My.Application.Log による情報の書き込み先の確認</span><span class="sxs-lookup"><span data-stu-id="fc0d9-114">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](walkthrough-determining-where-my-application-log-writes-information.md)
- [<span data-ttu-id="fc0d9-115">チュートリアル : My.Application.Log による情報の書き込み先の変更</span><span class="sxs-lookup"><span data-stu-id="fc0d9-115">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](walkthrough-changing-where-my-application-log-writes-information.md)
- [<span data-ttu-id="fc0d9-116">チュートリアル : My.Application.Log の出力をフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="fc0d9-116">Walkthrough: Filtering My.Application.Log Output</span></span>](walkthrough-filtering-my-application-log-output.md)
