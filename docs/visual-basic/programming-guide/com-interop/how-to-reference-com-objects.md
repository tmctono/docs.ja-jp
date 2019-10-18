---
title: '方法 : Visual Basic から COM オブジェクトを参照する'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
ms.openlocfilehash: ea0e1d9b0ae9f151d901c425512508ba7bc05343
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524363"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a><span data-ttu-id="ad025-102">方法 : Visual Basic から COM オブジェクトを参照する</span><span class="sxs-lookup"><span data-stu-id="ad025-102">How to: Reference COM Objects from Visual Basic</span></span>
<span data-ttu-id="ad025-103">Visual Basic では、タイプライブラリを持つ COM オブジェクトへの参照を追加するには、COM ライブラリ用の相互運用機能アセンブリを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad025-103">In Visual Basic, adding references to COM objects that have type libraries requires the creation of an interop assembly for the COM library.</span></span> <span data-ttu-id="ad025-104">COM オブジェクトのメンバーへの参照は相互運用機能アセンブリにルーティングされ、実際の COM オブジェクトに転送されます。</span><span class="sxs-lookup"><span data-stu-id="ad025-104">References to the members of the COM object are routed to the interop assembly and then forwarded to the actual COM object.</span></span> <span data-ttu-id="ad025-105">COM オブジェクトからの応答は相互運用機能アセンブリにルーティングされ、.NET Framework アプリケーションに転送されます。</span><span class="sxs-lookup"><span data-stu-id="ad025-105">Responses from the COM object are routed to the interop assembly and forwarded to your .NET Framework application.</span></span>  
  
 <span data-ttu-id="ad025-106">.NET アセンブリに COM オブジェクトの型情報を埋め込むことによって、相互運用機能アセンブリを使用せずに COM オブジェクトを参照できます。</span><span class="sxs-lookup"><span data-stu-id="ad025-106">You can reference a COM object without using an interop assembly by embedding the type information for the COM object in a .NET assembly.</span></span> <span data-ttu-id="ad025-107">型情報を埋め込むには、COM オブジェクトへの参照の `Embed Interop Types` プロパティを `True` に設定します。</span><span class="sxs-lookup"><span data-stu-id="ad025-107">To embed type information, set the `Embed Interop Types` property to `True` for the reference to the COM object.</span></span> <span data-ttu-id="ad025-108">コマンドラインコンパイラを使用してコンパイルする場合は、`/link` オプションを使用して COM ライブラリを参照します。</span><span class="sxs-lookup"><span data-stu-id="ad025-108">If you are compiling by using the command-line compiler, use the `/link` option to reference the COM library.</span></span> <span data-ttu-id="ad025-109">詳細については、「 [-link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad025-109">For more information, see [-link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span></span>  
  
 <span data-ttu-id="ad025-110">統合開発環境 (IDE: integrated development environment) からタイプライブラリへの参照を追加すると、Visual Basic によって相互運用機能アセンブリが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="ad025-110">Visual Basic automatically creates interop assemblies when you add a reference to a type library from the integrated development environment (IDE).</span></span> <span data-ttu-id="ad025-111">コマンドラインから作業する場合は、Tlbimp ユーティリティを使用して、相互運用機能アセンブリを手動で作成できます。</span><span class="sxs-lookup"><span data-stu-id="ad025-111">When working from the command line, you can use the Tlbimp utility to manually create interop assemblies.</span></span>  
  
### <a name="to-add-references-to-com-objects"></a><span data-ttu-id="ad025-112">COM オブジェクトへの参照を追加するには</span><span class="sxs-lookup"><span data-stu-id="ad025-112">To add references to COM objects</span></span>  
  
1. <span data-ttu-id="ad025-113">**[プロジェクト]** メニューの **[参照の追加]** をクリックし、ダイアログボックスの **[COM]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad025-113">On the **Project** menu, choose **Add Reference** and then click the **COM** tab in the dialog box.</span></span>  
  
2. <span data-ttu-id="ad025-114">COM オブジェクトの一覧から、使用するコンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="ad025-114">Select the component you want to use from the list of COM objects.</span></span>  
  
3. <span data-ttu-id="ad025-115">相互運用機能アセンブリへのアクセスを簡単にするには、COM オブジェクトを使用するクラスまたはモジュールの先頭に `Imports` ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="ad025-115">To simplify access to the interop assembly, add an `Imports` statement to the top of the class or module in which you will use the COM object.</span></span> <span data-ttu-id="ad025-116">たとえば、次のコード例では、`Microsoft InkEdit Control 1.0` ライブラリで参照されるオブジェクトの `INKEDLib` 名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="ad025-116">For example, the following code example imports the namespace `INKEDLib` for objects referenced in the `Microsoft InkEdit Control 1.0` library.</span></span>  
  
     [!code-vb[VbVbalrInterop#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#40)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a><span data-ttu-id="ad025-117">Tlbimp を使用して相互運用機能アセンブリを作成するには</span><span class="sxs-lookup"><span data-stu-id="ad025-117">To create an interop assembly using Tlbimp</span></span>  
  
1. <span data-ttu-id="ad025-118">まだ検索パスに含まれておらず、現在のディレクトリに存在しない場合は、Tlbimp の場所を検索パスに追加します。</span><span class="sxs-lookup"><span data-stu-id="ad025-118">Add the location of Tlbimp to the search path, if it is not already part of the search path and you are not currently in the directory where it is located.</span></span>  
  
2. <span data-ttu-id="ad025-119">コマンドプロンプトから Tlbimp を呼び出し、次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="ad025-119">Call Tlbimp from a command prompt, providing the following information:</span></span>  
  
    - <span data-ttu-id="ad025-120">タイプライブラリを含む DLL の名前と場所</span><span class="sxs-lookup"><span data-stu-id="ad025-120">Name and location of the DLL that contains the type library</span></span>  
  
    - <span data-ttu-id="ad025-121">情報を配置する名前空間の名前と場所</span><span class="sxs-lookup"><span data-stu-id="ad025-121">Name and location of the namespace where the information should be placed</span></span>  
  
    - <span data-ttu-id="ad025-122">ターゲット相互運用機能アセンブリの名前と場所</span><span class="sxs-lookup"><span data-stu-id="ad025-122">Name and location of the target interop assembly</span></span>  
  
     <span data-ttu-id="ad025-123">次にコード例を示します。</span><span class="sxs-lookup"><span data-stu-id="ad025-123">The following code provides an example:</span></span>  
  
    ```console  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     <span data-ttu-id="ad025-124">Tlbimp.exe を使用して、登録されていない COM オブジェクトに対しても、タイプライブラリの相互運用機能アセンブリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ad025-124">You can use Tlbimp to create interop assemblies for type libraries, even for unregistered COM objects.</span></span> <span data-ttu-id="ad025-125">ただし、相互運用機能アセンブリによって参照される COM オブジェクトは、それらが使用されるコンピューターに適切に登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad025-125">However, the COM objects referred to by interop assemblies must be properly registered on the computer where they are to be used.</span></span> <span data-ttu-id="ad025-126">Windows オペレーティングシステムに含まれている Regsvr32 ユーティリティを使用して、COM オブジェクトを登録できます。</span><span class="sxs-lookup"><span data-stu-id="ad025-126">You can register a COM object by using the Regsvr32 utility included with the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad025-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad025-127">See also</span></span>

- [<span data-ttu-id="ad025-128">COM 相互運用</span><span class="sxs-lookup"><span data-stu-id="ad025-128">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
- [<span data-ttu-id="ad025-129">Tlbimp.exe (タイプ ライブラリ インポーター)</span><span class="sxs-lookup"><span data-stu-id="ad025-129">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [<span data-ttu-id="ad025-130">Tlbexp.exe (タイプ ライブラリ エクスポーター)</span><span class="sxs-lookup"><span data-stu-id="ad025-130">Tlbexp.exe (Type Library Exporter)</span></span>](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [<span data-ttu-id="ad025-131">チュートリアル : COM オブジェクトによる継承の実装</span><span class="sxs-lookup"><span data-stu-id="ad025-131">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [<span data-ttu-id="ad025-132">相互運用性のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ad025-132">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
- [<span data-ttu-id="ad025-133">Imports ステートメント (.NET 名前空間および型)</span><span class="sxs-lookup"><span data-stu-id="ad025-133">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
