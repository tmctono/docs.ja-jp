---
title: COM への .NET Core コンポーネントの公開
ms.date: 07/12/2019
helpviewer_keywords:
- exposing .NET Core components to COM
- interoperation with unmanaged code, exposing .NET Core components
- COM interop, exposing COM components
ms.assetid: 21271167-fe7f-46ba-a81f-a6812ea649d4
author: jkoritzinsky
ms.author: jekoritz
ms.openlocfilehash: 686d1b31478121a8b2c907d99672a5fcc3438a71
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70849035"
---
# <a name="exposing-net-core-components-to-com"></a><span data-ttu-id="9a35b-102">COM への .NET Core コンポーネントの公開</span><span class="sxs-lookup"><span data-stu-id="9a35b-102">Exposing .NET Core Components to COM</span></span>

<span data-ttu-id="9a35b-103">.NET Core では、.NET Framework と比較し、.NET オブジェクトを COM に公開する工程が大幅に簡素化されています。</span><span class="sxs-lookup"><span data-stu-id="9a35b-103">In .NET Core, the process for exposing your .NET objects to COM has been significantly streamlined in comparison to .NET Framework.</span></span> <span data-ttu-id="9a35b-104">次の手順では、クラスを COM に公開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9a35b-104">The following process will walk you through how to expose a class to COM.</span></span> <span data-ttu-id="9a35b-105">このチュートリアルでは、次の方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="9a35b-105">This tutorial shows you how to:</span></span>

- <span data-ttu-id="9a35b-106">.NET Core から COM にクラスを公開します。</span><span class="sxs-lookup"><span data-stu-id="9a35b-106">Expose a class to COM from .NET Core.</span></span>
- <span data-ttu-id="9a35b-107">使用する .NET Core ライブラリをビルドする一環として、COM サーバーを生成します。</span><span class="sxs-lookup"><span data-stu-id="9a35b-107">Generate a COM server as part of building your .NET Core library.</span></span>
- <span data-ttu-id="9a35b-108">レジストリを使用しない COM 用の side-by-side サーバー マニフェストを自動生成します。</span><span class="sxs-lookup"><span data-stu-id="9a35b-108">Automatically generate a side-by-side server manifest for Registry-Free COM.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9a35b-109">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9a35b-109">Prerequisites</span></span>

