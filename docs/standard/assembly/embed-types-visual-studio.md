---
title: 'チュートリアル: Visual Studio でマネージド アセンブリからの型を埋め込む'
description: このチュートリアルでは、Visual Studio を使用して .NET のマネージド アセンブリからの型を埋め込む方法について説明します。 埋め込まれる型では、バージョンへの非依存がサポートされます。
ms.date: 08/19/2019
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
dev_langs:
- csharp
- vb
ms.openlocfilehash: 636e5f8095b64cd0f445555c96d00945ccf7eaf8
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378981"
---
# <a name="walkthrough-embed-types-from-managed-assemblies-in-visual-studio"></a><span data-ttu-id="e82d7-104">チュートリアル: Visual Studio でマネージド アセンブリからの型を埋め込む</span><span class="sxs-lookup"><span data-stu-id="e82d7-104">Walkthrough: Embed types from managed assemblies in Visual Studio</span></span>

<span data-ttu-id="e82d7-105">厳密な名前を持つマネージド アセンブリから型情報を埋め込むと、アプリケーション内で型を疎結合して、バージョンに依存しないプログラムを実現できます。</span><span class="sxs-lookup"><span data-stu-id="e82d7-105">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="e82d7-106">つまり、任意のバージョンのマネージド ライブラリの型を使用してプログラムを記述でき、新しいバージョンごとに再コンパイルする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e82d7-106">That is, your program can be written to use types from any version of a managed library without having to be recompiled for each new version.</span></span>

<span data-ttu-id="e82d7-107">型の埋め込みは、COM 相互運用と共によく使用されます (Microsoft Office からのオートメーション オブジェクトを使用するアプリケーションなど)。</span><span class="sxs-lookup"><span data-stu-id="e82d7-107">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="e82d7-108">型情報を埋め込むと、同じビルドのプログラムを、別のコンピューター上にある別バージョンの Microsoft Office と連携させることができます。</span><span class="sxs-lookup"><span data-stu-id="e82d7-108">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="e82d7-109">ただし、フル マネージド ソリューションで型の埋め込みを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e82d7-109">However, you can also use type embedding with fully managed solutions.</span></span>

<span data-ttu-id="e82d7-110">埋め込み可能なパブリック インターフェイスを指定した後、それらのインターフェイスを実装するランタイム クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-110">After you specify the public interfaces that can be embedded, you create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="e82d7-111">クライアント プログラムでは、パブリック インターフェイスが含まれるアセンブリを参照し、参照の `Embed Interop Types` プロパティを `True` に設定することで、設計時にインターフェイスの型情報を埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="e82d7-111">A client program can embed the type information for the interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="e82d7-112">クライアント プログラムでは、その後、それらのインターフェイスとして型指定されたランタイム オブジェクトのインスタンスを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="e82d7-112">The client program can then load instances of the runtime objects typed as those interfaces.</span></span> <span data-ttu-id="e82d7-113">これは、コマンド ライン コンパイラを使用し、[-link コンパイラ オプション](../../csharp/language-reference/compiler-options/link-compiler-option.md)を使用してアセンブリを参照することに相当します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-113">This is equivalent to using the command line compiler and referencing the assembly by using the [-link compiler option](../../csharp/language-reference/compiler-options/link-compiler-option.md).</span></span>

<span data-ttu-id="e82d7-114">厳密な名前を持つランタイム アセンブリの新バージョンを作成した場合でも、クライアント プログラムを再コンパイルする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e82d7-114">If you create a new version of your strong-named runtime assembly, the client program doesn't have to be recompiled.</span></span> <span data-ttu-id="e82d7-115">クライアント プログラムでは、パブリック インターフェイスの埋め込まれた型情報を使用して、利用可能などのバージョンでも引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="e82d7-115">The client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>

<span data-ttu-id="e82d7-116">このチュートリアルでは、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="e82d7-116">In this walkthrough, you:</span></span>

