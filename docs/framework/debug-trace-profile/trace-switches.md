---
title: トレース スイッチ
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tracing [.NET Framework], trace switches
- trace switches, about trace switches
- tracing [.NET Framework], level of detail
- switches, trace
- trace switches
- trace switches, creating custom
ms.assetid: 8ab913aa-f400-4406-9436-f45bc6e54fbe
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 85a1a017197826717280f53995ed98f26f1d80bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61873861"
---
# <a name="trace-switches"></a><span data-ttu-id="f8ea3-102">トレース スイッチ</span><span class="sxs-lookup"><span data-stu-id="f8ea3-102">Trace Switches</span></span>
<span data-ttu-id="f8ea3-103">トレース スイッチを使用すると、トレース出力を有効/無効にしたり、トレースの出力をフィルター処理したりできます。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-103">Trace switches enable you to enable, disable, and filter tracing output.</span></span> <span data-ttu-id="f8ea3-104">トレース スイッチは、コードに存在すれるオブジェクトであり、.config ファイルによって外部的に設定できます。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-104">They are objects that exist in your code and can be configured externally through the .config file.</span></span> <span data-ttu-id="f8ea3-105">.NET Framework に用意されたトレース スイッチには、 <xref:System.Diagnostics.BooleanSwitch> クラス、 <xref:System.Diagnostics.TraceSwitch> クラス、および <xref:System.Diagnostics.SourceSwitch> クラスの 3 種類があります。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-105">There are three types of trace switches provided in the .NET Framework: the <xref:System.Diagnostics.BooleanSwitch> class, the <xref:System.Diagnostics.TraceSwitch> class, and the <xref:System.Diagnostics.SourceSwitch> class.</span></span> <span data-ttu-id="f8ea3-106"><xref:System.Diagnostics.BooleanSwitch> クラスは、トグル スイッチとして機能し、各種のトレース ステートメントを有効にしたり無効にしたりできます。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-106">The <xref:System.Diagnostics.BooleanSwitch> class acts as a toggle switch, either enabling or disabling a variety of trace statements.</span></span> <span data-ttu-id="f8ea3-107"><xref:System.Diagnostics.TraceSwitch> クラスと <xref:System.Diagnostics.SourceSwitch> クラスを使用すると、特定のトレース レベルごとにトレース スイッチを有効にすることができます。これにより、該当するレベルおよびそれ以下のすべてのレベルに対して指定された <xref:System.Diagnostics.Trace> メッセージまたは <xref:System.Diagnostics.TraceSource> メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-107">The <xref:System.Diagnostics.TraceSwitch> and <xref:System.Diagnostics.SourceSwitch> classes allow you to enable a trace switch for a particular tracing level so that the <xref:System.Diagnostics.Trace> or <xref:System.Diagnostics.TraceSource> messages specified for that level and all levels below it appear.</span></span> <span data-ttu-id="f8ea3-108">スイッチを無効にした場合、トレース メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-108">If you disable the switch, the trace messages will not appear.</span></span> <span data-ttu-id="f8ea3-109">すべてのクラスは、他のユーザー定義のスイッチと同様に、どちらも**Switch**という抽象 ( **MustInherit**) クラスから派生したクラスです。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-109">All these classes derive from the abstract (**MustInherit**) class **Switch**, as should any user-developed switches.</span></span>  
  
 <span data-ttu-id="f8ea3-110">トレース スイッチは情報のフィルター処理に役立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-110">Trace switches can be useful for filtering information.</span></span> <span data-ttu-id="f8ea3-111">たとえば、データ アクセス モジュールではすべてのトレース メッセージを表示し、アプリケーションの他の部分ではエラー メッセージだけを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-111">For example, you might want to see every tracing message in a data access module, but only error messages in the rest of the application.</span></span> <span data-ttu-id="f8ea3-112">この場合は、データ アクセス モジュールに対してトレース スイッチを 1 つ使用し、アプリケーションの他の部分に対してスイッチを 1 つ使用します。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-112">In that case, you would use one trace switch for the data access module and one switch for the rest of the application.</span></span> <span data-ttu-id="f8ea3-113">.config ファイルの構成でスイッチを適切に設定することにより、受け取るトレース メッセージの種類を制御できます。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-113">By using the .config file to configure the switches to the appropriate settings, you could control what types of trace message you received.</span></span> <span data-ttu-id="f8ea3-114">詳細については、「[方法 :作成、初期化、およびトレース スイッチを構成する](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)します。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-114">For more information, see [How to: Create, Initialize and Configure Trace Switches](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md).</span></span>  
  
 <span data-ttu-id="f8ea3-115">一般に、配置されたアプリケーションはスイッチが無効にされた状態で実行されるため、ユーザーにとって意味のないトレース メッセージが画面に表示されたり、アプリケーションの実行ごとにログ ファイルに書き込んだりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-115">Typically, a deployed application is executed with its switches disabled, so that users need not observe a lot of irrelevant trace messages appearing on a screen or filling up a log file as the application runs.</span></span> <span data-ttu-id="f8ea3-116">アプリケーションの実行時に問題が発生した場合は、アプリケーションを中断し、スイッチを有効にしてからアプリケーションを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-116">If a problem arises during application execution, you can stop the application, enable the switches, and restart the application.</span></span> <span data-ttu-id="f8ea3-117">これにより、トレース メッセージが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-117">Then the tracing messages will be displayed.</span></span>  
  
 <span data-ttu-id="f8ea3-118">スイッチを使用するには、まず、 **BooleanSwitch** クラス、 **TraceSwitch** クラス、または開発者が定義したスイッチ クラスからスイッチ オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-118">To use a switch you must first create a switch object from a **BooleanSwitch** class, a **TraceSwitch** class, or a developer-defined switch class.</span></span> <span data-ttu-id="f8ea3-119">開発者定義スイッチの作成方法については、「.NET Framework リファレンス」の「 <xref:System.Diagnostics.Switch> クラス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-119">For more information about creating developer-defined switches, see the <xref:System.Diagnostics.Switch> class in the .NET Framework reference.</span></span> <span data-ttu-id="f8ea3-120">次に、スイッチ オブジェクトを使用するタイミングを指定する構成値を設定します。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-120">Then you set a configuration value that specifies when the switch object is to be used.</span></span> <span data-ttu-id="f8ea3-121">その後で、スイッチ オブジェクトの設定を各種の **Trace** (または **Debug**) トレース メソッドでテストします。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-121">You then test the setting of the switch object in various **Trace** (or **Debug**) tracing methods.</span></span>  
  
