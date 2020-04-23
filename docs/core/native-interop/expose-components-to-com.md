---
title: COM への .NET Core コンポーネントの公開
description: このチュートリアルでは、.NET Core から COM にクラスを公開する方法について説明します。 COM サーバーと、レジストリを使用しない COM 用のサイドバイサイド サーバー マニフェストを生成します。
ms.date: 07/12/2019
helpviewer_keywords:
- exposing .NET Core components to COM
- interoperation with unmanaged code, exposing .NET Core components
- COM interop, exposing COM components
ms.assetid: 21271167-fe7f-46ba-a81f-a6812ea649d4
author: jkoritzinsky
ms.author: jekoritz
ms.openlocfilehash: 17d85b9e9734fae0bb69f94da8c08669216ab0ae
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242869"
---
# <a name="exposing-net-core-components-to-com"></a><span data-ttu-id="3afa8-104">COM への .NET Core コンポーネントの公開</span><span class="sxs-lookup"><span data-stu-id="3afa8-104">Exposing .NET Core components to COM</span></span>

<span data-ttu-id="3afa8-105">.NET Core では、.NET Framework と比較し、.NET オブジェクトを COM に公開する工程が大幅に簡素化されています。</span><span class="sxs-lookup"><span data-stu-id="3afa8-105">In .NET Core, the process for exposing your .NET objects to COM has been significantly streamlined in comparison to .NET Framework.</span></span> <span data-ttu-id="3afa8-106">次の手順では、クラスを COM に公開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3afa8-106">The following process will walk you through how to expose a class to COM.</span></span> <span data-ttu-id="3afa8-107">このチュートリアルでは、次の方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="3afa8-107">This tutorial shows you how to:</span></span>

- <span data-ttu-id="3afa8-108">.NET Core から COM にクラスを公開します。</span><span class="sxs-lookup"><span data-stu-id="3afa8-108">Expose a class to COM from .NET Core.</span></span>
- <span data-ttu-id="3afa8-109">使用する .NET Core ライブラリをビルドする一環として、COM サーバーを生成します。</span><span class="sxs-lookup"><span data-stu-id="3afa8-109">Generate a COM server as part of building your .NET Core library.</span></span>
- <span data-ttu-id="3afa8-110">レジストリを使用しない COM 用の side-by-side サーバー マニフェストを自動生成します。</span><span class="sxs-lookup"><span data-stu-id="3afa8-110">Automatically generate a side-by-side server manifest for Registry-Free COM.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3afa8-111">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3afa8-111">Prerequisites</span></span>