1. <span data-ttu-id="e82d7-117">埋め込み可能な型情報が含まれるパブリック インターフェイスを使用して、厳密な名前を持つアセンブリを作成する。</span><span class="sxs-lookup"><span data-stu-id="e82d7-117">Create a strong-named assembly with a public interface containing type information that can be embedded.</span></span>
1. <span data-ttu-id="e82d7-118">そのパブリック インターフェイスを実装する、厳密な名前のランタイム アセンブリを作成する。</span><span class="sxs-lookup"><span data-stu-id="e82d7-118">Create a strong-named runtime assembly that implements the public interface.</span></span>
1. <span data-ttu-id="e82d7-119">パブリック インターフェイスから型情報を埋め込み、ランタイム アセンブリからクラスのインスタンスを作成する、クライアント プログラムを作成する。</span><span class="sxs-lookup"><span data-stu-id="e82d7-119">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>
1. <span data-ttu-id="e82d7-120">ランタイム アセンブリを変更し、リビルドする。</span><span class="sxs-lookup"><span data-stu-id="e82d7-120">Modify and rebuild the runtime assembly.</span></span>
1. <span data-ttu-id="e82d7-121">クライアント プログラムを実行し、クライアント プログラムを再コンパイルしなくても、新バージョンのランタイム アセンブリが使用されることを確認する。</span><span class="sxs-lookup"><span data-stu-id="e82d7-121">Run the client program to see that it uses the new version of the runtime assembly without having to be recompiled.</span></span>

[!INCLUDE[note_settings_general](../../../includes/note-settings-general-md.md)]

## <a name="conditions-and-limitations"></a><span data-ttu-id="e82d7-122">条件と制限</span><span class="sxs-lookup"><span data-stu-id="e82d7-122">Conditions and limitations</span></span>

<span data-ttu-id="e82d7-123">次の条件が満たされていると、アセンブリから型情報を埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="e82d7-123">You can embed type information from an assembly under the following conditions:</span></span>

- <span data-ttu-id="e82d7-124">アセンブリが、少なくとも 1 つのパブリック インターフェイスを公開している。</span><span class="sxs-lookup"><span data-stu-id="e82d7-124">The assembly exposes at least one public interface.</span></span>
- <span data-ttu-id="e82d7-125">埋め込みインターフェイスに、`ComImport` 属性および一意の GUID の `Guid` 属性で注釈が付けられている。</span><span class="sxs-lookup"><span data-stu-id="e82d7-125">The embedded interfaces are annotated with `ComImport` attributes and `Guid` attributes with unique GUIDs.</span></span>
- <span data-ttu-id="e82d7-126">アセンブリに、`ImportedFromTypeLib` 属性または `PrimaryInteropAssembly` 属性、およびアセンブリ レベルの `Guid` 属性が付けられている。</span><span class="sxs-lookup"><span data-stu-id="e82d7-126">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="e82d7-127">既定では、Visual C# と Visual Basic のプロジェクト テンプレートには、アセンブリ レベルの `Guid` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e82d7-127">The Visual C# and Visual Basic project templates include an assembly-level `Guid` attribute by default.</span></span>

<span data-ttu-id="e82d7-128">型の埋め込みの主な機能は、COM 相互運用アセンブリをサポートすることなので、フル マネージドのソリューションに型情報を埋め込む場合は、次の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e82d7-128">Because the primary function of type embedding is to support COM interop assemblies, the following limitations apply when you embed type information in a fully-managed solution:</span></span>

- <span data-ttu-id="e82d7-129">COM 相互運用に固有の属性のみが埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="e82d7-129">Only attributes specific to COM interop are embedded.</span></span> <span data-ttu-id="e82d7-130">他の属性は無視されます。</span><span class="sxs-lookup"><span data-stu-id="e82d7-130">Other attributes are ignored.</span></span>
- <span data-ttu-id="e82d7-131">型でジェネリック パラメーターが使用されていて、ジェネリック パラメーターの型が埋め込まれる型である場合、その型をアセンブリの境界を越えて使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e82d7-131">If a type uses generic parameters, and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="e82d7-132">アセンブリの境界を越える場合の例としては、別のアセンブリからメソッドを呼び出す場合や、別のアセンブリで定義されている型から型を派生させる場合です。</span><span class="sxs-lookup"><span data-stu-id="e82d7-132">Examples of crossing an assembly boundary include calling a method from another assembly or deriving a type from a type defined in another assembly.</span></span>
- <span data-ttu-id="e82d7-133">定数は埋め込まれません。</span><span class="sxs-lookup"><span data-stu-id="e82d7-133">Constants are not embedded.</span></span>
- <span data-ttu-id="e82d7-134"><xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> クラスでは、埋め込み型をキーとして利用できません。</span><span class="sxs-lookup"><span data-stu-id="e82d7-134">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> class does not support an embedded type as a key.</span></span> <span data-ttu-id="e82d7-135">埋め込み型をキーとしてサポートするために、独自のディクショナリ型を実装することは可能です。</span><span class="sxs-lookup"><span data-stu-id="e82d7-135">You can implement your own dictionary type to support an embedded type as a key.</span></span>

