---
title: '方法: プリンターのステータスをリモート操作で調査する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- surveying printer status remotely [WPF]
- printer status [WPF], surveying remotely
- remotely surveying printer status [WPF]
- status [WPF], printers [WPF], surveying remotely
ms.assetid: d6324759-8292-4c23-9584-9c708887dc94
ms.openlocfilehash: dc187a4ea120661e8118ce79a966d3d4a3b40711
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59340790"
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a><span data-ttu-id="a4bba-102">方法: プリンターのステータスをリモート操作で調査する</span><span class="sxs-lookup"><span data-stu-id="a4bba-102">How to: Remotely Survey the Status of Printers</span></span>
<span data-ttu-id="a4bba-103">中企業および大企業では、任意の時点において、紙詰まりや用紙切れなどの問題が発生したために動作していないプリンターが複数存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a4bba-103">At any given time at medium and large companies there may be multiple printers that are not working due to a paper jam or being out of paper or some other problematic situation.</span></span> <span data-ttu-id="a4bba-104">プリンターのプロパティで公開されている一連の豊富な[!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)]Microsoft .NET Framework のプリンターの状態を迅速に調査を実行する手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="a4bba-104">The rich set of printer properties exposed in the [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] of Microsoft .NET Framework provide a means for performing a rapid survey of the states of printers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4bba-105">例</span><span class="sxs-lookup"><span data-stu-id="a4bba-105">Example</span></span>  
 <span data-ttu-id="a4bba-106">このようなユーティリティを作成する主な手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a4bba-106">The major steps for creating this kind of utility are as follows.</span></span>  
  
1. <span data-ttu-id="a4bba-107">プリント サーバーの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="a4bba-107">Obtain a list of all print servers.</span></span>  
  
2. <span data-ttu-id="a4bba-108">サーバーをループして、印刷キューを照会します。</span><span class="sxs-lookup"><span data-stu-id="a4bba-108">Loop through the servers to query their print queues.</span></span>  
  
3. <span data-ttu-id="a4bba-109">サーバー ループの各パス内で、すべてのサーバーのキューをループして、キューが現在動作していないことを示している各プロパティを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="a4bba-109">Within each pass of the server loop, loop through all the server's queues and read each property that might indicate that the queue is not currently working.</span></span>  
  
 <span data-ttu-id="a4bba-110">以下のコードは、一連のスニペットを示しています。</span><span class="sxs-lookup"><span data-stu-id="a4bba-110">The code below is a series of snippets.</span></span> <span data-ttu-id="a4bba-111">この例では、説明を簡単にするために、CRLF で区切られたプリント サーバー リストがあることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="a4bba-111">For simplicity, this example assumes that there is a CRLF-delimited list of print servers.</span></span> <span data-ttu-id="a4bba-112">変数`fileOfPrintServers`は、<xref:System.IO.StreamReader>このファイルのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a4bba-112">The variable `fileOfPrintServers` is a <xref:System.IO.StreamReader> object for this file.</span></span> <span data-ttu-id="a4bba-113">すべての呼び出しのため、各サーバー名は、独自の行では、<xref:System.IO.StreamReader.ReadLine%2A>次のサーバーの名前を取得し、移動、<xref:System.IO.StreamReader>の次の行の先頭にカーソル。</span><span class="sxs-lookup"><span data-stu-id="a4bba-113">Since each server name is on its own line, any call of <xref:System.IO.StreamReader.ReadLine%2A> gets the name of the next server and moves the <xref:System.IO.StreamReader>'s cursor to the beginning of the next line.</span></span>  
  
 <span data-ttu-id="a4bba-114">外側のループ内でコードを作成、<xref:System.Printing.PrintServer>最新のプリント サーバーのオブジェクトし、アプリケーションがサーバーに管理権限を持っていることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4bba-114">Within the outer loop, the code creates a <xref:System.Printing.PrintServer> object for the latest print server and specifies that the application is to have administrative rights to the server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4bba-115">使用してパフォーマンスを向上させることができます、多数のサーバーがある場合、<xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29>のみ必要があるプロパティを初期化するコンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="a4bba-115">If there are a lot of servers, you can improve performance by using the <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> constructors that only initialize the properties you are going to need.</span></span>  
  
 <span data-ttu-id="a4bba-116">使用して<xref:System.Printing.PrintServer.GetPrintQueues%2A>のキューに配置してループを開始し、サーバーのすべてのコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="a4bba-116">The example then uses <xref:System.Printing.PrintServer.GetPrintQueues%2A> to create a collection of all of the server's queues and begins to loop through them.</span></span> <span data-ttu-id="a4bba-117">この内側のループは分岐構造になっており、プリンターの状態を確認する 2 つの方法に対応しています。</span><span class="sxs-lookup"><span data-stu-id="a4bba-117">This inner loop contains a branching structure corresponding to the two ways of checking a printer's status:</span></span>  
  
