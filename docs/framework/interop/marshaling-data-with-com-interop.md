---
title: COM 相互運用機能によるデータのマーシャリング
ms.date: 09/07/2017
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 807e514fac7d33cdacac3a48a37c7aa8dd92ef9c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648642"
---
# <a name="marshaling-data-with-com-interop"></a><span data-ttu-id="259a7-102">COM 相互運用機能によるデータのマーシャリング</span><span class="sxs-lookup"><span data-stu-id="259a7-102">Marshaling Data with COM Interop</span></span>
<span data-ttu-id="259a7-103">COM 相互運用は、マネージド コードから COM オブジェクトを使用すること、およびマネージド オブジェクトを COM に公開することの、両方の操作をサポートします。</span><span class="sxs-lookup"><span data-stu-id="259a7-103">COM interop provides support for both using COM objects from managed code and exposing managed objects to COM.</span></span> <span data-ttu-id="259a7-104">COM との間でデータをマーシャリングする操作のサポートは広範で、ほとんどの場合、正しいマーシャリング動作が提供されます。</span><span class="sxs-lookup"><span data-stu-id="259a7-104">Support for marshaling data to and from COM is extensive and almost always provides the correct marshaling behavior.</span></span>  
  
 <span data-ttu-id="259a7-105">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] には、以下の COM 相互運用ツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="259a7-105">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] includes the following COM interop tools:</span></span>  
  
- <span data-ttu-id="259a7-106">[タイプ ライブラリ インポーター (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)、これは COM タイプ ライブラリを相互運用アセンブリに変換します。</span><span class="sxs-lookup"><span data-stu-id="259a7-106">[Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), which converts a COM type library to an interop assembly.</span></span> <span data-ttu-id="259a7-107">このアセンブリから、相互運用マーシャリング サービスは、マネージド メモリとアンマネージド メモリ間のデータ マーシャリングを実行するラッパーを生成します。</span><span class="sxs-lookup"><span data-stu-id="259a7-107">From this assembly, the interop marshaling service generates wrappers that perform data marshaling between managed and unmanaged memory.</span></span>  
  
- <span data-ttu-id="259a7-108">[タイプ ライブラリ エクスポーター (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)、これは COM タイプ ライブラリをアセンブリから生成して、メソッド呼び出しの際にマーシャリングを実行するラッパーを生成します。</span><span class="sxs-lookup"><span data-stu-id="259a7-108">[Type Library Exporter (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which produces a COM type library from an assembly and generates a wrapper that performs marshaling during method calls.</span></span>  
  
 <span data-ttu-id="259a7-109">以下のセクションは、マーシャラーに追加の型情報を提供できる (またはその必要がある) ときに、相互運用ラッパーをカスタマイズするためのプロセスについて説明するトピックにリンクしています。</span><span class="sxs-lookup"><span data-stu-id="259a7-109">The following sections link to topics that describe the processes for customizing interop wrappers when you can (or must) supply the marshaler with additional type information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="259a7-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="259a7-110">In This Section</span></span>  
<span data-ttu-id="259a7-111">[方法: ラッパーを手動で作成する](how-to-create-wrappers-manually.md) </span><span class="sxs-lookup"><span data-stu-id="259a7-111">[How to: Create Wrappers Manually](how-to-create-wrappers-manually.md) </span></span>  
<span data-ttu-id="259a7-112">マネージド ソース コードにおいて COM ラッパーを手動で作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="259a7-112">Describes how to create a COM wrapper manually in managed source code.</span></span> 
 
 [<span data-ttu-id="259a7-113">方法: マネージド コード DCOM を WCF に移行する</span><span class="sxs-lookup"><span data-stu-id="259a7-113">How to: Migrate Managed-Code DCOM to WCF</span></span>](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 <span data-ttu-id="259a7-114">最も安全なソリューションのために、マネージド DCOM コードを WCF に移行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="259a7-114">Describes how to migrate managed DCOM code to WCF for the most secure solution.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="259a7-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="259a7-115">Related Sections</span></span>  
 <span data-ttu-id="259a7-116">[COM のデータ型](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="259a7-116">[COM Data Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span></span>  
 <span data-ttu-id="259a7-117">対応するマネージドとアンマネージドのデータ型を提供します。</span><span class="sxs-lookup"><span data-stu-id="259a7-117">Provides corresponding managed and unmanaged data types.</span></span>  
  
 <span data-ttu-id="259a7-118">[COM 呼び出し可能ラッパーのカスタマイズ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3bwc828w(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="259a7-118">[Customizing COM Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3bwc828w(v=vs.100))</span></span>  
 <span data-ttu-id="259a7-119">デザイン時に <xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性を使用して、データ型を明示的にマーシャリングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="259a7-119">Describes how to explicitly marshal data types using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute at design time.</span></span>  
  
 <span data-ttu-id="259a7-120">[ランタイム呼び出し可能ラッパーのカスタマイズ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="259a7-120">[Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span></span>  
 <span data-ttu-id="259a7-121">相互運用アセンブリで型のマーシャリング動作を調整する方法、および COM 型を手動で定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="259a7-121">Describes how to adjust the marshaling behavior of types in an interop assembly and how to define COM types manually.</span></span>  
  
 <span data-ttu-id="259a7-122">[高度な COM 相互運用性](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="259a7-122">[Advanced COM Interoperability](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>  
 <span data-ttu-id="259a7-123">.NET Framework アプリケーションに COM コンポーネントを組み込む方法についての詳細情報へのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="259a7-123">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>  
  
 <span data-ttu-id="259a7-124">[アセンブリからタイプ ライブラリへの変換の要約](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="259a7-124">[Assembly to Type Library Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))</span></span>  
 <span data-ttu-id="259a7-125">アセンブリからタイプ ライブラリにエクスポート変換するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="259a7-125">Describes the assembly to type library export conversion process.</span></span>  
  
 <span data-ttu-id="259a7-126">[タイプ ライブラリからアセンブリへの変換の要約](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="259a7-126">[Type Library to Assembly Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span></span>  
 <span data-ttu-id="259a7-127">タイプ ライブラリからアセンブリにインポート変換するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="259a7-127">Describes the type library to assembly import conversion process.</span></span>  
  
 <span data-ttu-id="259a7-128">[ジェネリック型を使用する相互運用](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="259a7-128">[Interoperating Using Generic Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))</span></span>  
 <span data-ttu-id="259a7-129">COM 相互運用性のジェネリック型を使用するとき、どのアクションがサポートされるかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="259a7-129">Describes which actions are supported when using generic types for COM interoperability.</span></span>