## <a name="trace-levels"></a><span data-ttu-id="f8ea3-122">トレース レベル</span><span class="sxs-lookup"><span data-stu-id="f8ea3-122">Trace Levels</span></span>  
 <span data-ttu-id="f8ea3-123">**TraceSwitch**を使用するときには、いくつかの付加的な考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-123">When you use **TraceSwitch**, there are additional considerations.</span></span> <span data-ttu-id="f8ea3-124">**TraceSwitch** オブジェクトには、スイッチを特定のレベル以上として設定するかどうかを示す **Boolean** 値を返す、4 つのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-124">A **TraceSwitch** object has four properties that return **Boolean** values indicating whether the switch is set to at least a particular level:</span></span>  
  
-   <xref:System.Diagnostics.TraceSwitch.TraceError%2A?displayProperty=nameWithType>  
  
-   <xref:System.Diagnostics.TraceSwitch.TraceWarning%2A?displayProperty=nameWithType>  
  
-   <xref:System.Diagnostics.TraceSwitch.TraceInfo%2A?displayProperty=nameWithType>  
  
-   <xref:System.Diagnostics.TraceSwitch.TraceVerbose%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="f8ea3-125">レベルを使用することにより、受け取るトレース情報を問題解決に必要な情報だけに制限できます。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-125">Levels allow you to limit the amount of tracing information you receive to only that information needed to solve a problem.</span></span> <span data-ttu-id="f8ea3-126">トレース スイッチを適切なトレース レベルに設定したり構成したりして、トレース出力に必要な詳細レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-126">You specify the level of detail you want in your tracing output by setting and configuring trace switches to the appropriate trace level.</span></span> <span data-ttu-id="f8ea3-127">エラー メッセージ、警告メッセージ、情報メッセージ、または詳細トレース メッセージを受け取ることができます。また、メッセージを一切受け取らないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-127">You can receive error messages, warning messages, informational messages, verbose tracing messages, or no message at all.</span></span>  
  
 <span data-ttu-id="f8ea3-128">各レベルに関連付けるメッセージの種類は、すべて開発者が指定します。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-128">It is entirely up to you to decide what kind of message to associate with each level.</span></span> <span data-ttu-id="f8ea3-129">トレース メッセージの内容は、通常、各レベルに関連付けた内容に依存しますが、レベルごとに動作の違いを設定できます。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-129">Typically, the content of tracing messages depends on what you associate with each level, but you determine the differences between levels.</span></span> <span data-ttu-id="f8ea3-130">たとえば、レベル 3 (**Info**) の問題については詳細な説明を提供するが、レベル 1 (**Error**) の問題についてはエラー参照番号だけを提供する場合があります。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-130">You might want to provide detailed descriptions of a problem at level 3 (**Info**), for example, but provide only an error reference number at level 1 (**Error**).</span></span> <span data-ttu-id="f8ea3-131">アプリケーションで最適な動作を得ることができるスキームは、独自に判断してください。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-131">It is entirely up to you to decide what scheme works best in your application.</span></span>  
  
 <span data-ttu-id="f8ea3-132">これらのプロパティは、 **TraceLevel** 列挙型の値 1 から 4 に対応します。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-132">These properties correspond to the values 1 through 4 of the **TraceLevel** enumeration.</span></span> <span data-ttu-id="f8ea3-133">**TraceLevel** 列挙型のレベルとそれぞれの値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-133">The following table lists the levels of the **TraceLevel** enumeration and their values.</span></span>  
  
