---
title: '方法: COM から .NET 型を参照する'
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 081548f9004d2fedf4d49845d3f44d4609fa508e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626303"
---
# <a name="how-to-reference-net-types-from-com"></a><span data-ttu-id="c6342-102">方法: COM から .NET 型を参照する</span><span class="sxs-lookup"><span data-stu-id="c6342-102">How to: Reference .NET Types from COM</span></span>
<span data-ttu-id="c6342-103">クライアント アンド サーバー コードの観点からすると、COM と .NET Framework の違いはほとんどわかりません。</span><span class="sxs-lookup"><span data-stu-id="c6342-103">From the point of view of client and server code, the differences between COM and the .NET Framework are largely invisible.</span></span> <span data-ttu-id="c6342-104">Microsoft Visual Basic クライアントでは、オブジェクト ブラウザーを使って .NET オブジェクトを表示できます。オブジェクト ブラウザーには、オブジェクトのメソッドと構文、プロパティ、およびフィールドが、他の COM オブジェクトの場合と同様に公開されます。</span><span class="sxs-lookup"><span data-stu-id="c6342-104">Microsoft Visual Basic clients can view a .NET object in the object browser, which exposes the object methods and syntax, properties, and fields exactly as if it were any other COM object.</span></span>  
  
 <span data-ttu-id="c6342-105">タイプ ライブラリのインポート処理は、COM タイプ ライブラリにメタデータをエクスポートする場合と同じツールを使用しますが、C++ クライアントの場合の方がやや複雑です。</span><span class="sxs-lookup"><span data-stu-id="c6342-105">The process for importing a type library is slightly more complicated for C++ clients, although you use the same tools to export metadata to a COM type library.</span></span> <span data-ttu-id="c6342-106">アンマネージ C++ クライアントから .NET オブジェクトのメンバーを参照するには、**#import** ディレクティブが含まれている TLB ファイル (Tlbexp.exe により生成) を参照します。</span><span class="sxs-lookup"><span data-stu-id="c6342-106">To reference .NET object members from an unmanaged C++ client, reference the TLB file (produced with Tlbexp.exe) with the **#import** directive.</span></span> <span data-ttu-id="c6342-107">C++ からタイプ ライブラリを参照する場合は、**raw_interfaces_only** オプションを指定するか、または基本クラス ライブラリの Mscorlib.tlb 内の定義をインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6342-107">When referencing a type library from C++, you must either specify the **raw_interfaces_only** option or import the definitions in the base class library, Mscorlib.tlb.</span></span>  
  
### <a name="to-import-a-library"></a><span data-ttu-id="c6342-108">ライブラリをインポートするには</span><span class="sxs-lookup"><span data-stu-id="c6342-108">To import a library</span></span>  
  
- <span data-ttu-id="c6342-109">**#import** ディレクティブで **raw_interfaces_only** オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c6342-109">Specify the **raw_interfaces_only** option in the **#import** directive.</span></span> <span data-ttu-id="c6342-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c6342-110">For example:</span></span>  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     <span data-ttu-id="c6342-111">- または -</span><span class="sxs-lookup"><span data-stu-id="c6342-111">-or-</span></span>  
  
- <span data-ttu-id="c6342-112">Mscorlib.tlb の #import ディレクティブを含めます。</span><span class="sxs-lookup"><span data-stu-id="c6342-112">Include an #import directive for Mscorlib.tlb.</span></span> <span data-ttu-id="c6342-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c6342-113">For example:</span></span>  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c6342-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6342-114">See also</span></span>

- [<span data-ttu-id="c6342-115">COM への .NET Framework コンポーネントの公開</span><span class="sxs-lookup"><span data-stu-id="c6342-115">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="c6342-116">COM へのアセンブリの登録</span><span class="sxs-lookup"><span data-stu-id="c6342-116">Registering Assemblies with COM</span></span>](registering-assemblies-with-com.md)
- <span data-ttu-id="c6342-117">[.NET オブジェクトの呼び出し](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c6342-117">[Calling a .NET Object](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))</span></span>
- <span data-ttu-id="c6342-118">[COM アクセスに対するアプリケーションの配置](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c6342-118">[Deploying an Application for COM Access](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))</span></span>
