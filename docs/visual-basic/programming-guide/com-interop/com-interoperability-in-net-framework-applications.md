---
title: .NET Framework アプリケーションにおける COM 相互運用性
ms.date: 07/20/2015
helpviewer_keywords:
- interoperability, COM and .NET Framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
ms.openlocfilehash: 377958a21886fe0257633ea19417f9a19bd51ff3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396870"
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a><span data-ttu-id="f8394-102">.NET Framework アプリケーションにおける COM 相互運用性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8394-102">COM Interoperability in .NET Framework Applications (Visual Basic)</span></span>

<span data-ttu-id="f8394-103">COM オブジェクトと .NET Framework オブジェクトを同じアプリケーションで使用する場合は、オブジェクトがメモリ内にどのように存在するかの違いに対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8394-103">When you want to use COM objects and .NET Framework objects in the same application, you need to address the differences in how the objects exist in memory.</span></span> <span data-ttu-id="f8394-104">.NET Framework オブジェクトはマネージド メモリ (共通言語ランタイムによって制御されるメモリ) 内にあり、必要に応じてランタイムによって移動される場合があります。</span><span class="sxs-lookup"><span data-stu-id="f8394-104">A .NET Framework object is located in managed memory—the memory controlled by the common language runtime—and may be moved by the runtime as needed.</span></span> <span data-ttu-id="f8394-105">COM オブジェクトはアンマネージ メモリ内にあり、別のメモリの場所に移動することは想定されていません。</span><span class="sxs-lookup"><span data-stu-id="f8394-105">A COM object is located in unmanaged memory and is not expected to move to another memory location.</span></span> <span data-ttu-id="f8394-106">Visual Studio と .NET Framework には、これらのマネージド コンポーネントとアンマネージ コンポーネントの相互作用を制御するためのツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f8394-106">Visual Studio and the .NET Framework provide tools to control the interaction of these managed and unmanaged components.</span></span> <span data-ttu-id="f8394-107">詳細については、[共通言語ランタイム](../../../standard/clr.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8394-107">For more information about managed code, see [Common Language Runtime](../../../standard/clr.md).</span></span>

<span data-ttu-id="f8394-108">.NET アプリケーションで COM オブジェクトを使用するだけでなく、Visual Basic を使用して、COM を介してアンマネージ コードからアクセスできるオブジェクトを開発することもできます。</span><span class="sxs-lookup"><span data-stu-id="f8394-108">In addition to using COM objects in .NET applications, you may also want to use Visual Basic to develop objects accessible from unmanaged code through COM.</span></span>

<span data-ttu-id="f8394-109">このページのリンクを使用すると、COM オブジェクトと .NET Framework オブジェクトの間の相互作用についての詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8394-109">The links on this page provide details on the interactions between COM and .NET Framework objects.</span></span>

## <a name="related-sections"></a><span data-ttu-id="f8394-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8394-110">Related sections</span></span>

| | |
|---------|---------|
| [<span data-ttu-id="f8394-111">COM 相互運用</span><span class="sxs-lookup"><span data-stu-id="f8394-111">COM Interop</span></span>](index.md) | <span data-ttu-id="f8394-112">COM オブジェクト、ActiveX コントロール、Win32 DLL、マネージド オブジェクト、COM オブジェクトの継承など、Visual Basic の COM 相互運用性に関するトピックへのリンクが掲載されています。</span><span class="sxs-lookup"><span data-stu-id="f8394-112">Provides links to topics covering COM interoperability in Visual Basic, including COM objects, ActiveX controls, Win32 DLLs, managed objects, and inheritance of COM objects.</span></span> |
| [<span data-ttu-id="f8394-113">アンマネージ コードとの相互運用</span><span class="sxs-lookup"><span data-stu-id="f8394-113">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md) | <span data-ttu-id="f8394-114">マネージド コードとアンマネージ コードの間の相互作用の問題について簡単に説明し、さらに学習するためのリンクを掲載しています。</span><span class="sxs-lookup"><span data-stu-id="f8394-114">Briefly describes some of the interaction issues between managed and unmanaged code, and provides links for further study.</span></span> |
| [<span data-ttu-id="f8394-115">COM ラッパー</span><span class="sxs-lookup"><span data-stu-id="f8394-115">COM Wrappers</span></span>](../../../standard/native-interop/com-wrappers.md) | <span data-ttu-id="f8394-116">マネージド コードが COM メソッドを呼び出すことができるようにするランタイム呼び出し可能ラッパー、および COM クライアントが .NET オブジェクトのメソッドを呼び出すことができるようにする COM 呼び出し可能ラッパーについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="f8394-116">Discusses runtime callable wrappers, which allow managed code to call COM methods, and COM callable wrappers, which allow COM clients to call .NET object methods.</span></span> |
| [<span data-ttu-id="f8394-117">高度な COM 相互運用性</span><span class="sxs-lookup"><span data-stu-id="f8394-117">Advanced COM Interoperability</span></span>](../../../framework/interop/index.md) | <span data-ttu-id="f8394-118">ラッパー、例外、継承、スレッド処理、イベント、変換、およびマーシャリングに関して、COM の相互運用性に関するトピックへのリンクを掲載しています。</span><span class="sxs-lookup"><span data-stu-id="f8394-118">Provides links to topics covering COM interoperability with respect to wrappers, exceptions, inheritance, threading, events, conversions, and marshaling.</span></span> |
| [<span data-ttu-id="f8394-119">Tlbimp.exe (タイプ ライブラリ インポーター)</span><span class="sxs-lookup"><span data-stu-id="f8394-119">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md) | <span data-ttu-id="f8394-120">COM タイプ ライブラリにある型定義を共通言語ランタイム アセンブリで等価な定義に変換するために使用できるツールについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="f8394-120">Discusses the tool you can use to convert the type definitions found within a COM type library into equivalent definitions in a common language runtime assembly.</span></span> |