|<span data-ttu-id="f8ea3-134">列挙値</span><span class="sxs-lookup"><span data-stu-id="f8ea3-134">Enumerated value</span></span>|<span data-ttu-id="f8ea3-135">整数値</span><span class="sxs-lookup"><span data-stu-id="f8ea3-135">Integer value</span></span>|<span data-ttu-id="f8ea3-136">表示されるメッセージ (または指定された出力対象に書き込まれるメッセージ) の種類</span><span class="sxs-lookup"><span data-stu-id="f8ea3-136">Type of message displayed (or written to a specified output target)</span></span>|  
|----------------------|-------------------|---------------------------------------------------------------------------|  
|<span data-ttu-id="f8ea3-137">オフ</span><span class="sxs-lookup"><span data-stu-id="f8ea3-137">Off</span></span>|<span data-ttu-id="f8ea3-138">0</span><span class="sxs-lookup"><span data-stu-id="f8ea3-138">0</span></span>|<span data-ttu-id="f8ea3-139">なし</span><span class="sxs-lookup"><span data-stu-id="f8ea3-139">None</span></span>|  
|<span data-ttu-id="f8ea3-140">Error</span><span class="sxs-lookup"><span data-stu-id="f8ea3-140">Error</span></span>|<span data-ttu-id="f8ea3-141">1</span><span class="sxs-lookup"><span data-stu-id="f8ea3-141">1</span></span>|<span data-ttu-id="f8ea3-142">エラー メッセージのみ</span><span class="sxs-lookup"><span data-stu-id="f8ea3-142">Only error messages</span></span>|  
|<span data-ttu-id="f8ea3-143">警告</span><span class="sxs-lookup"><span data-stu-id="f8ea3-143">Warning</span></span>|<span data-ttu-id="f8ea3-144">2</span><span class="sxs-lookup"><span data-stu-id="f8ea3-144">2</span></span>|<span data-ttu-id="f8ea3-145">警告メッセージとエラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="f8ea3-145">Warning messages and error messages</span></span>|  
|<span data-ttu-id="f8ea3-146">Info</span><span class="sxs-lookup"><span data-stu-id="f8ea3-146">Info</span></span>|<span data-ttu-id="f8ea3-147">3</span><span class="sxs-lookup"><span data-stu-id="f8ea3-147">3</span></span>|<span data-ttu-id="f8ea3-148">通知メッセージ、警告メッセージ、およびエラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="f8ea3-148">Informational messages, warning messages, and error messages</span></span>|  
|<span data-ttu-id="f8ea3-149">詳細</span><span class="sxs-lookup"><span data-stu-id="f8ea3-149">Verbose</span></span>|<span data-ttu-id="f8ea3-150">4</span><span class="sxs-lookup"><span data-stu-id="f8ea3-150">4</span></span>|<span data-ttu-id="f8ea3-151">詳細メッセージ、情報メッセージ、警告メッセージ、およびエラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="f8ea3-151">Verbose messages, informational messages, warning messages, and error messages</span></span>|  
  
 <span data-ttu-id="f8ea3-152">**TraceSwitch** のプロパティは、スイッチの最大トレース レベルを示します。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-152">The **TraceSwitch** properties indicate the maximum trace level for the switch.</span></span> <span data-ttu-id="f8ea3-153">つまり、指定されたレベルとそれ以下のすべてのレベルについて、トレース情報が書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-153">That is, tracing information is written for the level specified as well as for all lower levels.</span></span> <span data-ttu-id="f8ea3-154">たとえば、 **TraceInfo** が **true**の場合、 **TraceError** と **TraceWarning** も **true** になりますが、 **TraceVerbose** は **false**になることがあります。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-154">For example, if **TraceInfo** is **true**, then **TraceError** and **TraceWarning** are also **true** but **TraceVerbose** might well be **false**.</span></span>  
  
 <span data-ttu-id="f8ea3-155">これらのプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-155">These properties are read-only.</span></span> <span data-ttu-id="f8ea3-156">**TraceSwitch** オブジェクトは、 **TraceLevel** プロパティの設定時にこれらのプロパティを自動的に設定します。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-156">The **TraceSwitch** object automatically sets them when the **TraceLevel** property is set.</span></span> <span data-ttu-id="f8ea3-157">例:</span><span class="sxs-lookup"><span data-stu-id="f8ea3-157">For example:</span></span>  
  
