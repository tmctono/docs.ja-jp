---
title: COM への .NET Framework コンポーネントの公開
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b2b2f550b21a8d64968c6280cc1a29c1d18bfabd
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364013"
---
# <a name="exposing-net-framework-components-to-com"></a><span data-ttu-id="4d835-102">COM への .NET Framework コンポーネントの公開</span><span class="sxs-lookup"><span data-stu-id="4d835-102">Exposing .NET Framework Components to COM</span></span>
<span data-ttu-id="4d835-103">.NET 型の記述とその型をアンマネージ コードから使用することは、開発者にとっては個別のアクティビティです。</span><span class="sxs-lookup"><span data-stu-id="4d835-103">Writing a .NET type and consuming that type from unmanaged code are distinct activities for developers.</span></span> <span data-ttu-id="4d835-104">このセクションでは、COM クライアントと相互運用するマネージド コードの記述のためのいくつかのヒントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4d835-104">This section describes several tips for writing managed code that interoperates with COM clients:</span></span>  
  
- <span data-ttu-id="4d835-105">[相互運用のための .NET 型の要件を満たす](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md)。</span><span class="sxs-lookup"><span data-stu-id="4d835-105">[Qualifying .NET types for interoperation](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md).</span></span>  
  
     <span data-ttu-id="4d835-106">COM に対して公開するすべてのマネージド型、マネージド メソッド、マネージド プロパティ、マネージド フィールド、およびマネージド イベントは、パブリックとしてください。</span><span class="sxs-lookup"><span data-stu-id="4d835-106">All managed types, methods, properties, fields, and events that you want to expose to COM must be public.</span></span> <span data-ttu-id="4d835-107">型には、パラメーターなしのパブリック コンストラクターが含まれている必要があります。これは COM を通じて呼び出すことができる唯一のコンストラクターです。</span><span class="sxs-lookup"><span data-stu-id="4d835-107">Types must have a public parameterless constructor, which is the only constructor that can be invoked through COM.</span></span>  
  
- <span data-ttu-id="4d835-108">[相互運用属性を適用する](../../../docs/framework/interop/applying-interop-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="4d835-108">[Applying interop attributes](../../../docs/framework/interop/applying-interop-attributes.md).</span></span>  
  
     <span data-ttu-id="4d835-109">マネージド コード内のカスタム属性は、コンポーネントの相互運用性を強化できます。</span><span class="sxs-lookup"><span data-stu-id="4d835-109">Custom attributes within managed code can enhance the interoperability of a component.</span></span>  
  
- <span data-ttu-id="4d835-110">[COM 用にアセンブリをパッケージ化する](../../../docs/framework/interop/packaging-an-assembly-for-com.md)。</span><span class="sxs-lookup"><span data-stu-id="4d835-110">[Packaging an assembly for COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md).</span></span>  
  
     <span data-ttu-id="4d835-111">COM 開発者から、アセンブリの参照と展開に必要な手順をまとめるように求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4d835-111">COM developers might require that you summarize the steps involved in referencing and deploying your assemblies.</span></span>  
  
 <span data-ttu-id="4d835-112">さらに、このセクションでは、COM クライアントからマネージド型の使用に関連するタスクを明らかにします。</span><span class="sxs-lookup"><span data-stu-id="4d835-112">Additionally, this section identifies the tasks related to consuming a managed type from a COM client.</span></span>  
  
#### <a name="to-consume-a-managed-type-from-com"></a><span data-ttu-id="4d835-113">COM からマネージド型を使用するには</span><span class="sxs-lookup"><span data-stu-id="4d835-113">To consume a managed type from COM</span></span>  
  
1. <span data-ttu-id="4d835-114">[COM にアセンブリを登録する](../../../docs/framework/interop/registering-assemblies-with-com.md)。</span><span class="sxs-lookup"><span data-stu-id="4d835-114">[Register assemblies with COM](../../../docs/framework/interop/registering-assemblies-with-com.md).</span></span>  
  
     <span data-ttu-id="4d835-115">アセンブリ (およびタイプ ライブラリ) 内の型は、デザイン時に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d835-115">Types in an assembly (and type libraries) must be registered at design time.</span></span> <span data-ttu-id="4d835-116">インストーラーでアセンブリが登録されない場合は、Regasm.exe を使用するように COM 開発者に指示します。</span><span class="sxs-lookup"><span data-stu-id="4d835-116">If an installer does not register the assembly, instruct COM developers to use Regasm.exe.</span></span>  
  
2. <span data-ttu-id="4d835-117">[COM から .NET 型を参照する](../../../docs/framework/interop/how-to-reference-net-types-from-com.md)。</span><span class="sxs-lookup"><span data-stu-id="4d835-117">[Reference .NET types from COM](../../../docs/framework/interop/how-to-reference-net-types-from-com.md).</span></span>  
  
     <span data-ttu-id="4d835-118">COM 開発者は、現在使用しているのと同じツールと手法を使用して、アセンブリ内の型を参照できます。</span><span class="sxs-lookup"><span data-stu-id="4d835-118">COM developers can reference types in an assembly using the same tools and techniques they use today.</span></span>  
  
3. <span data-ttu-id="4d835-119">[.NET オブジェクトを呼び出す](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="4d835-119">[Call a .NET object](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100)).</span></span>  
  
     <span data-ttu-id="4d835-120">COM 開発者は、アンマネージ型でメソッドを呼び出すのと同じ方法で、.NET オブジェクトでメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="4d835-120">COM developers can call methods on the .NET object the same way they call methods on any unmanaged type.</span></span> <span data-ttu-id="4d835-121">たとえば、COM **CoCreateInstance** API は、.NET オブジェクトをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="4d835-121">For example, the COM **CoCreateInstance** API activates .NET objects.</span></span>  
  
4. <span data-ttu-id="4d835-122">[COM アクセスに対してアプリケーションを展開する](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="4d835-122">[Deploy an application for COM access](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100)).</span></span>  
  
     <span data-ttu-id="4d835-123">厳格な名前付きのアセンブリは、グローバル アセンブリ キャッシュにインストールすることができ、発行元からの署名が必要です。</span><span class="sxs-lookup"><span data-stu-id="4d835-123">A strong-named assembly can be installed in the global assembly cache and requires a signature from its publisher.</span></span> <span data-ttu-id="4d835-124">厳密な名前のないアセンブリは、クライアントのアプリケーション ディレクトリにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d835-124">Assemblies that are not strong named must be installed in the application directory of the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d835-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d835-125">See also</span></span>

- [<span data-ttu-id="4d835-126">アンマネージ コードとの相互運用</span><span class="sxs-lookup"><span data-stu-id="4d835-126">Interoperating with Unmanaged Code</span></span>](../../../docs/framework/interop/index.md)
- [<span data-ttu-id="4d835-127">COM 相互運用機能のサンプル:COM クライアントおよび .NET サーバー</span><span class="sxs-lookup"><span data-stu-id="4d835-127">COM Interop Sample: COM Client and .NET Server</span></span>](../../../docs/framework/interop/com-interop-sample-com-client-and-net-server.md)
