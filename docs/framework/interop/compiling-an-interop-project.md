---
title: 相互運用プロジェクトのコンパイル
ms.date: 03/30/2017
helpviewer_keywords:
- interoperation with unmanaged code, compiling
- COM interop, compiling
- exposing COM components to .NET Framework
- compiling interop projects
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
ms.openlocfilehash: 32102910ae674a97e941e1346a1898585f503527
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123684"
---
# <a name="compiling-an-interop-project"></a><span data-ttu-id="44bc2-102">相互運用プロジェクトのコンパイル</span><span class="sxs-lookup"><span data-stu-id="44bc2-102">Compiling an Interop Project</span></span>

<span data-ttu-id="44bc2-103">インポートされた COM 型を含む 1 つ以上のアセンブリを参照する COM 相互運用プロジェクトは、他のマネージド プロジェクトと同じようにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="44bc2-103">COM interop projects that reference one or more assemblies containing imported COM types are compiled like any other managed project.</span></span> <span data-ttu-id="44bc2-104">相互運用機能アセンブリは、Visual Studio などの開発環境で参照できます。コマンド ライン コンパイラを使用して参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="44bc2-104">You can reference interop assemblies in a development environment such as Visual Studio, or you can reference them when you use a command-line compiler.</span></span> <span data-ttu-id="44bc2-105">どちらの場合でも、正常にコンパイルするには、相互運用機能アセンブリを、その他のプロジェクト ファイルと同じディレクトリに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44bc2-105">In either case, to compile properly, the interop assembly must be in the same directory as the other project files.</span></span>

 <span data-ttu-id="44bc2-106">相互運用機能アセンブリを参照する方法には、次の 2 つがあります。</span><span class="sxs-lookup"><span data-stu-id="44bc2-106">There are two ways to reference interop assemblies:</span></span>

- <span data-ttu-id="44bc2-107">埋め込まれた相互運用機能型: .NET Framework 4 と Visual Studio 2010 以降では、相互運用機能アセンブリから実行可能ファイルに型情報を埋め込むようにコンパイラに指示できます。</span><span class="sxs-lookup"><span data-stu-id="44bc2-107">Embedded interop types: Beginning with the .NET Framework 4 and Visual Studio 2010, you can instruct the compiler to embed type information from an interop assembly into your executable.</span></span> <span data-ttu-id="44bc2-108">この手法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="44bc2-108">This is the recommended technique.</span></span>

- <span data-ttu-id="44bc2-109">相互運用機能アセンブリの配置: 相互運用機能アセンブリへの標準の参照を作成できます。</span><span class="sxs-lookup"><span data-stu-id="44bc2-109">Deploying interop assemblies: You can create a standard reference to an interop assembly.</span></span> <span data-ttu-id="44bc2-110">この場合、アプリケーションで相互運用機能アセンブリを配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44bc2-110">In this case, the interop assembly must be deployed with your application.</span></span>

 <span data-ttu-id="44bc2-111">この 2 つの手法の違いの詳細については、「[Using COM Types in Managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))」(マネージド コードでの COM 型の使用) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44bc2-111">The differences between these two techniques are discussed in greater detail in [Using COM Types in Managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span></span>

 <span data-ttu-id="44bc2-112">Visual Studio での相互運用機能型の埋め込みについては、 [「チュートリアル: Visual studio におけるマネージアセンブリからの型の埋め込み](../../standard/assembly/embed-types-visual-studio.md)」で説明されています。</span><span class="sxs-lookup"><span data-stu-id="44bc2-112">Embedding interop types with Visual Studio is demonstrated in [Walkthrough: Embedding Types from Managed Assemblies in Visual Studio](../../standard/assembly/embed-types-visual-studio.md).</span></span>

 <span data-ttu-id="44bc2-113">コマンドラインコンパイラを使用して相互運用機能アセンブリを参照し、実行可能ファイルに型情報を埋め込むには、 [-link (C#コンパイラオプション)](../../csharp/language-reference/compiler-options/link-compiler-option.md)または[-link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md)コンパイラスイッチを使用して、相互運用機能アセンブリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="44bc2-113">To reference an interop assembly with a command-line compiler and embed type information in your executables, use the [-link (C# Compiler Options)](../../csharp/language-reference/compiler-options/link-compiler-option.md) or the [-link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) compiler switch and specify the name of the interop assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="44bc2-114">Visual C++ アプリケーションは型情報を埋め込むことはできませんが、型情報を埋め込むことができるアプリケーションまたはアドインと相互運用できます。</span><span class="sxs-lookup"><span data-stu-id="44bc2-114">Visual C++ applications cannot embed type information, but they can interoperate with applications or add-ins that do.</span></span>

 <span data-ttu-id="44bc2-115">配置時にプライマリ相互運用機能アセンブリを含むアプリケーションをコンパイルするには、 **/reference** コンパイラ スイッチを使用して、相互運用機能アセンブリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="44bc2-115">To compile an application that includes a primary interop assembly when it is deployed, use the **/reference** compiler switch and specify the name of the interop assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="44bc2-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="44bc2-116">See also</span></span>

- [<span data-ttu-id="44bc2-117">.NET Framework への COM コンポーネントの公開</span><span class="sxs-lookup"><span data-stu-id="44bc2-117">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
- [<span data-ttu-id="44bc2-118">言語への非依存性、および言語非依存コンポーネント</span><span class="sxs-lookup"><span data-stu-id="44bc2-118">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)
- <span data-ttu-id="44bc2-119">[マネージド コードでの COM 型の使用](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="44bc2-119">[Using COM Types in Managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))</span></span>
- [<span data-ttu-id="44bc2-120">チュートリアル: マネージド アセンブリからの型の埋め込み (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="44bc2-120">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio</span></span>](../../standard/assembly/embed-types-visual-studio.md)
- [<span data-ttu-id="44bc2-121">タイプ ライブラリのアセンブリとしてのインポート</span><span class="sxs-lookup"><span data-stu-id="44bc2-121">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