- <span data-ttu-id="9a35b-110">[.NET Core 3.0 Preview 7 SDK](https://dotnet.microsoft.com/download) 以降のバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9a35b-110">Install the [.NET Core 3.0 Preview 7 SDK](https://dotnet.microsoft.com/download) or a newer version.</span></span>

## <a name="create-the-library"></a><span data-ttu-id="9a35b-111">ライブラリを作成する</span><span class="sxs-lookup"><span data-stu-id="9a35b-111">Create the library</span></span>

<span data-ttu-id="9a35b-112">最初の手順では、ライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="9a35b-112">The first step is to create the library.</span></span>

1. <span data-ttu-id="9a35b-113">新しいフォルダーを作成し、そのフォルダーで `dotnet new classlib` を実行します。</span><span class="sxs-lookup"><span data-stu-id="9a35b-113">Create a new folder, and in that folder run `dotnet new classlib`.</span></span>
2. <span data-ttu-id="9a35b-114">`Class1.cs`を開きます。</span><span class="sxs-lookup"><span data-stu-id="9a35b-114">Open `Class1.cs`.</span></span>
3. <span data-ttu-id="9a35b-115">ファイルの先頭に、`using System.Runtime.InteropServices;` を追加します。</span><span class="sxs-lookup"><span data-stu-id="9a35b-115">Add `using System.Runtime.InteropServices;` to the top of the file.</span></span>
4. <span data-ttu-id="9a35b-116">`IServer` という名前のインターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9a35b-116">Create an interface named `IServer`.</span></span> <span data-ttu-id="9a35b-117">たとえば、[!code-csharp[The IServer interface](~/samples/core/extensions/COMServerDemo/COMContract/IServer.cs)] のようにします。</span><span class="sxs-lookup"><span data-stu-id="9a35b-117">For example: [!code-csharp[The IServer interface](~/samples/core/extensions/COMServerDemo/COMContract/IServer.cs)]</span></span>
5. <span data-ttu-id="9a35b-118">このインターフェイスに、実装する COM インターフェイス用のインターフェイス GUID を使用して、`[Guid("<IID>")]` 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="9a35b-118">Add the `[Guid("<IID>")]` attribute to the interface, with the interface GUID for the COM interface you're implementing.</span></span> <span data-ttu-id="9a35b-119">たとえば、`[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]` のようにします。</span><span class="sxs-lookup"><span data-stu-id="9a35b-119">For example, `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`.</span></span> <span data-ttu-id="9a35b-120">この GUID は、COM 用のこのインターフェイスの唯一の識別子であるため、一意である必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9a35b-120">Note that this GUID needs to be unique since it is the only identifier of this interface for COM.</span></span> <span data-ttu-id="9a35b-121">Visual Studio で GUID を作成するには、[ツール] > [GUID の作成] の順に移動して GUI の作成ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="9a35b-121">In Visual Studio, you can generate a GUID by going to Tools > Create GUID to open the Create GUID tool.</span></span>
6. <span data-ttu-id="9a35b-122">インターフェイスに `[InterfaceType]` 属性を追加し、お使いのインターフェイスで実装すべき基本 COM インターフェイスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9a35b-122">Add the `[InterfaceType]` attribute to the interface and specify what base COM interfaces your interface should implement.</span></span>
7. <span data-ttu-id="9a35b-123">`IServer` を実装する、`Server` という名前のクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9a35b-123">Create a class named `Server` that implements `IServer`.</span></span>
8. <span data-ttu-id="9a35b-124">クラスに、実装する COM クラス用のクラス識別子 GUID を使用して、`[Guid("<CLSID>")]` 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="9a35b-124">Add the `[Guid("<CLSID>")]` attribute to the class, with the class identifier GUID for the COM class you're implementing.</span></span> <span data-ttu-id="9a35b-125">たとえば、`[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]` のようにします。</span><span class="sxs-lookup"><span data-stu-id="9a35b-125">For example, `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`.</span></span> <span data-ttu-id="9a35b-126">インターフェイス GUID でこの GUID は、COM ではこのインターフェイスの唯一の識別子であるため、一意である必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9a35b-126">As with the interface GUID, this GUID must be unique since it is the only identifier of this interface to COM.</span></span>
9. <span data-ttu-id="9a35b-127">インターフェイスとクラスの両方に `[ComVisible(true)]` 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="9a35b-127">Add the `[ComVisible(true)]` attribute to both the interface and the class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9a35b-128">.NET Framework とは異なり、.NET Core では COM を使用してアクティブ化したいすべてのクラスの CLSID を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a35b-128">Unlike in .NET Framework, .NET Core requires you to specify the CLSID of any class you want to be activatable via COM.</span></span>

## <a name="generate-the-com-host"></a><span data-ttu-id="9a35b-129">COM ホストを生成する</span><span class="sxs-lookup"><span data-stu-id="9a35b-129">Generate the COM host</span></span>

1. <span data-ttu-id="9a35b-130">`.csproj` プロジェクト ファイルを開き、`<PropertyGroup></PropertyGroup>` タグの内側に `<EnableComHosting>true</EnableComHosting>` を追加します。</span><span class="sxs-lookup"><span data-stu-id="9a35b-130">Open the `.csproj` project file and add `<EnableComHosting>true</EnableComHosting>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="9a35b-131">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="9a35b-131">Build the project.</span></span>

<span data-ttu-id="9a35b-132">結果として、`ProjectName.dll`、`ProjectName.runtimeconfig.json`、`ProjectName.deps.json`、および`ProjectName.comhost.dll` ファイルが出力されます。</span><span class="sxs-lookup"><span data-stu-id="9a35b-132">The resulting output will have a `ProjectName.dll`, `ProjectName.deps.json`, `ProjectName.runtimeconfig.json` and `ProjectName.comhost.dll` file.</span></span>

## <a name="register-the-com-host-for-com"></a><span data-ttu-id="9a35b-133">COM 用の COM ホストを登録する</span><span class="sxs-lookup"><span data-stu-id="9a35b-133">Register the COM host for COM</span></span>

<span data-ttu-id="9a35b-134">管理者特権でのコマンド プロンプトを開き、`regsvr32 ProjectName.comhost.dll` を実行します。</span><span class="sxs-lookup"><span data-stu-id="9a35b-134">Open an elevated command prompt and run `regsvr32 ProjectName.comhost.dll`.</span></span> <span data-ttu-id="9a35b-135">これにより、公開されているすべての .NET オブジェクトが COM に登録されます。</span><span class="sxs-lookup"><span data-stu-id="9a35b-135">That will register all of your exposed .NET objects with COM.</span></span>

## <a name="enabling-regfree-com"></a><span data-ttu-id="9a35b-136">Regfree COM を有効にする</span><span class="sxs-lookup"><span data-stu-id="9a35b-136">Enabling RegFree COM</span></span>

1. <span data-ttu-id="9a35b-137">`.csproj` プロジェクト ファイルを開き、`<PropertyGroup></PropertyGroup>` タグの内側に `<EnableRegFreeCom>true</EnableRegFreeCom>` を追加します。</span><span class="sxs-lookup"><span data-stu-id="9a35b-137">Open the `.csproj` project file and add `<EnableRegFreeCom>true</EnableRegFreeCom>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="9a35b-138">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="9a35b-138">Build the project.</span></span>

<span data-ttu-id="9a35b-139">これで結果として、`ProjectName.X.manifest` ファイルも出力されます。</span><span class="sxs-lookup"><span data-stu-id="9a35b-139">The resulting output will now also have a `ProjectName.X.manifest` file.</span></span> <span data-ttu-id="9a35b-140">このファイルが、Registry-Free COM で使用される side-by-side マニフェストです。</span><span class="sxs-lookup"><span data-stu-id="9a35b-140">This file is the side-by-side manifest for use with Registry-Free COM.</span></span>

## <a name="sample"></a><span data-ttu-id="9a35b-141">サンプル</span><span class="sxs-lookup"><span data-stu-id="9a35b-141">Sample</span></span>

<span data-ttu-id="9a35b-142">GitHub の dotnet/samples リポジトリには、完全に機能する [COM サーバーのサンプル](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo)があります。</span><span class="sxs-lookup"><span data-stu-id="9a35b-142">There is a fully functional [COM server sample](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo) in the dotnet/samples repository on GitHub.</span></span>

## <a name="additional-notes"></a><span data-ttu-id="9a35b-143">その他のメモ</span><span class="sxs-lookup"><span data-stu-id="9a35b-143">Additional Notes</span></span>

<span data-ttu-id="9a35b-144">.NET Core では、.NET Framework とは異なり、.NET Core アセンブリからの COM タイプ ライブラリ (TLB) の生成はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9a35b-144">Unlike in .NET Framework, there is no support in .NET Core for generating a COM Type Library (TLB) from a .NET Core assembly.</span></span> <span data-ttu-id="9a35b-145">インターフェイスのネイティブ宣言には、IDL ファイルまたは C++ ヘッダーを手動で記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a35b-145">You will either have to manually write an IDL file or a C++ header for the native declarations of your interfaces.</span></span>

<span data-ttu-id="9a35b-146">また、.NET Framework と .NET Core の両方の同じプロセスでの読み込みはサポートされていないため、.NET Core COM サーバーを .NET Framework COM クライアント プロセスに読み込むこと、またはその逆はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9a35b-146">Additionally, loading both .NET Framework and .NET Core into the same process is unsupported, and as a result loading a .NET Core COM server into a .NET Framework COM client process or vice versa is not supported.</span></span>