-   <span data-ttu-id="a4bba-118">フラグを読み取ることができます、<xref:System.Printing.PrintQueue.QueueStatus%2A>型のプロパティ<xref:System.Printing.PrintQueueStatus>します。</span><span class="sxs-lookup"><span data-stu-id="a4bba-118">You can read the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property which is of type <xref:System.Printing.PrintQueueStatus>.</span></span>  
  
-   <span data-ttu-id="a4bba-119">など、各関連プロパティを読み取ることができます<xref:System.Printing.PrintQueue.IsOutOfPaper%2A>、および<xref:System.Printing.PrintQueue.IsPaperJammed%2A>します。</span><span class="sxs-lookup"><span data-stu-id="a4bba-119">You can read each relevant property such as <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, and <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.</span></span>  
  
 <span data-ttu-id="a4bba-120">この例では、両方の方法、ユーザーが以前に使用する方法に関して入力を求めし、求めのフラグを使用する場合は、"y"で応答したため、<xref:System.Printing.PrintQueue.QueueStatus%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a4bba-120">This example demonstrates both methods, so the user was previously prompted as to which method to use and responded with "y" if he or she wanted to use the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property.</span></span> <span data-ttu-id="a4bba-121">2 つの方法の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4bba-121">See below for the details of the two methods.</span></span>  
  
 <span data-ttu-id="a4bba-122">最後に、結果がユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4bba-122">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 <span data-ttu-id="a4bba-123">フラグを使用してプリンターの状態を確認する、<xref:System.Printing.PrintQueue.QueueStatus%2A>プロパティに設定されているかどうかを参照してください。 各関連フラグを確認します。</span><span class="sxs-lookup"><span data-stu-id="a4bba-123">To check printer status using the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property, you check each relevant flag to see if it is set.</span></span> <span data-ttu-id="a4bba-124">1 ビットがビット フラグ セットで設定されているかどうかを確認するには、通常、フラグ セットを 1 つのオペランドとし、フラグ自体をもう 1 つのオペランドとして、論理 AND 演算を行います。</span><span class="sxs-lookup"><span data-stu-id="a4bba-124">The standard way to see if one bit is set in a set of bit flags is to perform a logical AND operation with the set of flags as one operand and the flag itself as the other.</span></span> <span data-ttu-id="a4bba-125">フラグ自体には 1 ビットのみが設定されているため、論理 AND の結果は、その同じビットが上限となります。</span><span class="sxs-lookup"><span data-stu-id="a4bba-125">Since the flag itself has only one bit set, the result of the logical AND is that, at most, that same bit is set.</span></span> <span data-ttu-id="a4bba-126">それが該当するかどうかを確認するには、論理 AND の結果とフラグ自体を比較します。</span><span class="sxs-lookup"><span data-stu-id="a4bba-126">To find out whether it is or not, just compare the result of the logical AND with the flag itself.</span></span> <span data-ttu-id="a4bba-127">詳細については、次を参照してください。 <xref:System.Printing.PrintQueueStatus>、 [& 演算子 (C#リファレンス)](~/docs/csharp/language-reference/operators/and-operator.md)、および<xref:System.FlagsAttribute>します。</span><span class="sxs-lookup"><span data-stu-id="a4bba-127">For more information, see <xref:System.Printing.PrintQueueStatus>, the [& Operator (C# Reference)](~/docs/csharp/language-reference/operators/and-operator.md), and <xref:System.FlagsAttribute>.</span></span>  
  
 <span data-ttu-id="a4bba-128">次のコードでは、ビットが設定されている属性ごとに、ユーザーに表示される最終レポートに警告を追加します </span><span class="sxs-lookup"><span data-stu-id="a4bba-128">For each attribute whose bit is set, the code adds a notice to the final report that will be presented to the user.</span></span> <span data-ttu-id="a4bba-129">(コードの最後で呼び出している **ReportAvailabilityAtThisTime** メソッドについては以下で説明します)。</span><span class="sxs-lookup"><span data-stu-id="a4bba-129">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 <span data-ttu-id="a4bba-130">各プロパティを使用してプリンターの状態を確認するには、各プロパティを読み取り、プロパティが `true` の場合にユーザーに表示される最終レポートに警告を追加するだけです </span><span class="sxs-lookup"><span data-stu-id="a4bba-130">To check printer status using each property, you simply read each property and add a note to the final report that will be presented to the user if the property is `true`.</span></span> <span data-ttu-id="a4bba-131">(コードの最後で呼び出している **ReportAvailabilityAtThisTime** メソッドについては以下で説明します)。</span><span class="sxs-lookup"><span data-stu-id="a4bba-131">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 <span data-ttu-id="a4bba-132">**ReportAvailabilityAtThisTime** メソッドは、現在の時刻にキューが使用可能かどうかを確認する必要がある場合に備えて作成されたものです。</span><span class="sxs-lookup"><span data-stu-id="a4bba-132">The **ReportAvailabilityAtThisTime** method was created in case you need to determine if the queue is available at the current time of day.</span></span>  
  
 <span data-ttu-id="a4bba-133">メソッドは何も場合、<xref:System.Printing.PrintQueue.StartTimeOfDay%2A>と<xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>プリンターは常に使用できる、そうであるために、プロパティが等しい。</span><span class="sxs-lookup"><span data-stu-id="a4bba-133">The method will do nothing if the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are equal; because in that case the printer is available at all times.</span></span> <span data-ttu-id="a4bba-134">メソッドが、ため、合計分数に変換するには、現在の時刻を取得するが異なる場合、<xref:System.Printing.PrintQueue.StartTimeOfDay%2A>と<xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>プロパティは、<xref:System.Int32>いない深夜後分を表す<xref:System.DateTime>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a4bba-134">If they are different, the method gets the current time which then has to be converted into total minutes past midnight because the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are <xref:System.Int32>s representing minutes-after-midnight, not <xref:System.DateTime> objects.</span></span> <span data-ttu-id="a4bba-135">最後に、このメソッドは、現在の時刻が、開始時刻と終了時刻の間にあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a4bba-135">Finally, the method checks to see if the current time is between the start and "until" times.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a><span data-ttu-id="a4bba-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4bba-136">See also</span></span>

- <xref:System.Printing.PrintQueue.StartTimeOfDay%2A>
- <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>
- <xref:System.DateTime>
- <xref:System.Printing.PrintQueueStatus>
- <xref:System.FlagsAttribute>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- [<span data-ttu-id="a4bba-137">& 演算子 (C#リファレンス)</span><span class="sxs-lookup"><span data-stu-id="a4bba-137">& Operator (C# Reference)</span></span>](~/docs/csharp/language-reference/operators/and-operator.md)
- [<span data-ttu-id="a4bba-138">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="a4bba-138">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="a4bba-139">印刷の概要</span><span class="sxs-lookup"><span data-stu-id="a4bba-139">Printing Overview</span></span>](printing-overview.md)
