---
title: アンマネージド ライブラリの読み込みアルゴリズム - .NET Core
description: .NET Core でのアンマネージド アセンブリ読み込みアルゴリズムの詳細の説明
ms.date: 10/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: c651aa6e0f37a968e6f8b26d1909def6fa488ccd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "72303696"
---
# <a name="unmanaged-native-library-loading-algorithm"></a><span data-ttu-id="2c7cb-103">アンマネージド (ネイティブ) ライブラリの読み込みアルゴリズム</span><span class="sxs-lookup"><span data-stu-id="2c7cb-103">Unmanaged (native) library loading algorithm</span></span>

<span data-ttu-id="2c7cb-104">アンマネージド ライブラリは、さまざまな段階を伴うアルゴリズムを使用して検出され、読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="2c7cb-104">Unmanaged libraries are located and loaded with an algorithm involving various stages.</span></span>

<span data-ttu-id="2c7cb-105">次のアルゴリズムでは、`PInvoke` によってネイティブ ライブラリがどのように読み込まれるかを説明します。</span><span class="sxs-lookup"><span data-stu-id="2c7cb-105">The following algorithm describes how native libraries are loaded through `PInvoke`.</span></span>

## <a name="pinvoke-load-library-algorithm"></a><span data-ttu-id="2c7cb-106">`PInvoke` のライブラリ読み込みアルゴリズム</span><span class="sxs-lookup"><span data-stu-id="2c7cb-106">`PInvoke` load library algorithm</span></span>

<span data-ttu-id="2c7cb-107">`PInvoke` では、アンマネージド アセンブリを読み込むときに、次のアルゴリズムが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2c7cb-107">`PInvoke` uses the following algorithm when attempting to load an unmanaged assembly:</span></span>

1. <span data-ttu-id="2c7cb-108">`active` <xref:System.Runtime.Loader.AssemblyLoadContext> を決定します。</span><span class="sxs-lookup"><span data-stu-id="2c7cb-108">Determine the `active` <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="2c7cb-109">アンマネージド ライブラリ読み込みの場合、`active` AssemblyLoadContext が、`PInvoke` を定義するアセンブリを持っています。</span><span class="sxs-lookup"><span data-stu-id="2c7cb-109">For an unmanaged load library, the `active` AssemblyLoadContext is the one with the assembly that defines the `PInvoke`.</span></span>

2. <span data-ttu-id="2c7cb-110">`active` <xref:System.Runtime.Loader.AssemblyLoadContext> について、次の優先順位に従ってアセンブリを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7cb-110">For the `active` <xref:System.Runtime.Loader.AssemblyLoadContext>, try to find the assembly in priority order by:</span></span>
    * <span data-ttu-id="2c7cb-111">キャッシュを調べます。</span><span class="sxs-lookup"><span data-stu-id="2c7cb-111">Checking its cache.</span></span>

    * <span data-ttu-id="2c7cb-112"><xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType> 関数によって設定された現在の <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType> デリゲートを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2c7cb-112">Calling the current <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType> delegate set by the <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType> function.</span></span>

    * <span data-ttu-id="2c7cb-113">`active` AssemblyLoadContext で <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType> 関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2c7cb-113">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType> function on the `active` AssemblyLoadContext.</span></span>

    * <span data-ttu-id="2c7cb-114"><xref:System.AppDomain> インスタンスのキャッシュを確認し、[アンマネージ (ネイティブ) ライブラリプローブ](default-probing.md#unmanaged-native-library-probing) ロジックを実行します。</span><span class="sxs-lookup"><span data-stu-id="2c7cb-114">Checking the <xref:System.AppDomain> instance's cache and running the [Unmanaged (native) library probing](default-probing.md#unmanaged-native-library-probing) logic.</span></span>

    * <span data-ttu-id="2c7cb-115">`active` AssemblyLoadContext の <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType> イベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="2c7cb-115">Raising the <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType> event for the `active` AssemblyLoadContext.</span></span>
