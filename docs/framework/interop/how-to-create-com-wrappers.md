---
title: '方法: COM ラッパーを作成する'
description: Visual Studio または .NET のツール (Tlbimp.exe と Regasm.exe) を使用して、コンポーネント オブジェクト モデル (COM) ラッパーを作成します。 どちらの方法でも、2 種類の COM ラッパーが生成されます。
ms.date: 03/30/2017
helpviewer_keywords:
- COM,wrappers creating
- COM,wrappers Visual Studio
ms.assetid: bdf89bea-1623-45ee-a57b-cf7c90395efa
ms.openlocfilehash: 286526c710287e6efa3e49a7f7c55e3687076e29
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617393"
---
# <a name="how-to-create-com-wrappers"></a><span data-ttu-id="607a6-104">方法: COM ラッパーを作成する</span><span class="sxs-lookup"><span data-stu-id="607a6-104">How to: Create COM Wrappers</span></span>

<span data-ttu-id="607a6-105">Visual Studio 2005 の機能または .NET Framework のツールである Tlbimp.exe と Regasm.exe を使用して、COM (コンポーネント オブジェクト モデル) ラッパーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="607a6-105">You can create Component Object Model (COM) wrappers by using Visual Studio 2005 features or the .NET Framework tools Tlbimp.exe and Regasm.exe.</span></span> <span data-ttu-id="607a6-106">どちらの方法でも以下の 2 種類の COM ラッパーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="607a6-106">Both methods generate two types of COM wrappers:</span></span>

- <span data-ttu-id="607a6-107">タイプ ライブラリからの[ランタイム呼び出し可能ラッパー](../../standard/native-interop/runtime-callable-wrapper.md)。マネージド コードで COM オブジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="607a6-107">A [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) from a type library to run a COM object in managed code.</span></span>

- <span data-ttu-id="607a6-108">必要なレジストリ設定を含む [COM 呼び出し可能ラッパー](../../standard/native-interop/com-callable-wrapper.md)。ネイティブ アプリケーションでマネージド オブジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="607a6-108">A [COM Callable Wrapper](../../standard/native-interop/com-callable-wrapper.md) with the required registry settings to run a managed object in a native application.</span></span>

<span data-ttu-id="607a6-109">Visual Studio 2005 では、プロジェクトに参照として COM ラッパーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="607a6-109">In Visual Studio 2005, you can add the COM wrapper as a reference to your project.</span></span>

## <a name="wrap-com-objects-in-a-managed-application"></a><span data-ttu-id="607a6-110">マネージド アプリケーションに COM オブジェクトをラップする</span><span class="sxs-lookup"><span data-stu-id="607a6-110">Wrap COM Objects in a Managed Application</span></span>

### <a name="to-create-a-runtime-callable-wrapper-using-visual-studio"></a><span data-ttu-id="607a6-111">Visual Studio を使用してランタイム呼び出し可能ラッパーを作成するには</span><span class="sxs-lookup"><span data-stu-id="607a6-111">To create a runtime callable wrapper using Visual Studio</span></span>

1. <span data-ttu-id="607a6-112">マネージド アプリケーションのプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="607a6-112">Open the project for your managed application.</span></span>

