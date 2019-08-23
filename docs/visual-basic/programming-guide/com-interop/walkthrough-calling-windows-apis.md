---
title: 'チュートリアル: Windows API の呼び出し (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- DLLs, calling
- Windows API, walkthroughs
- platform invoke, walkthroughs
- API calls [Visual Basic], walkthroughs [Visual Basic]
- Windows API, calling
- walkthroughs [Visual Basic], API calls
- DllImport attribute, calling Windows API
- Declare statement [Visual Basic], declaring DLL functions
ms.assetid: 9280ca96-7a93-47a3-8d01-6d01be0657cb
ms.openlocfilehash: 8e6d3e7f84c96d145a48daa27918cbb2cb3b61ac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958310"
---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a><span data-ttu-id="38b46-102">チュートリアル: Windows API の呼び出し (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38b46-102">Walkthrough: Calling Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="38b46-103">Windows API は、Windows オペレーティング システムの一部であるダイナミック リンク ライブラリ (Dll) です。</span><span class="sxs-lookup"><span data-stu-id="38b46-103">Windows APIs are dynamic-link libraries (DLLs) that are part of the Windows operating system.</span></span> <span data-ttu-id="38b46-104">独自の手順を記述するのが難しい場合は、タスクを使用してタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="38b46-104">You use them to perform tasks when it is difficult to write equivalent procedures of your own.</span></span> <span data-ttu-id="38b46-105">たとえば、Windows にはという名前`FlashWindowEx`の関数が用意されています。これを使用すると、アプリケーションのタイトルバーを明るい網掛けと暗い影の間で交互にすることができます。</span><span class="sxs-lookup"><span data-stu-id="38b46-105">For example, Windows provides a function named `FlashWindowEx` that lets you make the title bar for an application alternate between light and dark shades.</span></span>  
  
 <span data-ttu-id="38b46-106">Windows API を使用して、コード内の利点は、数十個は既に書き込まれている便利な関数の使用を待機しているが含まれているため、開発時間を保存することができます。</span><span class="sxs-lookup"><span data-stu-id="38b46-106">The advantage of using Windows APIs in your code is that they can save development time because they contain dozens of useful functions that are already written and waiting to be used.</span></span> <span data-ttu-id="38b46-107">欠点は、問題が生じた場合、および晙の処理が難しくなって Windows API であることができます。</span><span class="sxs-lookup"><span data-stu-id="38b46-107">The disadvantage is that Windows APIs can be difficult to work with and unforgiving when things go wrong.</span></span>  
  
 <span data-ttu-id="38b46-108">Windows API では、相互運用性の特殊なカテゴリを表します。</span><span class="sxs-lookup"><span data-stu-id="38b46-108">Windows APIs represent a special category of interoperability.</span></span> <span data-ttu-id="38b46-109">Windows API では、マネージ コードを使用しないでください、タイプ ライブラリ、および Visual Studio で使用されるものとは異なるデータ型を使用して、組み込みはありません。</span><span class="sxs-lookup"><span data-stu-id="38b46-109">Windows APIs do not use managed code, do not have built-in type libraries, and use data types that are different than those used with Visual Studio.</span></span> <span data-ttu-id="38b46-110">これらの違いにより、Windows Api は COM オブジェクトではないため、Windows Api との相互運用性と、プラットフォーム呼び出しまたは PInvoke を使用して .NET Framework が実行されます。</span><span class="sxs-lookup"><span data-stu-id="38b46-110">Because of these differences, and because Windows APIs are not COM objects, interoperability with Windows APIs and the .NET Framework is performed using platform invoke, or PInvoke.</span></span> <span data-ttu-id="38b46-111">プラットフォーム呼び出しは、マネージコードが Dll で実装されているアンマネージ関数を呼び出すことができるようにするサービスです。</span><span class="sxs-lookup"><span data-stu-id="38b46-111">Platform invoke is a service that enables managed code to call unmanaged functions implemented in DLLs.</span></span> <span data-ttu-id="38b46-112">詳細については、「[アンマネージ DLL 関数](../../../framework/interop/consuming-unmanaged-dll-functions.md)の使用」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b46-112">For more information, see [Consuming Unmanaged DLL Functions](../../../framework/interop/consuming-unmanaged-dll-functions.md).</span></span> <span data-ttu-id="38b46-113">Visual Basic で PInvoke を使用するには、 `Declare`ステートメントを使用するか、または空の`DllImport`プロシージャに属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="38b46-113">You can use PInvoke in Visual Basic by using either the `Declare` statement or applying the `DllImport` attribute to an empty procedure.</span></span>  
  
 <span data-ttu-id="38b46-114">Windows API の呼び出しでは、Visual Basic では、以前は、プログラミングの重要な部分をされたが、Visual Basic .NET を使用して必要なことはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="38b46-114">Windows API calls were an important part of Visual Basic programming in the past, but are seldom necessary with Visual Basic .NET.</span></span> <span data-ttu-id="38b46-115">可能な限り、.NET Framework のマネージコードを使用して、Windows API 呼び出しの代わりにタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38b46-115">Whenever possible, you should use managed code from the .NET Framework to perform tasks, instead of Windows API calls.</span></span> <span data-ttu-id="38b46-116">このチュートリアルは、使用する必要のある状況についての情報を提供します。 Windows API が必要です。</span><span class="sxs-lookup"><span data-stu-id="38b46-116">This walkthrough provides information for those situations in which using Windows APIs is necessary.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="api-calls-using-declare"></a><span data-ttu-id="38b46-117">Declare を使用した API 呼び出し</span><span class="sxs-lookup"><span data-stu-id="38b46-117">API Calls Using Declare</span></span>  
 <span data-ttu-id="38b46-118">Windows API を呼び出すための最も一般的な方法を使用して、`Declare`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="38b46-118">The most common way to call Windows APIs is by using the `Declare` statement.</span></span>  
  
### <a name="to-declare-a-dll-procedure"></a><span data-ttu-id="38b46-119">DLL プロシージャを宣言するには</span><span class="sxs-lookup"><span data-stu-id="38b46-119">To declare a DLL procedure</span></span>  
  
1. <span data-ttu-id="38b46-120">呼び出す関数の名前とその引数、引数の型、戻り値を指定し、それを含む DLL の名前と場所を決定します。</span><span class="sxs-lookup"><span data-stu-id="38b46-120">Determine the name of the function you want to call, plus its arguments, argument types, and return value, as well as the name and location of the DLL that contains it.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="38b46-121">Windows API については、プラットフォーム SDK の Windows API で Win32 SDK ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b46-121">For complete information about the Windows APIs, see the Win32 SDK documentation in the Platform SDK Windows API.</span></span> <span data-ttu-id="38b46-122">Windows API を使用する定数の詳細については、Windows.h、Platform SDK に含まれているなどのヘッダー ファイルを調べてください。</span><span class="sxs-lookup"><span data-stu-id="38b46-122">For more information about the constants that Windows APIs use, examine the header files such as Windows.h included with the Platform SDK.</span></span>  
  
2. <span data-ttu-id="38b46-123">**[ファイル]** メニューの **[新規作成]** をクリックし、 **[プロジェクト]** をクリックして、新しい Windows アプリケーションプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="38b46-123">Open a new Windows Application project by clicking **New** on the **File** menu, and then clicking **Project**.</span></span> <span data-ttu-id="38b46-124">**[新しいプロジェクト]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b46-124">The **New Project** dialog box appears.</span></span>  
  
3. <span data-ttu-id="38b46-125">Visual Basic プロジェクトテンプレートの一覧から **[Windows アプリケーション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="38b46-125">Select **Windows Application** from the list of Visual Basic project templates.</span></span> <span data-ttu-id="38b46-126">新しいプロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b46-126">The new project is displayed.</span></span>  
  
4. <span data-ttu-id="38b46-127">DLL を使用`Declare`するクラスまたはモジュールに、次の関数を追加します。</span><span class="sxs-lookup"><span data-stu-id="38b46-127">Add the following `Declare` function either to the class or module in which you want to use the DLL:</span></span>  
  
     [!code-vb[VbVbalrInterop#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#9)]  
  
### <a name="parts-of-the-declare-statement"></a><span data-ttu-id="38b46-128">Declare ステートメントの部分</span><span class="sxs-lookup"><span data-stu-id="38b46-128">Parts of the Declare Statement</span></span>  
 <span data-ttu-id="38b46-129">ステートメント`Declare`には、次の要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="38b46-129">The `Declare` statement includes the following elements.</span></span>  
  
#### <a name="auto-modifier"></a><span data-ttu-id="38b46-130">Auto 修飾子</span><span class="sxs-lookup"><span data-stu-id="38b46-130">Auto modifier</span></span>  
 <span data-ttu-id="38b46-131">修飾子`Auto`は、共通言語ランタイムの規則 (または、指定されている場合はエイリアス名) に従って、メソッド名に基づいて文字列を変換するようにランタイムに指示します。</span><span class="sxs-lookup"><span data-stu-id="38b46-131">The `Auto` modifier instructs the runtime to convert the string based on the method name according to common language runtime rules (or alias name if specified).</span></span>  
  
#### <a name="lib-and-alias-keywords"></a><span data-ttu-id="38b46-132">Lib キーワードと Alias キーワード</span><span class="sxs-lookup"><span data-stu-id="38b46-132">Lib and Alias keywords</span></span>  
 <span data-ttu-id="38b46-133">キーワードに`Function`続く名前は、インポートされた関数にアクセスするためにプログラムが使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="38b46-133">The name following the `Function` keyword is the name your program uses to access the imported function.</span></span> <span data-ttu-id="38b46-134">これは、呼び出す関数の実際の名前と同じにすることも、任意の有効なプロシージャ名を使用してから`Alias`キーワードを使用して、呼び出す関数の実際の名前を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="38b46-134">It can be the same as the real name of the function you are calling, or you can use any valid procedure name and then employ the `Alias` keyword to specify the real name of the function you are calling.</span></span>  
  
 <span data-ttu-id="38b46-135">`Lib`キーワードを指定し、その後に、呼び出し元の関数が含まれている DLL の名前と場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="38b46-135">Specify the `Lib` keyword, followed by the name and location of the DLL that contains the function you are calling.</span></span> <span data-ttu-id="38b46-136">Windows システムディレクトリにあるファイルのパスを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="38b46-136">You do not need to specify the path for files located in the Windows system directories.</span></span>  
  
 <span data-ttu-id="38b46-137">呼び出す関数`Alias`の名前が有効な Visual Basic プロシージャ名ではない場合、またはアプリケーション内の他のアイテムの名前と競合する場合は、キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="38b46-137">Use the `Alias` keyword if the name of the function you are calling is not a valid Visual Basic procedure name, or conflicts with the name of other items in your application.</span></span> <span data-ttu-id="38b46-138">`Alias`呼び出される関数の実際の名前を示します。</span><span class="sxs-lookup"><span data-stu-id="38b46-138">`Alias` indicates the true name of the function being called.</span></span>  
  
#### <a name="argument-and-data-type-declarations"></a><span data-ttu-id="38b46-139">引数とデータ型の宣言</span><span class="sxs-lookup"><span data-stu-id="38b46-139">Argument and Data Type Declarations</span></span>  
 <span data-ttu-id="38b46-140">引数とそのデータ型を宣言します。</span><span class="sxs-lookup"><span data-stu-id="38b46-140">Declare the arguments and their data types.</span></span> <span data-ttu-id="38b46-141">Windows で使用されるデータ型が Visual Studio のデータ型に対応していないため、この部分は困難になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="38b46-141">This part can be challenging because the data types that Windows uses do not correspond to Visual Studio data types.</span></span> <span data-ttu-id="38b46-142">Visual Basic は、引数を互換性のあるデータ型 (*マーシャリング*と呼ばれます) に変換することによって、さまざまな処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="38b46-142">Visual Basic does a lot of the work for you by converting arguments to compatible data types, a process called *marshaling*.</span></span> <span data-ttu-id="38b46-143">名前<xref:System.Runtime.InteropServices>空間で定義されている<xref:System.Runtime.InteropServices.MarshalAsAttribute>属性を使用して、引数のマーシャリング方法を明示的に制御できます。</span><span class="sxs-lookup"><span data-stu-id="38b46-143">You can explicitly control how arguments are marshaled by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute defined in the <xref:System.Runtime.InteropServices> namespace.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="38b46-144">以前のバージョンの Visual Basic では、パラメーター `As Any`を宣言できるようになりました。つまり、任意のデータ型のデータを使用できます。</span><span class="sxs-lookup"><span data-stu-id="38b46-144">Previous versions of Visual Basic allowed you to declare parameters `As Any`, meaning that data of any data type could be used.</span></span> <span data-ttu-id="38b46-145">Visual Basic では、すべて`Declare`のステートメントに特定のデータ型を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38b46-145">Visual Basic requires that you use a specific data type for all `Declare` statements.</span></span>  
  
#### <a name="windows-api-constants"></a><span data-ttu-id="38b46-146">Windows API 定数</span><span class="sxs-lookup"><span data-stu-id="38b46-146">Windows API Constants</span></span>  
 <span data-ttu-id="38b46-147">引数の中には、定数の組み合わせもあります。</span><span class="sxs-lookup"><span data-stu-id="38b46-147">Some arguments are combinations of constants.</span></span> <span data-ttu-id="38b46-148">たとえば、このチュートリアル`MessageBox`で示されている API では、メッセージ`Typ`ボックスの表示方法を制御するという整数の引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="38b46-148">For example, the `MessageBox` API shown in this walkthrough accepts an integer argument called `Typ` that controls how the message box is displayed.</span></span> <span data-ttu-id="38b46-149">これらの定数の数値を確認するには、ファイル`#define`のステートメントを調べます。</span><span class="sxs-lookup"><span data-stu-id="38b46-149">You can determine the numeric value of these constants by examining the `#define` statements in the file WinUser.h.</span></span> <span data-ttu-id="38b46-150">通常、数値は16進数で表示されるので、電卓を使用して追加したり、decimal に変換したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="38b46-150">The numeric values are generally shown in hexadecimal, so you may want to use a calculator to add them and convert to decimal.</span></span> <span data-ttu-id="38b46-151">たとえば、感嘆符`MB_ICONEXCLAMATION` (0x00000030) と Yes/No スタイル`MB_YESNO`の0x00000004 の定数を組み合わせる場合は、数値を加算して、0x00000030 または 52 decimal の結果を取得できます。</span><span class="sxs-lookup"><span data-stu-id="38b46-151">For example, if you want to combine the constants for the exclamation style `MB_ICONEXCLAMATION` 0x00000030 and the Yes/No style `MB_YESNO` 0x00000004, you can add the numbers and get a result of 0x00000034, or 52 decimal.</span></span> <span data-ttu-id="38b46-152">10進数の結果を直接使用することもできますが、これらの値を定数としてアプリケーションで宣言し`Or` 、演算子を使用して組み合わせることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="38b46-152">Although you can use the decimal result directly, it is better to declare these values as constants in your application and combine them using the `Or` operator.</span></span>  
  
##### <a name="to-declare-constants-for-windows-api-calls"></a><span data-ttu-id="38b46-153">Windows API 呼び出しの定数を宣言するには</span><span class="sxs-lookup"><span data-stu-id="38b46-153">To declare constants for Windows API calls</span></span>  
  
1. <span data-ttu-id="38b46-154">呼び出している Windows 関数のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b46-154">Consult the documentation for the Windows function you are calling.</span></span> <span data-ttu-id="38b46-155">使用する定数の名前と、これらの定数の数値が含まれている .h ファイルの名前を確認します。</span><span class="sxs-lookup"><span data-stu-id="38b46-155">Determine the name of the constants it uses and the name of the .h file that contains the numeric values for these constants.</span></span>  
  
2. <span data-ttu-id="38b46-156">メモ帳などのテキストエディターを使用してヘッダー (.h) ファイルの内容を表示し、使用している定数に関連付けられている値を検索します。</span><span class="sxs-lookup"><span data-stu-id="38b46-156">Use a text editor, such as Notepad, to view the contents of the header (.h) file, and find the values associated with the constants you are using.</span></span> <span data-ttu-id="38b46-157">たとえば、API は`MessageBox`定数`MB_ICONQUESTION`を使用して、メッセージボックスに疑問符を表示します。</span><span class="sxs-lookup"><span data-stu-id="38b46-157">For example, the `MessageBox` API uses the constant `MB_ICONQUESTION` to show a question mark in the message box.</span></span> <span data-ttu-id="38b46-158">の定義は`MB_ICONQUESTION` winuser. h にあり、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b46-158">The definition for `MB_ICONQUESTION` is in WinUser.h and appears as follows:</span></span>  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3. <span data-ttu-id="38b46-159">これらの`Const`定数をアプリケーションで使用できるようにするには、同等のステートメントをクラスまたはモジュールに追加します。</span><span class="sxs-lookup"><span data-stu-id="38b46-159">Add equivalent `Const` statements to your class or module to make these constants available to your application.</span></span> <span data-ttu-id="38b46-160">例:</span><span class="sxs-lookup"><span data-stu-id="38b46-160">For example:</span></span>  
  
     [!code-vb[VbVbalrInterop#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#11)]  
  
###### <a name="to-call-the-dll-procedure"></a><span data-ttu-id="38b46-161">DLL プロシージャを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="38b46-161">To call the DLL procedure</span></span>  
  
1. <span data-ttu-id="38b46-162">という名前`Button1`のボタンをプロジェクトのスタートアップフォームに追加し、それをダブルクリックしてコードを表示します。</span><span class="sxs-lookup"><span data-stu-id="38b46-162">Add a button named `Button1` to the startup form for your project, and then double-click it to view its code.</span></span> <span data-ttu-id="38b46-163">ボタンのイベントハンドラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b46-163">The event handler for the button is displayed.</span></span>  
  
2. <span data-ttu-id="38b46-164">追加したボタン`Click`のイベントハンドラーにコードを追加して、プロシージャを呼び出し、適切な引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="38b46-164">Add code to the `Click` event handler for the button you added, to call the procedure and provide the appropriate arguments:</span></span>  
  
     [!code-vb[VbVbalrInterop#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#12)]  
  
3. <span data-ttu-id="38b46-165">F5 キーを押してプロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="38b46-165">Run the project by pressing F5.</span></span> <span data-ttu-id="38b46-166">メッセージボックスには、 **[はい] と [** **いいえ**] の両方のボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b46-166">The message box is displayed with both **Yes** and **No** response buttons.</span></span> <span data-ttu-id="38b46-167">いずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="38b46-167">Click either one.</span></span>  
  
#### <a name="data-marshaling"></a><span data-ttu-id="38b46-168">データのマーシャリング</span><span class="sxs-lookup"><span data-stu-id="38b46-168">Data Marshaling</span></span>  
 <span data-ttu-id="38b46-169">Visual Basic は、Windows API 呼び出しのパラメーターと戻り値のデータ型を自動的に変換しますが`MarshalAs` 、属性を使用して、api が期待するアンマネージデータ型を明示的に指定することができます。</span><span class="sxs-lookup"><span data-stu-id="38b46-169">Visual Basic automatically converts the data types of parameters and return values for Windows API calls, but you can use the `MarshalAs` attribute to explicitly specify unmanaged data types that an API expects.</span></span> <span data-ttu-id="38b46-170">相互運用マーシャリングの詳細については、「[相互運用マーシャリング](../../../framework/interop/interop-marshaling.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b46-170">For more information about interop marshaling, see [Interop Marshaling](../../../framework/interop/interop-marshaling.md).</span></span>  
  
##### <a name="to-use-declare-and-marshalas-in-an-api-call"></a><span data-ttu-id="38b46-171">API 呼び出しで Declare と MarshalAs を使用するには</span><span class="sxs-lookup"><span data-stu-id="38b46-171">To use Declare and MarshalAs in an API call</span></span>  
  
1. <span data-ttu-id="38b46-172">呼び出す関数の名前とその引数、データ型、および戻り値を決定します。</span><span class="sxs-lookup"><span data-stu-id="38b46-172">Determine the name of the function you want to call, plus its arguments, data types, and return value.</span></span>  
  
2. <span data-ttu-id="38b46-173">`MarshalAs`属性へのアクセスを簡単にするに`Imports`は、次の例に示すように、クラスまたはモジュールのコードの先頭にステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="38b46-173">To simplify access to the `MarshalAs` attribute, add an `Imports` statement to the top of the code for the class or module, as in the following example:</span></span>  
  
     [!code-vb[VbVbalrInterop#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#13)]  
  
3. <span data-ttu-id="38b46-174">インポートされた関数の関数プロトタイプを使用しているクラスまたはモジュールに追加し`MarshalAs` 、属性をパラメーターまたは戻り値に適用します。</span><span class="sxs-lookup"><span data-stu-id="38b46-174">Add a function prototype for the imported function to the class or module you are using, and apply the `MarshalAs` attribute to the parameters or return value.</span></span> <span data-ttu-id="38b46-175">次の例では、型`void*`を想定する API 呼び出しは、次のよう`AsAny`にマーシャリングされます。</span><span class="sxs-lookup"><span data-stu-id="38b46-175">In the following example, an API call that expects the type `void*` is marshaled as `AsAny`:</span></span>  
  
     [!code-vb[VbVbalrInterop#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#14)]  
  
## <a name="api-calls-using-dllimport"></a><span data-ttu-id="38b46-176">DllImport を使用した API 呼び出し</span><span class="sxs-lookup"><span data-stu-id="38b46-176">API Calls Using DllImport</span></span>  
 <span data-ttu-id="38b46-177">属性`DllImport`は、タイプライブラリを使用せずに dll 内の関数を呼び出すための2番目の方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="38b46-177">The `DllImport` attribute provides a second way to call functions in DLLs without type libraries.</span></span> <span data-ttu-id="38b46-178">`DllImport`は`Declare`ステートメントを使用することとほぼ同じですが、関数の呼び出し方法をより詳細に制御できます。</span><span class="sxs-lookup"><span data-stu-id="38b46-178">`DllImport` is roughly equivalent to using a `Declare` statement but provides more control over how functions are called.</span></span>  
  
 <span data-ttu-id="38b46-179">呼び出しが共有`DllImport` (*静的*メソッドと呼ばれることもあります) メソッドを参照している限り、ほとんどの Windows API 呼び出しでを使用できます。</span><span class="sxs-lookup"><span data-stu-id="38b46-179">You can use `DllImport` with most Windows API calls as long as the call refers to a shared (sometimes called *static*) method.</span></span> <span data-ttu-id="38b46-180">クラスのインスタンスを必要とするメソッドは使用できません。</span><span class="sxs-lookup"><span data-stu-id="38b46-180">You cannot use methods that require an instance of a class.</span></span> <span data-ttu-id="38b46-181">ステートメント`Declare`とは`DllImport`異なり、呼び出しで`MarshalAs`は属性を使用できません。</span><span class="sxs-lookup"><span data-stu-id="38b46-181">Unlike `Declare` statements, `DllImport` calls cannot use the `MarshalAs` attribute.</span></span>  
  
### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a><span data-ttu-id="38b46-182">DllImport 属性を使用して Windows API を呼び出すには</span><span class="sxs-lookup"><span data-stu-id="38b46-182">To call a Windows API using the DllImport attribute</span></span>  
  
1. <span data-ttu-id="38b46-183">**[ファイル]** メニューの **[新規作成]** をクリックし、 **[プロジェクト]** をクリックして、新しい Windows アプリケーションプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="38b46-183">Open a new Windows Application project by clicking **New** on the **File** menu, and then clicking **Project**.</span></span> <span data-ttu-id="38b46-184">**[新しいプロジェクト]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b46-184">The **New Project** dialog box appears.</span></span>  
  
2. <span data-ttu-id="38b46-185">Visual Basic プロジェクトテンプレートの一覧から **[Windows アプリケーション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="38b46-185">Select **Windows Application** from the list of Visual Basic project templates.</span></span> <span data-ttu-id="38b46-186">新しいプロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b46-186">The new project is displayed.</span></span>  
  
3. <span data-ttu-id="38b46-187">という名前`Button2`のボタンをスタートアップフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="38b46-187">Add a button named `Button2` to the startup form.</span></span>  
  
4. <span data-ttu-id="38b46-188">をダブルクリック`Button2`して、フォームのコードビューを開きます。</span><span class="sxs-lookup"><span data-stu-id="38b46-188">Double-click `Button2` to open the code view for the form.</span></span>  
  
5. <span data-ttu-id="38b46-189">へ`DllImport`のアクセスを簡単にする`Imports`には、スタートアップフォームクラスのコードの先頭にステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="38b46-189">To simplify access to `DllImport`, add an `Imports` statement to the top of the code for the startup form class:</span></span>  
  
     [!code-vb[VbVbalrInterop#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#13)]  
  
6. <span data-ttu-id="38b46-190">フォームのステートメントの`End Class`前に空の関数を宣言し、関数`MoveFile`にという名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="38b46-190">Declare an empty function preceding the `End Class` statement for the form, and name the function `MoveFile`.</span></span>  
  
7. <span data-ttu-id="38b46-191">関数宣言に`Shared` `MoveFile`および修飾子を適用し、Windows API 関数が使用する引数に基づいてのパラメーターを設定します。 `Public`</span><span class="sxs-lookup"><span data-stu-id="38b46-191">Apply the `Public` and `Shared` modifiers to the function declaration and set parameters for `MoveFile` based on the arguments the Windows API function uses:</span></span>  
  
     [!code-vb[VbVbalrInterop#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#16)]  
  
     <span data-ttu-id="38b46-192">関数は、任意の有効なプロシージャ名を持つことができます。属性`DllImport`は、DLL 内の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="38b46-192">Your function can have any valid procedure name; the `DllImport` attribute specifies the name in the DLL.</span></span> <span data-ttu-id="38b46-193">また、パラメーターと戻り値の相互運用性マーシャリングも処理するため、API で使用されるデータ型に似た Visual Studio データ型を選択できます。</span><span class="sxs-lookup"><span data-stu-id="38b46-193">It also handles interoperability marshaling for the parameters and return values, so you can choose Visual Studio data types that are similar to the data types the API uses.</span></span>  
  
8. <span data-ttu-id="38b46-194">空の関数に属性を適用します。`DllImport`</span><span class="sxs-lookup"><span data-stu-id="38b46-194">Apply the `DllImport` attribute to the empty function.</span></span> <span data-ttu-id="38b46-195">最初のパラメーターは、呼び出し元の関数を含む DLL の名前と場所です。</span><span class="sxs-lookup"><span data-stu-id="38b46-195">The first parameter is the name and location of the DLL containing the function you are calling.</span></span> <span data-ttu-id="38b46-196">Windows システムディレクトリにあるファイルのパスを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="38b46-196">You do not need to specify the path for files located in the Windows system directories.</span></span> <span data-ttu-id="38b46-197">2番目のパラメーターは、Windows API で関数の名前を指定する名前付き引数です。</span><span class="sxs-lookup"><span data-stu-id="38b46-197">The second parameter is a named argument that specifies the name of the function in the Windows API.</span></span> <span data-ttu-id="38b46-198">この例では、 `DllImport`属性によって`MoveFile`の呼び出しが kernel32.dll `MoveFileW`内のに強制的に転送されます。DLL.</span><span class="sxs-lookup"><span data-stu-id="38b46-198">In this example, the `DllImport` attribute forces calls to `MoveFile` to be forwarded to `MoveFileW` in KERNEL32.DLL.</span></span> <span data-ttu-id="38b46-199">メソッド`MoveFileW`は、パスから`src`パス`dst`にファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="38b46-199">The `MoveFileW` method copies a file from the path `src` to the path `dst`.</span></span>  
  
     [!code-vb[VbVbalrInterop#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#17)]  
  
9. <span data-ttu-id="38b46-200">関数を呼び出すコード`Button2_Click`をイベントハンドラーに追加します。</span><span class="sxs-lookup"><span data-stu-id="38b46-200">Add code to the `Button2_Click` event handler to call the function:</span></span>  
  
     [!code-vb[VbVbalrInterop#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#18)]  
  
10. <span data-ttu-id="38b46-201">Test.txt という名前のファイルを作成し、ハードドライブの C:\ Tmp ディレクトリに配置します。</span><span class="sxs-lookup"><span data-stu-id="38b46-201">Create a file named Test.txt and place it in the C:\Tmp directory on your hard drive.</span></span> <span data-ttu-id="38b46-202">必要に応じて、Tmp ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="38b46-202">Create the Tmp directory if necessary.</span></span>  
  
11. <span data-ttu-id="38b46-203">F5 キーを押してアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="38b46-203">Press F5 to start the application.</span></span> <span data-ttu-id="38b46-204">メインフォームが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b46-204">The main form appears.</span></span>  
  
12. <span data-ttu-id="38b46-205">**[Button2]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38b46-205">Click **Button2**.</span></span> <span data-ttu-id="38b46-206">ファイルを移動できる場合、"ファイルは正常に移動されました" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38b46-206">The message "The file was moved successfully" is displayed if the file can be moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38b46-207">関連項目</span><span class="sxs-lookup"><span data-stu-id="38b46-207">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="38b46-208">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="38b46-208">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="38b46-209">Auto</span><span class="sxs-lookup"><span data-stu-id="38b46-209">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)
- [<span data-ttu-id="38b46-210">Alias</span><span class="sxs-lookup"><span data-stu-id="38b46-210">Alias</span></span>](../../../visual-basic/language-reference/statements/alias-clause.md)
- [<span data-ttu-id="38b46-211">COM 相互運用</span><span class="sxs-lookup"><span data-stu-id="38b46-211">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
- [<span data-ttu-id="38b46-212">マネージド コードでのプロトタイプの作成</span><span class="sxs-lookup"><span data-stu-id="38b46-212">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="38b46-213">コールバック メソッドとしてのデリゲートのマーシャ リング</span><span class="sxs-lookup"><span data-stu-id="38b46-213">Marshaling a Delegate as a Callback Method</span></span>](../../../framework/interop/marshaling-a-delegate-as-a-callback-method.md)
