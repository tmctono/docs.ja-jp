---
title: .NET Framework アプリケーションにおける COM 相互運用性 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
ms.openlocfilehash: 6e8b4eba40cc1872cb289ca120679bb951f2652a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022381"
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a><span data-ttu-id="20b7a-102">.NET Framework アプリケーションにおける COM 相互運用性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20b7a-102">COM Interoperability in .NET Framework Applications (Visual Basic)</span></span>

<span data-ttu-id="20b7a-103">同じアプリケーションで COM オブジェクトと .NET Framework オブジェクトを使用する場合は、メモリ内のオブジェクトの存在の違いに対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20b7a-103">When you want to use COM objects and .NET Framework objects in the same application, you need to address the differences in how the objects exist in memory.</span></span> <span data-ttu-id="20b7a-104">.NET Framework のオブジェクトは、マネージ メモリにある、共通言語ランタイムによって制御されるメモリ:、必要に応じて、ランタイムによって移動することがあります。</span><span class="sxs-lookup"><span data-stu-id="20b7a-104">A .NET Framework object is located in managed memory—the memory controlled by the common language runtime—and may be moved by the runtime as needed.</span></span> <span data-ttu-id="20b7a-105">COM オブジェクトでは、アンマネージ メモリ内にあるし、別のメモリ位置に移動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="20b7a-105">A COM object is located in unmanaged memory and is not expected to move to another memory location.</span></span> <span data-ttu-id="20b7a-106">Visual Studio と[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]これらの相互作用を制御するためのツールのマネージし、アンマネージ コンポーネントを提供します。</span><span class="sxs-lookup"><span data-stu-id="20b7a-106">Visual Studio and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provide tools to control the interaction of these managed and unmanaged components.</span></span> <span data-ttu-id="20b7a-107">マネージ コードの詳細については、次を参照してください。[共通言語ランタイム](../../../standard/clr.md)します。</span><span class="sxs-lookup"><span data-stu-id="20b7a-107">For more information about managed code, see [Common Language Runtime](../../../standard/clr.md).</span></span>

<span data-ttu-id="20b7a-108">.NET アプリケーションで COM オブジェクトを使用するだけでなくすることも Visual Basic を使用して、COM 経由のアンマネージ コードからアクセスできるオブジェクトを開発するには</span><span class="sxs-lookup"><span data-stu-id="20b7a-108">In addition to using COM objects in .NET applications, you may also want to use Visual Basic to develop objects accessible from unmanaged code through COM.</span></span>

<span data-ttu-id="20b7a-109">このページのリンクでは、COM と .NET Framework のオブジェクト間の相互作用の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="20b7a-109">The links on this page provide details on the interactions between COM and .NET Framework objects.</span></span>

## <a name="related-sections"></a><span data-ttu-id="20b7a-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="20b7a-110">Related sections</span></span>

| | |
|---------|---------|
| [<span data-ttu-id="20b7a-111">COM 相互運用</span><span class="sxs-lookup"><span data-stu-id="20b7a-111">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md) | <span data-ttu-id="20b7a-112">COM オブジェクト、ActiveX コントロール、Win32 の Dll、管理対象のオブジェクト、および COM オブジェクトの継承をなど、Visual Basic における COM 相互運用性を説明するトピックへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="20b7a-112">Provides links to topics covering COM interoperability in Visual Basic, including COM objects, ActiveX controls, Win32 DLLs, managed objects, and inheritance of COM objects.</span></span> |
| [<span data-ttu-id="20b7a-113">アンマネージ コードとの相互運用</span><span class="sxs-lookup"><span data-stu-id="20b7a-113">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md) | <span data-ttu-id="20b7a-114">簡単な説明、マネージとアンマネージ コード間の相互作用の問題の一部と、詳細情報へのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="20b7a-114">Briefly describes some of the interaction issues between managed and unmanaged code, and provides links for further study.</span></span> |
| [<span data-ttu-id="20b7a-115">COM ラッパー</span><span class="sxs-lookup"><span data-stu-id="20b7a-115">COM Wrappers</span></span>](../../../framework/interop/com-wrappers.md) | <span data-ttu-id="20b7a-116">マネージ コードから COM メソッドを呼び出すには、ランタイム呼び出し可能ラッパーを .NET オブジェクトのメソッドを呼び出す COM クライアントを許可する COM 呼び出し可能ラッパーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="20b7a-116">Discusses runtime callable wrappers, which allow managed code to call COM methods, and COM callable wrappers, which allow COM clients to call .NET object methods.</span></span> |
| [<span data-ttu-id="20b7a-117">高度な COM 相互運用性</span><span class="sxs-lookup"><span data-stu-id="20b7a-117">Advanced COM Interoperability</span></span>](../../../framework/interop/index.md) | <span data-ttu-id="20b7a-118">ラッパー、例外、継承、スレッド処理、イベント、変換、およびマーシャ リングに対して COM 相互運用性を説明するトピックへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="20b7a-118">Provides links to topics covering COM interoperability with respect to wrappers, exceptions, inheritance, threading, events, conversions, and marshaling.</span></span> |
| [<span data-ttu-id="20b7a-119">Tlbimp.exe (タイプ ライブラリ インポーター)</span><span class="sxs-lookup"><span data-stu-id="20b7a-119">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md) | <span data-ttu-id="20b7a-120">共通言語ランタイム アセンブリで等価な定義に COM タイプ ライブラリ内で見つかった種類の定義の変換に使用できるツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="20b7a-120">Discusses the tool you can use to convert the type definitions found within a COM type library into equivalent definitions in a common language runtime assembly.</span></span> |