## <a name="create-an-interface"></a><span data-ttu-id="e82d7-136">インターフェイスの作成</span><span class="sxs-lookup"><span data-stu-id="e82d7-136">Create an interface</span></span>

<span data-ttu-id="e82d7-137">最初のステップは、型等価性インターフェイス プロジェクトを作成することです。</span><span class="sxs-lookup"><span data-stu-id="e82d7-137">The first step is to create the type equivalence interface assembly.</span></span>

1. <span data-ttu-id="e82d7-138">Visual Studio で、 **[ファイル]**  >  **[新規作成]**  >  **[プロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-138">In Visual Studio, select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="e82d7-139">**[新しいプロジェクトの作成]** ダイアログ ボックスで、 **[Search for templates]\(テンプレートの検索\)** ボックスに「*クラス ライブラリ*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-139">In the **Create a new project** dialog box, type *class library* in the **Search for templates** box.</span></span> <span data-ttu-id="e82d7-140">一覧から C# または Visual Basic の**クラス ライブラリ (.NET Framework)** テンプレートを選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-140">Select either the C# or Visual Basic **Class Library (.NET Framework)** template from the list, and then select **Next**.</span></span>

1. <span data-ttu-id="e82d7-141">**[新しいプロジェクトの構成]** ダイアログ ボックスの **[プロジェクト名]** に「*TypeEquivalenceInterface*」と入力し、 **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-141">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceInterface*, and then select **Create**.</span></span> <span data-ttu-id="e82d7-142">新しいプロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e82d7-142">The new project is created.</span></span>

1. <span data-ttu-id="e82d7-143">**ソリューション エクスプローラー**で、*Class1.cs* ファイルまたは *Class1.vb* ファイルを右クリックし、 **[名前の変更]** を選択して、ファイル名を *Class1* から *ISampleInterface* に変更します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-143">In **Solution Explorer**, right-click the *Class1.cs* or *Class1.vb* file, select **Rename**, and rename the file from *Class1* to *ISampleInterface*.</span></span> <span data-ttu-id="e82d7-144">クラスの名前も `ISampleInterface` 変更するかどうかを確認を求めるメッセージが表示されたら、 **[はい]** と応答します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-144">Respond **Yes** to the prompt to also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="e82d7-145">このクラスは、クラスのパブリック インターフェイスを表します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-145">This class represents the public interface for the class.</span></span>

1. <span data-ttu-id="e82d7-146">**ソリューション エクスプローラー**で **TypeEquivalenceInterface** プロジェクトを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-146">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project, and then select **Properties**.</span></span>

1. <span data-ttu-id="e82d7-147">**[プロパティ]** 画面の左側のウィンドウで **[ビルド]** を選択し、 **[出力パス]** をお使いのコンピューター上の場所 (*C:\TypeEquivalenceSample* など) に設定します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-147">Select **Build** on the left pane of the **Properties** screen, and set the **Output path** to a location on your computer, such as *C:\TypeEquivalenceSample*.</span></span> <span data-ttu-id="e82d7-148">このチュートリアル全体で同じ場所を使用します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-148">You use the same location throughout this walkthrough.</span></span>

1. <span data-ttu-id="e82d7-149">**[プロパティ]** 画面の左側のウィンドウで **[署名]** を選択し、 **[アセンブリに署名する]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e82d7-149">Select **Signing** on the left pane of the **Properties** screen, and then select the **Sign the assembly** check box.</span></span> <span data-ttu-id="e82d7-150">**[厳密な名前のキー ファイルを選択してください]** のドロップダウンで、 **[新規作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-150">In the dropdown for **Choose a strong name key file**, select **New**.</span></span>

1. <span data-ttu-id="e82d7-151">**[厳密な名前キーの作成]** ダイアログで、 **[キー ファイル名]** に「*key.snk*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-151">In the **Create Strong Name Key** dialog, under **Key file name**, type *key.snk*.</span></span> <span data-ttu-id="e82d7-152">**[キーファイルをパスワードで保護する]** チェック ボックスをオフにし、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-152">Deselect the **Protect my key file with a password** check box, and then select **OK**.</span></span>

1. <span data-ttu-id="e82d7-153">コード エディターで *ISampleInterface* クラス ファイルを開き、その内容を次のコードに置き換えて、`ISampleInterface` インターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-153">Open the *ISampleInterface* class file in the code editor, and replace its contents with the following code to create the `ISampleInterface` interface:</span></span>

   ```csharp
   using System;
   using System.Runtime.InteropServices;

   namespace TypeEquivalenceInterface
   {
       [ComImport]
       [Guid("8DA56996-A151-4136-B474-32784559F6DF")]
       public interface ISampleInterface
       {
           void GetUserInput();
           string UserInput { get; }
       }
   }
   ```

   ```vb
   Imports System.Runtime.InteropServices

   <ComImport()>
   <Guid("8DA56996-A151-4136-B474-32784559F6DF")>
   Public Interface ISampleInterface
       Sub GetUserInput()
       ReadOnly Property UserInput As String
   End Interface
   ```

1. <span data-ttu-id="e82d7-154">**[ツール]** メニューの **[GUID の作成]** を選択し、 **[GUID の作成]** ダイアログ ボックスで **[レジストリ形式]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-154">On the **Tools** menu, select **Create Guid**, and in the **Create GUID** dialog box, select **Registry Format**.</span></span> <span data-ttu-id="e82d7-155">**[コピー]** を選択し、 **[終了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-155">Select **Copy**, and then select **Exit**.</span></span>

1. <span data-ttu-id="e82d7-156">コードの `Guid` 属性で、サンプルの GUID をコピーした GUID に置き換えて、中かっこ ( **{ }** ) を削除します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-156">In the `Guid` attribute of your code, replace the sample GUID with the GUID you copied, and remove the braces (**{ }**).</span></span>

1. <span data-ttu-id="e82d7-157">**ソリューション エクスプローラー**で **[プロパティ]** フォルダーを展開し、*AssemblyInfo.cs* または *AssemblyInfo.vb* ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-157">In **Solution Explorer**, expand the **Properties** folder and select the *AssemblyInfo.cs* or *AssemblyInfo.vb* file.</span></span> <span data-ttu-id="e82d7-158">コード エディターで、次の属性をファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-158">In the code editor, add the following attribute to the file:</span></span>

   ```csharp
   [assembly: ImportedFromTypeLib("")]
   ```

   ```vb
   <Assembly: ImportedFromTypeLib("")>
   ```

1. <span data-ttu-id="e82d7-159">**[ファイル]**  >  **[すべて保存]** を選択するか、**Ctrl**+**Shift**+**S** キーを押して、ファイルとプロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-159">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="e82d7-160">**ソリューション エクスプローラー**で **TypeEquivalenceInterface** プロジェクトを右クリックし、 **[ビルド]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-160">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Build**.</span></span> <span data-ttu-id="e82d7-161">クラス ライブラリの DLL ファイルがコンパイルされ、指定したビルド出力パス (たとえば、*C:\TypeEquivalenceSample*) に保存されます。</span><span class="sxs-lookup"><span data-stu-id="e82d7-161">The class library DLL file is compiled and saved to the specified build output path, for example *C:\TypeEquivalenceSample*.</span></span>

## <a name="create-a-runtime-class"></a><span data-ttu-id="e82d7-162">ランタイム クラスを作成する</span><span class="sxs-lookup"><span data-stu-id="e82d7-162">Create a runtime class</span></span>

<span data-ttu-id="e82d7-163">次に、型等価性ランタイム クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-163">Next, create the type equivalence runtime class.</span></span>

1. <span data-ttu-id="e82d7-164">Visual Studio で、 **[ファイル]**  >  **[新規作成]**  >  **[プロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-164">In Visual Studio, select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="e82d7-165">**[新しいプロジェクトの作成]** ダイアログ ボックスで、 **[Search for templates]\(テンプレートの検索\)** ボックスに「*クラス ライブラリ*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-165">In the **Create a new project** dialog box, type *class library* in the **Search for templates** box.</span></span> <span data-ttu-id="e82d7-166">一覧から C# または Visual Basic の**クラス ライブラリ (.NET Framework)** テンプレートを選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-166">Select either the C# or Visual Basic **Class Library (.NET Framework)** template from the list, and then select **Next**.</span></span>

1. <span data-ttu-id="e82d7-167">**[新しいプロジェクトの構成]** ダイアログ ボックスの **[プロジェクト名]** に「*TypeEquivalenceRuntime*」と入力し、 **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-167">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceRuntime*, and then select **Create**.</span></span> <span data-ttu-id="e82d7-168">新しいプロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e82d7-168">The new project is created.</span></span>

1. <span data-ttu-id="e82d7-169">**ソリューション エクスプローラー**で、*Class1.cs* ファイルまたは *Class1.vb* ファイルを右クリックし、 **[名前の変更]** を選択して、ファイル名を *Class1* から *SampleClass* に変更します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-169">In **Solution Explorer**, right-click the *Class1.cs* or *Class1.vb* file, select **Rename**, and rename the file from *Class1* to *SampleClass*.</span></span> <span data-ttu-id="e82d7-170">クラスの名前も `SampleClass` 変更するかどうかを確認を求めるメッセージが表示されたら、 **[はい]** と応答します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-170">Respond **Yes** to the prompt to also rename the class to `SampleClass`.</span></span> <span data-ttu-id="e82d7-171">このクラスは、 `ISampleInterface` インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-171">This class implements the `ISampleInterface` interface.</span></span>

1. <span data-ttu-id="e82d7-172">**ソリューション エクスプローラー**で **TypeEquivalenceInterface** プロジェクトを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-172">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Properties**.</span></span>

1. <span data-ttu-id="e82d7-173">**[プロパティ]** 画面の左側のウィンドウで **[ビルド]** を選択し、 **[出力パス]** を TypeEquivalenceInterface プロジェクトで使用したのと同じ場所 (たとえば、*C:\TypeEquivalenceSample*) に設定します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-173">Select **Build** on the left pane of the **Properties** screen, and then set the **Output path** to the same location you used for the TypeEquivalenceInterface project, for example, *C:\TypeEquivalenceSample*.</span></span>

1. <span data-ttu-id="e82d7-174">**[プロパティ]** 画面の左側のウィンドウで **[署名]** を選択し、 **[アセンブリに署名する]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e82d7-174">Select **Signing** on the left pane of the **Properties** screen, and then select the **Sign the assembly** check box.</span></span> <span data-ttu-id="e82d7-175">**[厳密な名前のキー ファイルを選択してください]** のドロップダウンで、 **[新規作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-175">In the dropdown for **Choose a strong name key file**, select **New**.</span></span>

1. <span data-ttu-id="e82d7-176">**[厳密な名前キーの作成]** ダイアログで、 **[キー ファイル名]** に「*key.snk*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-176">In the **Create Strong Name Key** dialog, under **Key file name**, type *key.snk*.</span></span> <span data-ttu-id="e82d7-177">**[キーファイルをパスワードで保護する]** チェック ボックスをオフにし、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-177">Deselect the **Protect my key file with a password** check box, and then select **OK**.</span></span>

1. <span data-ttu-id="e82d7-178">**ソリューション エクスプローラー**で、**TypeEquivalenceRuntime** プロジェクトを右クリックし、 **[追加]**  >  **[参照]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-178">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Add** > **Reference**.</span></span>

1. <span data-ttu-id="e82d7-179">**[参照マネージャー]** ダイアログ ボックスで **[参照]** を選択し、出力パスのフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-179">In the **Reference Manager** dialog, select **Browse** and browse to the output path folder.</span></span> <span data-ttu-id="e82d7-180">*TypeEquivalenceInterface.dll* ファイルを選択し、 **[追加]** を選択して、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-180">Select the *TypeEquivalenceInterface.dll* file, select **Add**, and then select **OK**.</span></span>

1. <span data-ttu-id="e82d7-181">**ソリューション エクスプローラー**で **[参照]** フォルダーを展開し、**TypeEquivalenceInterface** 参照を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-181">In **Solution Explorer**, expand the **References** folder and select the **TypeEquivalenceInterface** reference.</span></span> <span data-ttu-id="e82d7-182">**[プロパティ]** ウィンドウで、まだ設定されていない場合は **[特定バージョン]** を **[False]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-182">In the **Properties** pane, set **Specific Version** to **False** if it is not already.</span></span>

1. <span data-ttu-id="e82d7-183">コード エディターで *SampleClass* クラス ファイルを開き、その内容を次のコードに置き換えて、`SampleClass` クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-183">Open the *SampleClass* class file in the code editor, and replace its contents with the following code to create the `SampleClass` class:</span></span>

   ```csharp
   using System;
   using TypeEquivalenceInterface;

   namespace TypeEquivalenceRuntime
   {
       public class SampleClass : ISampleInterface
       {
           private string p_UserInput;
           public string UserInput { get { return p_UserInput; } }

           public void GetUserInput()
           {
               Console.WriteLine("Please enter a value:");
               p_UserInput = Console.ReadLine();
           }
       }
   }
   ```

   ```vb
   Imports TypeEquivalenceInterface

   Public Class SampleClass
       Implements ISampleInterface

       Private p_UserInput As String
       Public ReadOnly Property UserInput() As String Implements ISampleInterface.UserInput
           Get
               Return p_UserInput
           End Get
       End Property

       Public Sub GetUserInput() Implements ISampleInterface.GetUserInput
           Console.WriteLine("Please enter a value:")
           p_UserInput = Console.ReadLine()
       End Sub
   End Class
   ```

1. <span data-ttu-id="e82d7-184">**[ファイル]**  >  **[すべて保存]** を選択するか、**Ctrl**+**Shift**+**S** キーを押して、ファイルとプロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-184">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="e82d7-185">**ソリューション エクスプローラー**で **TypeEquivalenceRuntime** プロジェクトを右クリックし、 **[ビルド]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-185">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Build**.</span></span> <span data-ttu-id="e82d7-186">クラス ライブラリの DLL ファイルがコンパイルされ、指定したビルド出力パスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="e82d7-186">The class library DLL file is compiled and saved to the specified build output path.</span></span>

## <a name="create-a-client-project"></a><span data-ttu-id="e82d7-187">クライアント プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="e82d7-187">Create a client project</span></span>

<span data-ttu-id="e82d7-188">最後に、インターフェイス アセンブリを参照する型等価性クライアント プログラムを作成します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-188">Finally, create a type equivalence client program that references the interface assembly.</span></span>

1. <span data-ttu-id="e82d7-189">Visual Studio で、 **[ファイル]**  >  **[新規作成]**  >  **[プロジェクト]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-189">In Visual Studio, select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="e82d7-190">**[新しいプロジェクトの作成]** ダイアログ ボックスで、 **[Search for templates]\(テンプレートの検索\)** ボックスに「*コンソール*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-190">In the **Create a new project** dialog box, type *console* in the **Search for templates** box.</span></span> <span data-ttu-id="e82d7-191">一覧から C# または Visual Basic の**コンソール アプリ (.NET Framework)** テンプレートを選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-191">Select either the C# or Visual Basic **Console App (.NET Framework)** template from the list, and then select **Next**.</span></span>

1. <span data-ttu-id="e82d7-192">**[新しいプロジェクトの構成]** ダイアログ ボックスの **[プロジェクト名]** に「*TypeEquivalenceClient*」と入力し、 **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-192">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceClient*, and then select **Create**.</span></span> <span data-ttu-id="e82d7-193">新しいプロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e82d7-193">The new project is created.</span></span>

1. <span data-ttu-id="e82d7-194">**ソリューション エクスプローラー**で **TypeEquivalenceClient** プロジェクトを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-194">In **Solution Explorer**, right-click the **TypeEquivalenceClient** project and select **Properties**.</span></span>

1. <span data-ttu-id="e82d7-195">**[プロパティ]** 画面の左側のウィンドウで **[ビルド]** を選択し、 **[出力パス]** を TypeEquivalenceInterface プロジェクトで使用したのと同じ場所 (たとえば、*C:\TypeEquivalenceSample*) に設定します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-195">Select **Build** on the left pane of the **Properties** screen, and then set the **Output path** to the same location you used for the TypeEquivalenceInterface project, for example, *C:\TypeEquivalenceSample*.</span></span>

1. <span data-ttu-id="e82d7-196">**ソリューション エクスプローラー**で **TypeEquivalenceClient** プロジェクトを右クリックし、 **[追加]**  >  **[参照]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-196">In **Solution Explorer**, right-click the **TypeEquivalenceClient** project and select **Add** > **Reference**.</span></span>

1. <span data-ttu-id="e82d7-197">**[参照マネージャー]** ダイアログで、**TypeEquivalenceInterface.dll** ファイルが一覧に既に表示されている場合は、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-197">In the **Reference Manager** dialog, if the **TypeEquivalenceInterface.dll** file is already listed, select it.</span></span> <span data-ttu-id="e82d7-198">表示されていない場合は、 **[参照]** を選択し、出力パス フォルダーを参照して、(*TypeEquivalenceRuntime.dll* ではなく) *TypeEquivalenceInterface.dll* ファイルを選択し、 **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-198">If not, select **Browse**, browse to the output path folder, select the *TypeEquivalenceInterface.dll* file (not the *TypeEquivalenceRuntime.dll*), and select **Add**.</span></span> <span data-ttu-id="e82d7-199">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-199">Select **OK**.</span></span>

1. <span data-ttu-id="e82d7-200">**ソリューション エクスプローラー**で **[参照]** フォルダーを展開し、**TypeEquivalenceInterface** 参照を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-200">In **Solution Explorer**, expand the **References** folder and select the **TypeEquivalenceInterface** reference.</span></span> <span data-ttu-id="e82d7-201">**[プロパティ]** ウィンドウで、 **[相互運用型の埋め込み]** を **[True]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-201">In the **Properties** pane, set **Embed Interop Types** to **True**.</span></span>

1. <span data-ttu-id="e82d7-202">コード エディターで *Program.cs* または *Module1.vb* ファイルを開き、その内容を次のコードに置き換えて、クライアント プログラムを作成します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-202">Open the *Program.cs* or *Module1.vb* file in the code editor, and replace its contents with the following code to create the client program:</span></span>

   ```csharp
   using System;
   using System.Reflection;
   using TypeEquivalenceInterface;

   namespace TypeEquivalenceClient
   {
       class Program
       {
           static void Main(string[] args)
           {
               Assembly sampleAssembly = Assembly.Load("TypeEquivalenceRuntime");
               ISampleInterface sampleClass =
                   (ISampleInterface)sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass");
               sampleClass.GetUserInput();
               Console.WriteLine(sampleClass.UserInput);
               Console.WriteLine(sampleAssembly.GetName().Version.ToString());
               Console.ReadLine();
           }
       }
   }
   ```

   ```vb
   Imports System.Reflection
   Imports TypeEquivalenceInterface

   Module Module1

       Sub Main()
           Dim sampleAssembly = Assembly.Load("TypeEquivalenceRuntime")
           Dim sampleClass As ISampleInterface = CType( _
               sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass"), ISampleInterface)
           sampleClass.GetUserInput()
           Console.WriteLine(sampleClass.UserInput)
           Console.WriteLine(sampleAssembly.GetName().Version)
           Console.ReadLine()
       End Sub

   End Module
   ```

1. <span data-ttu-id="e82d7-203">**[ファイル]**  >  **[すべて保存]** を選択するか、**Ctrl**+**Shift**+**S** キーを押して、ファイルとプロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-203">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="e82d7-204">**Ctrl**+**F5** キーを押し、プログラムをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-204">Press **Ctrl**+**F5** to build and run the program.</span></span> <span data-ttu-id="e82d7-205">コンソールの出力にアセンブリのバージョン **1.0.0.0** が返されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e82d7-205">Note that the console output returns the assembly version **1.0.0.0**.</span></span>

## <a name="modify-the-interface"></a><span data-ttu-id="e82d7-206">インターフェイスを変更する</span><span class="sxs-lookup"><span data-stu-id="e82d7-206">Modify the interface</span></span>

<span data-ttu-id="e82d7-207">ここでは、インターフェイス アセンブリを変更して、そのバージョンを変更します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-207">Now, modify the interface assembly, and change its version.</span></span>

1. <span data-ttu-id="e82d7-208">Visual Studio で、 **[ファイル]**  >  **[開く]**  >  **[プロジェクト/ソリューション]** を選択し、**TypeEquivalenceInterface** プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="e82d7-208">In Visual Studio, select **File** > **Open** > **Project/Solution**, and open the **TypeEquivalenceInterface** project.</span></span>

1. <span data-ttu-id="e82d7-209">**ソリューション エクスプローラー**で **TypeEquivalenceInterface** プロジェクトを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-209">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Properties**.</span></span>

1. <span data-ttu-id="e82d7-210">**[プロパティ]** 画面の左側のウィンドウで **[アプリケーション]** を選択し、 **[アセンブリ情報]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-210">Select **Application** on the left pane of the **Properties** screen, and then select **Assembly Information**.</span></span>

1. <span data-ttu-id="e82d7-211">**[アセンブリ情報]** ダイアログ ボックスで、 **[アセンブリのバージョン]** と **[ファイルのバージョン]** の値を「*2.0.0.0*」に変更して、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-211">In the **Assembly Information** dialog box, change the **Assembly version** and **File version** values to *2.0.0.0*, and then select **OK**.</span></span>

1. <span data-ttu-id="e82d7-212">*SampleInterface.cs* ファイルまたは *SampleInterface.vb* ファイルを開き、次のコード行を `ISampleInterface` インターフェイスに追加します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-212">Open the *SampleInterface.cs* or *SampleInterface.vb* file, and add the following line of code to the `ISampleInterface` interface:</span></span>

   ```csharp
   DateTime GetDate();
   ```

   ```vb
   Function GetDate() As Date
   ```

1. <span data-ttu-id="e82d7-213">**[ファイル]**  >  **[すべて保存]** を選択するか、**Ctrl**+**Shift**+**S** キーを押して、ファイルとプロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-213">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="e82d7-214">**ソリューション エクスプローラー**で **TypeEquivalenceInterface** プロジェクトを右クリックし、 **[ビルド]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-214">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Build**.</span></span> <span data-ttu-id="e82d7-215">クラス ライブラリの DLL ファイルの新しいバージョンがコンパイルされて、ビルド出力パスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="e82d7-215">A new version of the class library DLL file is compiled and saved to the build output path.</span></span>

## <a name="modify-the-runtime-class"></a><span data-ttu-id="e82d7-216">ランタイム クラスを変更する</span><span class="sxs-lookup"><span data-stu-id="e82d7-216">Modify the runtime class</span></span>

<span data-ttu-id="e82d7-217">また、ランタイム クラスを変更し、そのバージョンを更新します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-217">Also modify the runtime class and update its version.</span></span>

1. <span data-ttu-id="e82d7-218">Visual Studio で、 **[ファイル]**  >  **[開く]**  >  **[プロジェクト/ソリューション]** を選択し、**TypeEquivalenceRuntime** プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="e82d7-218">In Visual Studio, select **File** > **Open** > **Project/Solution**, and open the **TypeEquivalenceRuntime** project.</span></span>

1. <span data-ttu-id="e82d7-219">**ソリューション エクスプローラー**で **TypeEquivalenceRuntime** プロジェクトを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-219">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Properties**.</span></span>

1. <span data-ttu-id="e82d7-220">**[プロパティ]** 画面の左側のウィンドウで **[アプリケーション]** を選択し、 **[アセンブリ情報]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-220">Select **Application** on the left pane of the **Properties** screen, and then select **Assembly Information**.</span></span>

1. <span data-ttu-id="e82d7-221">**[アセンブリ情報]** ダイアログ ボックスで、 **[アセンブリのバージョン]** と **[ファイルのバージョン]** の値を「*2.0.0.0*」に変更して、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-221">In the **Assembly Information** dialog box, change the **Assembly version** and **File version** values to *2.0.0.0*, and then select **OK**.</span></span>

1. <span data-ttu-id="e82d7-222">*SampleClass.cs* ファイルまたは *SampleClass.vb* ファイルを開き、次のコードを `SampleClass` クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-222">Open the *SampleClass.cs* or *SampleClass.vb* file, and add the following code to the `SampleClass` class:</span></span>

   ```csharp
    public DateTime GetDate()
    {
        return DateTime.Now;
    }
   ```

   ```vb
   Public Function GetDate() As DateTime Implements ISampleInterface.GetDate
       Return Now
   End Function
   ```

1. <span data-ttu-id="e82d7-223">**[ファイル]**  >  **[すべて保存]** を選択するか、**Ctrl**+**Shift**+**S** キーを押して、ファイルとプロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-223">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="e82d7-224">**ソリューション エクスプローラー**で **TypeEquivalenceRuntime** プロジェクトを右クリックし、 **[ビルド]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-224">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Build**.</span></span> <span data-ttu-id="e82d7-225">クラス ライブラリの DLL ファイルの新しいバージョンがコンパイルされて、ビルド出力パスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="e82d7-225">A new version of the class library DLL file is compiled and saved to the build output path.</span></span>

## <a name="run-the-updated-client-program"></a><span data-ttu-id="e82d7-226">更新されたクライアント プログラムを実行する</span><span class="sxs-lookup"><span data-stu-id="e82d7-226">Run the updated client program</span></span>

<span data-ttu-id="e82d7-227">ビルド出力フォルダーの場所に移動し、*TypeEquivalenceClient.exe* を実行します。</span><span class="sxs-lookup"><span data-stu-id="e82d7-227">Go to the build output folder location and run *TypeEquivalenceClient.exe*.</span></span> <span data-ttu-id="e82d7-228">プログラムを再コンパイルしなくても、コンソール出力に `TypeEquivalenceRuntime` アセンブリの新しいバージョン *2.0.0.0* が反映されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e82d7-228">Note that the console output now reflects the new version of the `TypeEquivalenceRuntime` assembly, *2.0.0.0*, without the program being recompiled.</span></span>

## <a name="see-also"></a><span data-ttu-id="e82d7-229">関連項目</span><span class="sxs-lookup"><span data-stu-id="e82d7-229">See also</span></span>

- [<span data-ttu-id="e82d7-230">-link (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="e82d7-230">-link (C# Compiler Options)</span></span>](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [<span data-ttu-id="e82d7-231">-link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e82d7-231">-link (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/link.md)
- [<span data-ttu-id="e82d7-232">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="e82d7-232">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="e82d7-233">プログラミングの概念 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e82d7-233">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="e82d7-234">.NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="e82d7-234">Assemblies in .NET</span></span>](index.md)