```vb  
Dim myTraceSwitch As New TraceSwitch("SwitchOne", "The first switch")  
myTraceSwitch.Level = TraceLevel.Info  
' This message box displays true, because setting the level to  
' TraceLevel.Info sets all lower levels to true as well.  
MessageBox.Show(myTraceSwitch.TraceWarning.ToString())  
' This messagebox displays false.  
MessageBox.Show(myTraceSwitch.TraceVerbose.ToString())  
```  
  
```csharp  
System.Diagnostics.TraceSwitch myTraceSwitch =   
   new System.Diagnostics.TraceSwitch("SwitchOne", "The first switch");  
myTraceSwitch.Level = System.Diagnostics.TraceLevel.Info;  
// This message box displays true, because setting the level to   
// TraceLevel.Info sets all lower levels to true as well.  
MessageBox.Show(myTraceSwitch.TraceWarning.ToString());  
// This message box displays false.  
MessageBox.Show(myTraceSwitch.TraceVerbose.ToString());  
```  
  
## <a name="developer-defined-switches"></a><span data-ttu-id="f8ea3-158">開発者が定義するスイッチ</span><span class="sxs-lookup"><span data-stu-id="f8ea3-158">Developer-Defined Switches</span></span>  
 <span data-ttu-id="f8ea3-159">**BooleanSwitch** と **TraceSwitch**を指定する以外に、 **Switch** クラスから継承される独自のスイッチを定義して、カスタマイズしたメソッドで基本クラスのメソッドをオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-159">In addition to providing **BooleanSwitch** and **TraceSwitch**, you can define your own switches by inheriting from the **Switch** class and overriding the base class methods with customized methods.</span></span> <span data-ttu-id="f8ea3-160">開発者定義スイッチの作成方法については、「.NET Framework リファレンス」の「 <xref:System.Diagnostics.Switch> クラス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-160">For more information about creating developer-defined switches, see the <xref:System.Diagnostics.Switch> class in the .NET Framework reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8ea3-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8ea3-161">See also</span></span>

- [<span data-ttu-id="f8ea3-162">トレース リスナー</span><span class="sxs-lookup"><span data-stu-id="f8ea3-162">Trace Listeners</span></span>](../../../docs/framework/debug-trace-profile/trace-listeners.md)
- [<span data-ttu-id="f8ea3-163">方法: アプリケーション コードにトレース ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="f8ea3-163">How to: Add Trace Statements to Application Code</span></span>](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)
- [<span data-ttu-id="f8ea3-164">アプリケーションのトレースとインストルメント</span><span class="sxs-lookup"><span data-stu-id="f8ea3-164">Tracing and Instrumenting Applications</span></span>](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)