2. <span data-ttu-id="607a6-113">**[プロジェクト]** メニューの **[すべてのファイルを表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="607a6-113">On the **Project** menu, click **Show All Files**.</span></span>

3. <span data-ttu-id="607a6-114">**[プロジェクト]** メニューの **[参照の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="607a6-114">On the **Project** menu, click **Add Reference**.</span></span>

4. <span data-ttu-id="607a6-115">[参照の追加] ダイアログ ボックスで、 **[COM]** タブをクリックし、使用するコンポーネントを選択して **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="607a6-115">In the Add Reference dialog box, click the **COM** tab, select the component you want to use, and click **OK**.</span></span>

     <span data-ttu-id="607a6-116">**ソリューション エクスプローラー**で、COM コンポーネントがプロジェクトの [参照設定] フォルダーに追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="607a6-116">In **Solution Explorer**, note that the COM component is added to the References folder in your project.</span></span>

<span data-ttu-id="607a6-117">これで、COM オブジェクトにアクセスするためのコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="607a6-117">You can now write code to access the COM object.</span></span> <span data-ttu-id="607a6-118">まず、Visual Basic の場合は `Imports` ステートメント、C# の場合は `Using` ステートメントなど、オブジェクトの宣言から始めます。</span><span class="sxs-lookup"><span data-stu-id="607a6-118">You can begin by declaring the object, such as with an `Imports` statement for Visual Basic or a `Using` statement for C#.</span></span>

> [!NOTE]
> <span data-ttu-id="607a6-119">Microsoft Office コンポーネントをプログラミングする場合は、最初に Microsoft ダウンロード センターから [Microsoft Office Primary Interop Assemblies Redistributable](https://www.microsoft.com/Download/details.aspx?id=3508) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="607a6-119">If you want to program Microsoft Office components, first install the [Microsoft Office Primary Interop Assemblies Redistributable](https://www.microsoft.com/Download/details.aspx?id=3508).</span></span>
  
### <a name="to-create-a-runtime-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="607a6-120">.NET Framework ツールを使用してランタイム呼び出し可能ラッパーを作成するには</span><span class="sxs-lookup"><span data-stu-id="607a6-120">To create a runtime callable wrapper using .NET Framework tools</span></span>  
  
- <span data-ttu-id="607a6-121">[Tlbimp.exe (タイプ ライブラリ インポーター)](../tools/tlbimp-exe-type-library-importer.md) ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="607a6-121">Run the [Tlbimp.exe (Type Library Importer)](../tools/tlbimp-exe-type-library-importer.md) tool.</span></span>  
  
 <span data-ttu-id="607a6-122">このツールは、元のタイプ ライブラリで定義された型のランタイム メタデータを含むアセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="607a6-122">This tool creates an assembly that contains run-time metadata for the types defined in the original type library.</span></span>  
  
## <a name="wrap-managed-objects-in-a-native-application"></a><span data-ttu-id="607a6-123">ネイティブ アプリケーションにマネージド オブジェクトをラップする</span><span class="sxs-lookup"><span data-stu-id="607a6-123">Wrap Managed Objects in a Native Application</span></span>  
  
### <a name="to-create-a-com-callable-wrapper-using-visual-studio"></a><span data-ttu-id="607a6-124">Visual Studio を使用して COM 呼び出し可能ラッパーを作成するには</span><span class="sxs-lookup"><span data-stu-id="607a6-124">To create a COM callable wrapper using Visual Studio</span></span>  
  
1. <span data-ttu-id="607a6-125">ネイティブ コードで実行するマネージド クラス用のクラス ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="607a6-125">Create a Class Library project for the managed class that you want to run in native code.</span></span> <span data-ttu-id="607a6-126">このクラスには、パラメーターなしのコンストラクターが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="607a6-126">The class must have a parameterless constructor.</span></span>  
  
     <span data-ttu-id="607a6-127">AssemblyInfo ファイルで、アセンブリの 4 つの部分で構成される完全なバージョン番号があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="607a6-127">Verify that you have a complete four-part version number for your assembly in the AssemblyInfo file.</span></span> <span data-ttu-id="607a6-128">この番号は、Windows レジストリでバージョンを管理するために必要となります。</span><span class="sxs-lookup"><span data-stu-id="607a6-128">This number is required for maintaining versioning in the Windows registry.</span></span> <span data-ttu-id="607a6-129">バージョン番号の詳細については、「[アセンブリのバージョン管理](../../standard/assembly/versioning.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="607a6-129">For more information about version numbers, see [Assembly Versioning](../../standard/assembly/versioning.md).</span></span>  
  
2. <span data-ttu-id="607a6-130">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="607a6-130">On the **Project** menu, click **Properties**.</span></span>  
  
3. <span data-ttu-id="607a6-131">**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="607a6-131">Click the **Compile** tab.</span></span>  
  
4. <span data-ttu-id="607a6-132">**[COM の相互運用機能に登録]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="607a6-132">Select the **Register for COM interop** check box.</span></span>  
  
 <span data-ttu-id="607a6-133">プロジェクトをビルドすると、アセンブリが COM 相互運用機能に対して自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="607a6-133">When you build the project, the assembly is automatically registered for COM interop.</span></span> <span data-ttu-id="607a6-134">Visual Studio 2005 でネイティブ アプリケーションをビルドする場合は、 **[プロジェクト]** メニューの **[参照の追加]** をクリックすることで、アセンブリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="607a6-134">If you are building a native application in Visual Studio 2005, you can use the assembly by clicking **Add Reference** on the **Project** menu.</span></span>  
  
### <a name="to-create-a-com-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="607a6-135">.NET Framework ツールを使用して COM 呼び出し可能ラッパーを作成するには</span><span class="sxs-lookup"><span data-stu-id="607a6-135">To create a COM callable wrapper using .NET Framework tools</span></span>  
  
<span data-ttu-id="607a6-136">[Regasm.exe (アセンブリ登録ツール)](../tools/regasm-exe-assembly-registration-tool.md) を実行します。</span><span class="sxs-lookup"><span data-stu-id="607a6-136">Run the [Regasm.exe (Assembly Registration Tool)](../tools/regasm-exe-assembly-registration-tool.md) tool.</span></span>  
  
<span data-ttu-id="607a6-137">このツールはアセンブリ メタデータを読み取り、必要なエントリをレジストリに追加します。</span><span class="sxs-lookup"><span data-stu-id="607a6-137">This tool reads the assembly metadata and adds the necessary entries to the registry.</span></span> <span data-ttu-id="607a6-138">その結果、COM クライアントで .NET Framework クラスを透過的に作成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="607a6-138">As a result, COM clients can create .NET Framework classes transparently.</span></span> <span data-ttu-id="607a6-139">アセンブリは、ネイティブ COM クラスの場合と同じように使用することができます。</span><span class="sxs-lookup"><span data-stu-id="607a6-139">You can use the assembly as if it were a native COM class.</span></span>  
  
<span data-ttu-id="607a6-140">任意のディレクトリにあるアセンブリで Regasm.exe を実行してから、[Gacutil.exe (グローバル アセンブリ キャッシュ ツール)](../tools/gacutil-exe-gac-tool.md) を実行して、そのアセンブリをグローバル アセンブリ キャッシュに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="607a6-140">You can run Regasm.exe on an assembly located in any directory, and then run the [Gacutil.exe (Global Assembly Cache Tool)](../tools/gacutil-exe-gac-tool.md) to move it to the global assembly cache.</span></span> <span data-ttu-id="607a6-141">アセンブリを移動しても場所のレジストリ エントリが無効になることはありません。これは、アセンブリが他の場所で見つからない場合に常にグローバル アセンブリ キャッシュが調べられるからです。</span><span class="sxs-lookup"><span data-stu-id="607a6-141">Moving the assembly does not invalidate location registry entries, because the global assembly cache is always examined if the assembly is not found elsewhere.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="607a6-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="607a6-142">See also</span></span>

- [<span data-ttu-id="607a6-143">ランタイム呼び出し可能ラッパー</span><span class="sxs-lookup"><span data-stu-id="607a6-143">Runtime Callable Wrapper</span></span>](../../standard/native-interop/runtime-callable-wrapper.md)
- [<span data-ttu-id="607a6-144">COM 呼び出し可能ラッパー</span><span class="sxs-lookup"><span data-stu-id="607a6-144">COM Callable Wrapper</span></span>](../../standard/native-interop/com-callable-wrapper.md)
