---
title: '方法: COM ラッパーを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- COM,wrappers creating
- COM,wrappers Visual Studio
ms.assetid: bdf89bea-1623-45ee-a57b-cf7c90395efa
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1c4423c20a9a485f3c40877ccd489c749dc0e2c
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2019
ms.locfileid: "70971833"
---
# <a name="how-to-create-com-wrappers"></a><span data-ttu-id="47eb8-102">方法: COM ラッパーを作成する</span><span class="sxs-lookup"><span data-stu-id="47eb8-102">How to: Create COM Wrappers</span></span>

<span data-ttu-id="47eb8-103">Visual Studio 2005 の機能または .NET Framework のツールである Tlbimp.exe と Regasm.exe を使用して、COM (コンポーネント オブジェクト モデル) ラッパーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="47eb8-103">You can create Component Object Model (COM) wrappers by using Visual Studio 2005 features or the .NET Framework tools Tlbimp.exe and Regasm.exe.</span></span> <span data-ttu-id="47eb8-104">どちらの方法でも以下の 2 種類の COM ラッパーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="47eb8-104">Both methods generate two types of COM wrappers:</span></span>

- <span data-ttu-id="47eb8-105">タイプ ライブラリからの[ランタイム呼び出し可能ラッパー](../../standard/native-interop/runtime-callable-wrapper.md)。マネージド コードで COM オブジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="47eb8-105">A [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) from a type library to run a COM object in managed code.</span></span>

- <span data-ttu-id="47eb8-106">必要なレジストリ設定を含む [COM 呼び出し可能ラッパー](../../standard/native-interop/com-callable-wrapper.md)。ネイティブ アプリケーションでマネージド オブジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="47eb8-106">A [COM Callable Wrapper](../../standard/native-interop/com-callable-wrapper.md) with the required registry settings to run a managed object in a native application.</span></span>

<span data-ttu-id="47eb8-107">Visual Studio 2005 では、プロジェクトに参照として COM ラッパーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="47eb8-107">In Visual Studio 2005, you can add the COM wrapper as a reference to your project.</span></span>

## <a name="wrap-com-objects-in-a-managed-application"></a><span data-ttu-id="47eb8-108">マネージド アプリケーションに COM オブジェクトをラップする</span><span class="sxs-lookup"><span data-stu-id="47eb8-108">Wrap COM Objects in a Managed Application</span></span>

### <a name="to-create-a-runtime-callable-wrapper-using-visual-studio"></a><span data-ttu-id="47eb8-109">Visual Studio を使用してランタイム呼び出し可能ラッパーを作成するには</span><span class="sxs-lookup"><span data-stu-id="47eb8-109">To create a runtime callable wrapper using Visual Studio</span></span>

1. <span data-ttu-id="47eb8-110">マネージド アプリケーションのプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="47eb8-110">Open the project for your managed application.</span></span>

