---
title: 'チュートリアル: WPF でホストするための Direct3D9 コンテンツの作成'
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 286e98bc-1eaa-4b5e-923d-3490a9cca5fc
ms.openlocfilehash: 462220b526db90d3acfa90a28f9bfd56dbe813e2
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991404"
---
# <a name="walkthrough-creating-direct3d9-content-for-hosting-in-wpf"></a><span data-ttu-id="6c8b1-102">チュートリアル: WPF でホストするための Direct3D9 コンテンツの作成</span><span class="sxs-lookup"><span data-stu-id="6c8b1-102">Walkthrough: Creating Direct3D9 Content for Hosting in WPF</span></span>
<span data-ttu-id="6c8b1-103">このチュートリアルでは、Windows Presentation Foundation (WPF) アプリケーションでのホストに適した Direct3D9 コンテンツを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-103">This walkthrough shows how to create Direct3D9 content that is suitable for hosting in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="6c8b1-104">WPF アプリケーションで Direct3D9 コンテンツをホストする方法の詳細については、「 [wpf と Direct3D9 の相互運用](wpf-and-direct3d9-interoperation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-104">For more information on hosting Direct3D9 content in WPF applications, see [WPF and Direct3D9 Interoperation](wpf-and-direct3d9-interoperation.md).</span></span>

 <span data-ttu-id="6c8b1-105">このチュートリアルでは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-105">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="6c8b1-106">Direct3D9 プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-106">Create a Direct3D9 project.</span></span>

- <span data-ttu-id="6c8b1-107">WPF アプリケーションでホストするための Direct3D9 プロジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-107">Configure the Direct3D9 project for hosting in a WPF application.</span></span>

 <span data-ttu-id="6c8b1-108">完了すると、WPF アプリケーションで使用する Direct3D9 コンテンツを含む DLL が作成されます。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-108">When you are finished, you will have a DLL that contains Direct3D9 content for use in a WPF application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6c8b1-109">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6c8b1-109">Prerequisites</span></span>
 <span data-ttu-id="6c8b1-110">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-110">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="6c8b1-111">Visual Studio 2010。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-111">Visual Studio 2010.</span></span>

- <span data-ttu-id="6c8b1-112">DirectX SDK 9 以降。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-112">DirectX SDK 9 or later.</span></span>

## <a name="creating-the-direct3d9-project"></a><span data-ttu-id="6c8b1-113">Direct3D9 プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="6c8b1-113">Creating the Direct3D9 Project</span></span>
 <span data-ttu-id="6c8b1-114">最初の手順では、Direct3D9 プロジェクトを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-114">The first step is to create and configure the Direct3D9 project.</span></span>

#### <a name="to-create-the-direct3d9-project"></a><span data-ttu-id="6c8b1-115">Direct3D9 プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="6c8b1-115">To create the Direct3D9 project</span></span>

1. <span data-ttu-id="6c8b1-116">という名前C++ `D3DContent`の新しい Win32 プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-116">Create a new Win32 Project in C++ named `D3DContent`.</span></span>

     <span data-ttu-id="6c8b1-117">Win32 アプリケーションウィザードが開き、[ようこそ] 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-117">The Win32 Application Wizard opens and displays the Welcome screen.</span></span>

2. <span data-ttu-id="6c8b1-118">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-118">Click **Next**.</span></span>

     <span data-ttu-id="6c8b1-119">[アプリケーションの設定] 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-119">The Application Settings screen appears.</span></span>

3. <span data-ttu-id="6c8b1-120">**[アプリケーションの種類:]** セクションで、 **[DLL]** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-120">In the **Application type:** section, select the **DLL** option.</span></span>

4. <span data-ttu-id="6c8b1-121">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-121">Click **Finish**.</span></span>

     <span data-ttu-id="6c8b1-122">D3DContent プロジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-122">The D3DContent project is generated.</span></span>

5. <span data-ttu-id="6c8b1-123">ソリューションエクスプローラーで、D3DContent プロジェクトを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-123">In Solution Explorer, right-click the D3DContent project and select **Properties**.</span></span>

     <span data-ttu-id="6c8b1-124">**[D3DContent プロパティページ]** ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-124">The **D3DContent Property Pages** dialog box opens.</span></span>

6. <span data-ttu-id="6c8b1-125">[ **C/C++**  node] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-125">Select the **C/C++** node.</span></span>

7. <span data-ttu-id="6c8b1-126">**[追加のインクルードディレクトリ]** フィールドで、DirectX インクルードフォルダーの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-126">In the **Additional Include Directories** field, specify the location of the DirectX include folder.</span></span> <span data-ttu-id="6c8b1-127">このフォルダーの既定の場所は、%ProgramFiles%\Microsoft DirectX SDK (*バージョン*) \ includeです。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-127">The default location for this folder is %ProgramFiles%\Microsoft DirectX SDK (*version*)\Include.</span></span>

8. <span data-ttu-id="6c8b1-128">**[リンカー]** ノードをダブルクリックして展開します。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-128">Double-click the **Linker** node to expand it.</span></span>

9. <span data-ttu-id="6c8b1-129">**[追加のライブラリディレクトリ]** フィールドで、DirectX ライブラリフォルダーの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-129">In the **Additional Library Directories** field, specify the location of the DirectX libraries folder.</span></span> <span data-ttu-id="6c8b1-130">このフォルダーの既定の場所は、%ProgramFiles%\Microsoft DirectX SDK (*バージョン*) \Lib\x86. です。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-130">The default location for this folder is %ProgramFiles%\Microsoft DirectX SDK (*version*)\Lib\x86.</span></span>

10. <span data-ttu-id="6c8b1-131">**入力**ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-131">Select the **Input** node.</span></span>