- <span data-ttu-id="3afa8-112">[NET Core 3.0 SDK](https://dotnet.microsoft.com/download) 以降のバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3afa8-112">Install [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download) or a newer version.</span></span>

## <a name="create-the-library"></a><span data-ttu-id="3afa8-113">ライブラリを作成する</span><span class="sxs-lookup"><span data-stu-id="3afa8-113">Create the library</span></span>

<span data-ttu-id="3afa8-114">最初の手順では、ライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="3afa8-114">The first step is to create the library.</span></span>

1. <span data-ttu-id="3afa8-115">新しいフォルダーを作成し、そのフォルダーで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3afa8-115">Create a new folder, and in that folder run the following command:</span></span>

    ```dotnetcli
    dotnet new classlib
    ```

2. <span data-ttu-id="3afa8-116">`Class1.cs`を開きます。</span><span class="sxs-lookup"><span data-stu-id="3afa8-116">Open `Class1.cs`.</span></span>
3. <span data-ttu-id="3afa8-117">ファイルの先頭に、`using System.Runtime.InteropServices;` を追加します。</span><span class="sxs-lookup"><span data-stu-id="3afa8-117">Add `using System.Runtime.InteropServices;` to the top of the file.</span></span>
4. <span data-ttu-id="3afa8-118">`IServer` という名前のインターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="3afa8-118">Create an interface named `IServer`.</span></span> <span data-ttu-id="3afa8-119">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3afa8-119">For example:</span></span>

   ```csharp
   using System;
   using System.Runtime.InteropServices;

   [ComVisible(true)]
   [Guid(ContractGuids.ServerInterface)]
   [InterfaceType(ComInterfaceType.InterfaceIsIUnknown)]
   public interface IServer
   {
       /// <summary>
       /// Compute the value of the constant Pi.
       /// </summary>
       double ComputePi();
   }
   ```

5. <span data-ttu-id="3afa8-120">このインターフェイスに、実装する COM インターフェイス用のインターフェイス GUID を使用して、`[Guid("<IID>")]` 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="3afa8-120">Add the `[Guid("<IID>")]` attribute to the interface, with the interface GUID for the COM interface you're implementing.</span></span> <span data-ttu-id="3afa8-121">たとえば、`[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]` のようにします。</span><span class="sxs-lookup"><span data-stu-id="3afa8-121">For example, `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`.</span></span> <span data-ttu-id="3afa8-122">この GUID は、COM 用のこのインターフェイスの唯一の識別子であるため、一意である必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3afa8-122">Note that this GUID needs to be unique since it is the only identifier of this interface for COM.</span></span> <span data-ttu-id="3afa8-123">Visual Studio で GUID を作成するには、[ツール] > [GUID の作成] の順に移動して GUI の作成ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="3afa8-123">In Visual Studio, you can generate a GUID by going to Tools > Create GUID to open the Create GUID tool.</span></span>
6. <span data-ttu-id="3afa8-124">インターフェイスに `[InterfaceType]` 属性を追加し、お使いのインターフェイスで実装すべき基本 COM インターフェイスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3afa8-124">Add the `[InterfaceType]` attribute to the interface and specify what base COM interfaces your interface should implement.</span></span>
7. <span data-ttu-id="3afa8-125">`IServer` を実装する、`Server` という名前のクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="3afa8-125">Create a class named `Server` that implements `IServer`.</span></span>
8. <span data-ttu-id="3afa8-126">クラスに、実装する COM クラス用のクラス識別子 GUID を使用して、`[Guid("<CLSID>")]` 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="3afa8-126">Add the `[Guid("<CLSID>")]` attribute to the class, with the class identifier GUID for the COM class you're implementing.</span></span> <span data-ttu-id="3afa8-127">たとえば、`[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]` のようにします。</span><span class="sxs-lookup"><span data-stu-id="3afa8-127">For example, `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`.</span></span> <span data-ttu-id="3afa8-128">インターフェイス GUID でこの GUID は、COM ではこのインターフェイスの唯一の識別子であるため、一意である必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3afa8-128">As with the interface GUID, this GUID must be unique since it is the only identifier of this interface to COM.</span></span>
9. <span data-ttu-id="3afa8-129">インターフェイスとクラスの両方に `[ComVisible(true)]` 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="3afa8-129">Add the `[ComVisible(true)]` attribute to both the interface and the class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3afa8-130">.NET Framework とは異なり、.NET Core では COM を使用してアクティブ化したいすべてのクラスの CLSID を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3afa8-130">Unlike in .NET Framework, .NET Core requires you to specify the CLSID of any class you want to be activatable via COM.</span></span>

## <a name="generate-the-com-host"></a><span data-ttu-id="3afa8-131">COM ホストを生成する</span><span class="sxs-lookup"><span data-stu-id="3afa8-131">Generate the COM host</span></span>

1. <span data-ttu-id="3afa8-132">`.csproj` プロジェクト ファイルを開き、`<PropertyGroup></PropertyGroup>` タグの内側に `<EnableComHosting>true</EnableComHosting>` を追加します。</span><span class="sxs-lookup"><span data-stu-id="3afa8-132">Open the `.csproj` project file and add `<EnableComHosting>true</EnableComHosting>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="3afa8-133">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="3afa8-133">Build the project.</span></span>

<span data-ttu-id="3afa8-134">結果として、`ProjectName.dll`、`ProjectName.runtimeconfig.json`、`ProjectName.deps.json`、および`ProjectName.comhost.dll` ファイルが出力されます。</span><span class="sxs-lookup"><span data-stu-id="3afa8-134">The resulting output will have a `ProjectName.dll`, `ProjectName.deps.json`, `ProjectName.runtimeconfig.json` and `ProjectName.comhost.dll` file.</span></span>

## <a name="register-the-com-host-for-com"></a><span data-ttu-id="3afa8-135">COM 用の COM ホストを登録する</span><span class="sxs-lookup"><span data-stu-id="3afa8-135">Register the COM host for COM</span></span>

<span data-ttu-id="3afa8-136">管理者特権でのコマンド プロンプトを開き、`regsvr32 ProjectName.comhost.dll` を実行します。</span><span class="sxs-lookup"><span data-stu-id="3afa8-136">Open an elevated command prompt and run `regsvr32 ProjectName.comhost.dll`.</span></span> <span data-ttu-id="3afa8-137">これにより、公開されているすべての .NET オブジェクトが COM に登録されます。</span><span class="sxs-lookup"><span data-stu-id="3afa8-137">That will register all of your exposed .NET objects with COM.</span></span>

## <a name="enabling-regfree-com"></a><span data-ttu-id="3afa8-138">Regfree COM を有効にする</span><span class="sxs-lookup"><span data-stu-id="3afa8-138">Enabling RegFree COM</span></span>

1. <span data-ttu-id="3afa8-139">`.csproj` プロジェクト ファイルを開き、`<PropertyGroup></PropertyGroup>` タグの内側に `<EnableRegFreeCom>true</EnableRegFreeCom>` を追加します。</span><span class="sxs-lookup"><span data-stu-id="3afa8-139">Open the `.csproj` project file and add `<EnableRegFreeCom>true</EnableRegFreeCom>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="3afa8-140">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="3afa8-140">Build the project.</span></span>

<span data-ttu-id="3afa8-141">これで結果として、`ProjectName.X.manifest` ファイルも出力されます。</span><span class="sxs-lookup"><span data-stu-id="3afa8-141">The resulting output will now also have a `ProjectName.X.manifest` file.</span></span> <span data-ttu-id="3afa8-142">このファイルが、Registry-Free COM で使用される side-by-side マニフェストです。</span><span class="sxs-lookup"><span data-stu-id="3afa8-142">This file is the side-by-side manifest for use with Registry-Free COM.</span></span>

## <a name="sample"></a><span data-ttu-id="3afa8-143">サンプル</span><span class="sxs-lookup"><span data-stu-id="3afa8-143">Sample</span></span>

<span data-ttu-id="3afa8-144">GitHub の dotnet/samples リポジトリには、完全に機能する [COM サーバーのサンプル](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo)があります。</span><span class="sxs-lookup"><span data-stu-id="3afa8-144">There is a fully functional [COM server sample](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo) in the dotnet/samples repository on GitHub.</span></span>

## <a name="additional-notes"></a><span data-ttu-id="3afa8-145">補足メモ</span><span class="sxs-lookup"><span data-stu-id="3afa8-145">Additional notes</span></span>

<span data-ttu-id="3afa8-146">.NET Core では、.NET Framework とは異なり、.NET Core アセンブリからの COM タイプ ライブラリ (TLB) の生成はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3afa8-146">Unlike in .NET Framework, there is no support in .NET Core for generating a COM Type Library (TLB) from a .NET Core assembly.</span></span> <span data-ttu-id="3afa8-147">このガイダンスは、COM インターフェイスのネイティブ宣言のために、IDL ファイルまたは C/C++ ヘッダーを手動で記述する方法について説明するものです。</span><span class="sxs-lookup"><span data-stu-id="3afa8-147">The guidance is to either manually write an IDL file or a C/C++ header for the native declarations of the COM interfaces.</span></span>

<span data-ttu-id="3afa8-148">COM コンポーネントの[自己完結型の配置](../deploying/index.md#publish-self-contained)はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3afa8-148">[Self-contained deployments](../deploying/index.md#publish-self-contained) of COM components are not supported.</span></span> <span data-ttu-id="3afa8-149">COM コンポーネントの[ランタイムに依存する配置](../deploying/index.md#publish-runtime-dependent)のみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3afa8-149">Only [runtime-dependent deployments](../deploying/index.md#publish-runtime-dependent) of COM components are supported.</span></span>

<span data-ttu-id="3afa8-150">また、.NET Framework と .NET Core の両方を同じプロセスに読み込むと、診断が制限されます。</span><span class="sxs-lookup"><span data-stu-id="3afa8-150">Additionally, loading both .NET Framework and .NET Core into the same process does have diagnostic limitations.</span></span> <span data-ttu-id="3afa8-151">主にマネージド コンポーネントのデバッグが制限されます。これは、.NET Framework と .NET Core の両方を同時にデバッグすることはできないためです。</span><span class="sxs-lookup"><span data-stu-id="3afa8-151">The primary limitation is the debugging of managed components as it is not possible to debug both .NET Framework and .NET Core at the same time.</span></span> <span data-ttu-id="3afa8-152">また、2 つのランタイム インスタンスはマネージド アセンブリを共有しません。</span><span class="sxs-lookup"><span data-stu-id="3afa8-152">In addition, the two runtime instances don't share managed assemblies.</span></span> <span data-ttu-id="3afa8-153">つまり、2 つのランタイム間で実際の .NET 型を共有することはできません。代わりに、すべての対話を、公開されている COM インターフェイス コントラクトに制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3afa8-153">This means that it isn't possible to share actual .NET types across the two runtimes and instead all interactions must be restricted to the exposed COM interface contracts.</span></span>