2. <span data-ttu-id="47eb8-111">**[プロジェクト]** メニューの **[すべてのファイルを表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47eb8-111">On the **Project** menu, click **Show All Files**.</span></span>

3. <span data-ttu-id="47eb8-112">**[プロジェクト]** メニューの **[参照の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47eb8-112">On the **Project** menu, click **Add Reference**.</span></span>

4. <span data-ttu-id="47eb8-113">[参照の追加] ダイアログ ボックスで、 **[COM]** タブをクリックし、使用するコンポーネントを選択して **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47eb8-113">In the Add Reference dialog box, click the **COM** tab, select the component you want to use, and click **OK**.</span></span>

     <span data-ttu-id="47eb8-114">**ソリューション エクスプローラー**で、COM コンポーネントがプロジェクトの [参照設定] フォルダーに追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="47eb8-114">In **Solution Explorer**, note that the COM component is added to the References folder in your project.</span></span>

<span data-ttu-id="47eb8-115">これで、COM オブジェクトにアクセスするためのコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="47eb8-115">You can now write code to access the COM object.</span></span> <span data-ttu-id="47eb8-116">まず、Visual Basic の場合は `Imports` ステートメント、C# の場合は `Using` ステートメントなど、オブジェクトの宣言から始めます。</span><span class="sxs-lookup"><span data-stu-id="47eb8-116">You can begin by declaring the object, such as with an `Imports` statement for Visual Basic or a `Using` statement for C#.</span></span>

> [!NOTE]
> <span data-ttu-id="47eb8-117">Microsoft Office コンポーネントをプログラミングする場合は、最初に Microsoft ダウンロード センターから [Microsoft Office プライマリ相互運用機能アセンブリ](https://go.microsoft.com/fwlink/?LinkId=50479) (PIA) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="47eb8-117">If you want to program Microsoft Office components, first install the [Microsoft Office Primary Interop Assemblies](https://go.microsoft.com/fwlink/?LinkId=50479) (PIAs) from the Microsoft Download Center.</span></span> <span data-ttu-id="47eb8-118">手順 4 で、必要な Office 製品で使用可能な最新バージョンのオブジェクト ライブラリ (**Microsoft Word 11.0 Object Library** など) を選択します。</span><span class="sxs-lookup"><span data-stu-id="47eb8-118">In step 4, select the latest version of the object library available for the Office product you want, such as the **Microsoft Word 11.0 Object Library**.</span></span>  
  
### <a name="to-create-a-runtime-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="47eb8-119">.NET Framework ツールを使用してランタイム呼び出し可能ラッパーを作成するには</span><span class="sxs-lookup"><span data-stu-id="47eb8-119">To create a runtime callable wrapper using .NET Framework tools</span></span>  
  
- <span data-ttu-id="47eb8-120">[Tlbimp.exe (タイプ ライブラリ インポーター)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="47eb8-120">Run the [Tlbimp.exe (Type Library Importer)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) tool.</span></span>  
  
 <span data-ttu-id="47eb8-121">このツールは、元のタイプ ライブラリで定義された型のランタイム メタデータを含むアセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="47eb8-121">This tool creates an assembly that contains run-time metadata for the types defined in the original type library.</span></span>  
  
## <a name="wrap-managed-objects-in-a-native-application"></a><span data-ttu-id="47eb8-122">ネイティブ アプリケーションにマネージド オブジェクトをラップする</span><span class="sxs-lookup"><span data-stu-id="47eb8-122">Wrap Managed Objects in a Native Application</span></span>  
  
### <a name="to-create-a-com-callable-wrapper-using-visual-studio"></a><span data-ttu-id="47eb8-123">Visual Studio を使用して COM 呼び出し可能ラッパーを作成するには</span><span class="sxs-lookup"><span data-stu-id="47eb8-123">To create a COM callable wrapper using Visual Studio</span></span>  
  
1. <span data-ttu-id="47eb8-124">ネイティブ コードで実行するマネージド クラス用のクラス ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="47eb8-124">Create a Class Library project for the managed class that you want to run in native code.</span></span> <span data-ttu-id="47eb8-125">このクラスには、パラメーターなしのコンストラクターが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="47eb8-125">The class must have a parameterless constructor.</span></span>  
  
     <span data-ttu-id="47eb8-126">AssemblyInfo ファイルで、アセンブリの 4 つの部分で構成される完全なバージョン番号があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="47eb8-126">Verify that you have a complete four-part version number for your assembly in the AssemblyInfo file.</span></span> <span data-ttu-id="47eb8-127">この番号は、Windows レジストリでバージョンを管理するために必要となります。</span><span class="sxs-lookup"><span data-stu-id="47eb8-127">This number is required for maintaining versioning in the Windows registry.</span></span> <span data-ttu-id="47eb8-128">バージョン番号の詳細については、「[アセンブリのバージョン管理](../../standard/assembly/versioning.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47eb8-128">For more information about version numbers, see [Assembly Versioning](../../standard/assembly/versioning.md).</span></span>  
  
2. <span data-ttu-id="47eb8-129">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47eb8-129">On the **Project** menu, click **Properties**.</span></span>  
  
3. <span data-ttu-id="47eb8-130">**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="47eb8-130">Click the **Compile** tab.</span></span>  
  
4. <span data-ttu-id="47eb8-131">**[COM の相互運用機能に登録]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="47eb8-131">Select the **Register for COM interop** check box.</span></span>  
  
 <span data-ttu-id="47eb8-132">プロジェクトをビルドすると、アセンブリが COM 相互運用機能に対して自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="47eb8-132">When you build the project, the assembly is automatically registered for COM interop.</span></span> <span data-ttu-id="47eb8-133">Visual Studio 2005 でネイティブ アプリケーションをビルドする場合は、 **[プロジェクト]** メニューの **[参照の追加]** をクリックすることで、アセンブリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="47eb8-133">If you are building a native application in Visual Studio 2005, you can use the assembly by clicking **Add Reference** on the **Project** menu.</span></span>  
  
### <a name="to-create-a-com-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="47eb8-134">.NET Framework ツールを使用して COM 呼び出し可能ラッパーを作成するには</span><span class="sxs-lookup"><span data-stu-id="47eb8-134">To create a COM callable wrapper using .NET Framework tools</span></span>  
  
<span data-ttu-id="47eb8-135">[Regasm.exe (アセンブリ登録ツール)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) を実行します。</span><span class="sxs-lookup"><span data-stu-id="47eb8-135">Run the [Regasm.exe (Assembly Registration Tool)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) tool.</span></span>  
  
<span data-ttu-id="47eb8-136">このツールはアセンブリ メタデータを読み取り、必要なエントリをレジストリに追加します。</span><span class="sxs-lookup"><span data-stu-id="47eb8-136">This tool reads the assembly metadata and adds the necessary entries to the registry.</span></span> <span data-ttu-id="47eb8-137">その結果、COM クライアントで .NET Framework クラスを透過的に作成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="47eb8-137">As a result, COM clients can create .NET Framework classes transparently.</span></span> <span data-ttu-id="47eb8-138">アセンブリは、ネイティブ COM クラスの場合と同じように使用することができます。</span><span class="sxs-lookup"><span data-stu-id="47eb8-138">You can use the assembly as if it were a native COM class.</span></span>  
  
<span data-ttu-id="47eb8-139">任意のディレクトリにあるアセンブリで Regasm.exe を実行してから、[Gacutil.exe (グローバル アセンブリ キャッシュ ツール)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) を実行して、そのアセンブリをグローバル アセンブリ キャッシュに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="47eb8-139">You can run Regasm.exe on an assembly located in any directory, and then run the [Gacutil.exe (Global Assembly Cache Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to move it to the global assembly cache.</span></span> <span data-ttu-id="47eb8-140">アセンブリを移動しても場所のレジストリ エントリが無効になることはありません。これは、アセンブリが他の場所で見つからない場合に常にグローバル アセンブリ キャッシュが調べられるからです。</span><span class="sxs-lookup"><span data-stu-id="47eb8-140">Moving the assembly does not invalidate location registry entries, because the global assembly cache is always examined if the assembly is not found elsewhere.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47eb8-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="47eb8-141">See also</span></span>

- [<span data-ttu-id="47eb8-142">ランタイム呼び出し可能ラッパー</span><span class="sxs-lookup"><span data-stu-id="47eb8-142">Runtime Callable Wrapper</span></span>](../../standard/native-interop/runtime-callable-wrapper.md)
- [<span data-ttu-id="47eb8-143">COM 呼び出し可能ラッパー</span><span class="sxs-lookup"><span data-stu-id="47eb8-143">COM Callable Wrapper</span></span>](../../standard/native-interop/com-callable-wrapper.md)
