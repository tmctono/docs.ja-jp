---
title: '方法: COM から .NET 型を参照する'
description: COM から .NET 型を参照します。 VB クライアントはオブジェクト ブラウザーで .NET オブジェクトを表示できますが、C++ クライアントは \#import ディレクティブを使用して TLB ファイルを参照する必要があります。
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- importing type library
- COM interop, referencing .NET types
- interoperation with unmanaged code, referencing .NET types
- referencing .NET types
- interoperation with unmanaged code, importing type library
- type libraries
- COM interop, importing type library
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
ms.openlocfilehash: fad0a8163bd3d023911fd8554a77f740ac010ee6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547246"
---
# <a name="how-to-reference-net-types-from-com"></a><span data-ttu-id="1b554-104">方法: COM から .NET 型を参照する</span><span class="sxs-lookup"><span data-stu-id="1b554-104">How to: Reference .NET Types from COM</span></span>
<span data-ttu-id="1b554-105">クライアント アンド サーバー コードの観点からすると、COM と .NET Framework の違いはほとんどわかりません。</span><span class="sxs-lookup"><span data-stu-id="1b554-105">From the point of view of client and server code, the differences between COM and the .NET Framework are largely invisible.</span></span> <span data-ttu-id="1b554-106">Microsoft Visual Basic クライアントでは、オブジェクト ブラウザーを使って .NET オブジェクトを表示できます。オブジェクト ブラウザーには、オブジェクトのメソッドと構文、プロパティ、およびフィールドが、他の COM オブジェクトの場合と同様に公開されます。</span><span class="sxs-lookup"><span data-stu-id="1b554-106">Microsoft Visual Basic clients can view a .NET object in the object browser, which exposes the object methods and syntax, properties, and fields exactly as if it were any other COM object.</span></span>  
  
 <span data-ttu-id="1b554-107">タイプ ライブラリのインポート処理は、COM タイプ ライブラリにメタデータをエクスポートする場合と同じツールを使用しますが、C++ クライアントの場合の方がやや複雑です。</span><span class="sxs-lookup"><span data-stu-id="1b554-107">The process for importing a type library is slightly more complicated for C++ clients, although you use the same tools to export metadata to a COM type library.</span></span> <span data-ttu-id="1b554-108">アンマネージ C++ クライアントから .NET オブジェクトのメンバーを参照するには、 **#import** ディレクティブが含まれている TLB ファイル (Tlbexp.exe により生成) を参照します。</span><span class="sxs-lookup"><span data-stu-id="1b554-108">To reference .NET object members from an unmanaged C++ client, reference the TLB file (produced with Tlbexp.exe) with the **#import** directive.</span></span> <span data-ttu-id="1b554-109">C++ からタイプ ライブラリを参照する場合は、**raw_interfaces_only** オプションを指定するか、または基本クラス ライブラリの Mscorlib.tlb 内の定義をインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b554-109">When referencing a type library from C++, you must either specify the **raw_interfaces_only** option or import the definitions in the base class library, Mscorlib.tlb.</span></span>  
  
### <a name="to-import-a-library"></a><span data-ttu-id="1b554-110">ライブラリをインポートするには</span><span class="sxs-lookup"><span data-stu-id="1b554-110">To import a library</span></span>  
  
- <span data-ttu-id="1b554-111">**#import** ディレクティブで **raw_interfaces_only** オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="1b554-111">Specify the **raw_interfaces_only** option in the **#import** directive.</span></span> <span data-ttu-id="1b554-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1b554-112">For example:</span></span>  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     <span data-ttu-id="1b554-113">\- または -</span><span class="sxs-lookup"><span data-stu-id="1b554-113">-or-</span></span>  
  
- <span data-ttu-id="1b554-114">Mscorlib.tlb の #import ディレクティブを含めます。</span><span class="sxs-lookup"><span data-stu-id="1b554-114">Include an #import directive for Mscorlib.tlb.</span></span> <span data-ttu-id="1b554-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1b554-115">For example:</span></span>  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1b554-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b554-116">See also</span></span>

- [<span data-ttu-id="1b554-117">COM への .NET Framework コンポーネントの公開</span><span class="sxs-lookup"><span data-stu-id="1b554-117">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="1b554-118">COM へのアセンブリの登録</span><span class="sxs-lookup"><span data-stu-id="1b554-118">Registering Assemblies with COM</span></span>](registering-assemblies-with-com.md)
- <span data-ttu-id="1b554-119">[.NET オブジェクトの呼び出し](/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1b554-119">[Calling a .NET Object](/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))</span></span>
- <span data-ttu-id="1b554-120">[COM アクセスに対するアプリケーションの配置](/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1b554-120">[Deploying an Application for COM Access](/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))</span></span>