11. <span data-ttu-id="6c8b1-132">**[追加の依存関係]** フィールドに`d3d9.lib` 、 `d3dx9.lib`ファイルとファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-132">In the **Additional Dependencies** field, add the `d3d9.lib` and `d3dx9.lib` files.</span></span>

12. <span data-ttu-id="6c8b1-133">ソリューションエクスプローラーで、という名前`D3DContent.def`の新しいモジュール定義ファイル (.def) をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-133">In Solution Explorer, add a new module definition file (.def) named `D3DContent.def` to the project.</span></span>

## <a name="creating-the-direct3d9-content"></a><span data-ttu-id="6c8b1-134">Direct3D9 コンテンツの作成</span><span class="sxs-lookup"><span data-stu-id="6c8b1-134">Creating the Direct3D9 Content</span></span>
 <span data-ttu-id="6c8b1-135">最適なパフォーマンスを得るには、Direct3D9 コンテンツで特定の設定を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-135">To get the best performance, your Direct3D9 content must use particular settings.</span></span> <span data-ttu-id="6c8b1-136">次のコードは、パフォーマンス特性が最高の Direct3D9 サーフェスを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-136">The following code shows how to create a Direct3D9 surface that has the best performance characteristics.</span></span> <span data-ttu-id="6c8b1-137">詳細については、「 [Direct3D9 と WPF の相互運用性のパフォーマンスに関する考慮事項](performance-considerations-for-direct3d9-and-wpf-interoperability.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-137">For more information, see [Performance Considerations for Direct3D9 and WPF Interoperability](performance-considerations-for-direct3d9-and-wpf-interoperability.md).</span></span>

#### <a name="to-create-the-direct3d9-content"></a><span data-ttu-id="6c8b1-138">Direct3D9 コンテンツを作成するには</span><span class="sxs-lookup"><span data-stu-id="6c8b1-138">To create the Direct3D9 content</span></span>

1. <span data-ttu-id="6c8b1-139">ソリューションエクスプローラーを使用してC++ 、次のように3つのクラスをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-139">Using Solution Explorer, add three C++ classes to the project named the following.</span></span>

     <span data-ttu-id="6c8b1-140">`CRenderer`(仮想デストラクターを使用)</span><span class="sxs-lookup"><span data-stu-id="6c8b1-140">`CRenderer` (with virtual destructor)</span></span>

     `CRendererManager`

     `CTriangleRenderer`

2. <span data-ttu-id="6c8b1-141">コードエディターでレンダラーを開き、自動的に生成されたコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-141">Open Renderer.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.h#rendererh)]

3. <span data-ttu-id="6c8b1-142">コードエディターでレンダラーを開き、自動的に生成されたコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-142">Open Renderer.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderercpp)]

4. <span data-ttu-id="6c8b1-143">コードエディターで RendererManager .h を開き、自動的に生成されたコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-143">Open RendererManager.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.h#renderermanagerh)]

5. <span data-ttu-id="6c8b1-144">コードエディターで RendererManager .cpp を開き、自動的に生成されたコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-144">Open RendererManager.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanagercpp)]

6. <span data-ttu-id="6c8b1-145">コードエディターで TriangleRenderer を開き、自動的に生成されたコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-145">Open TriangleRenderer.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.h#trianglerendererh)]

7. <span data-ttu-id="6c8b1-146">コードエディターで TriangleRenderer を開き、自動的に生成されたコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-146">Open TriangleRenderer.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.cpp#trianglerenderercpp)]

8. <span data-ttu-id="6c8b1-147">コードエディターで stdafx.h を開き、自動的に生成されたコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-147">Open stdafx.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#StdafxH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/stdafx.h#stdafxh)]

9. <span data-ttu-id="6c8b1-148">コードエディターで dllmain を開き、自動的に生成されたコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-148">Open dllmain.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]

10. <span data-ttu-id="6c8b1-149">コードエディターで D3DContent を開きます。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-149">Open D3DContent.def in the code editor.</span></span>

11. <span data-ttu-id="6c8b1-150">自動的に生成されたコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-150">Replace the automatically generated code with the following code.</span></span>

    ```cpp
    LIBRARY "D3DContent"

    EXPORTS

    SetSize
    SetAlpha
    SetNumDesiredSamples
    SetAdapter

    GetBackBufferNoRef
    Render
    Destroy
    ```

12. <span data-ttu-id="6c8b1-151">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-151">Build the project.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6c8b1-152">次の手順</span><span class="sxs-lookup"><span data-stu-id="6c8b1-152">Next Steps</span></span>

- <span data-ttu-id="6c8b1-153">WPF アプリケーションで Direct3D9 コンテンツをホストします。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-153">Host the Direct3D9 content in a WPF application.</span></span> <span data-ttu-id="6c8b1-154">詳細については、「[チュートリアル:WPF](walkthrough-hosting-direct3d9-content-in-wpf.md)で Direct3D9 コンテンツをホストする。</span><span class="sxs-lookup"><span data-stu-id="6c8b1-154">For more information, see [Walkthrough: Hosting Direct3D9 Content in WPF](walkthrough-hosting-direct3d9-content-in-wpf.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6c8b1-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c8b1-155">See also</span></span>

- <xref:System.Windows.Interop.D3DImage>
- [<span data-ttu-id="6c8b1-156">Direct3D9 および WPF の相互運用性のパフォーマンスに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="6c8b1-156">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [<span data-ttu-id="6c8b1-157">チュートリアル: WPF での Direct3D9 コンテンツのホスト</span><span class="sxs-lookup"><span data-stu-id="6c8b1-157">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>](walkthrough-hosting-direct3d9-content-in-wpf.md)
