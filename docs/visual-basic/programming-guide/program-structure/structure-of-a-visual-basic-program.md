---
title: Visual Basic プログラムの構造
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], Visual Basic
- program structure [Visual Basic], Visual Basic
- procedures [Visual Basic], structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
ms.openlocfilehash: dc6b38d78f02a42c8e7cc2aa964e9f3f74996f44
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408765"
---
# <a name="structure-of-a-visual-basic-program"></a><span data-ttu-id="d1daa-102">Visual Basic プログラムの構造</span><span class="sxs-lookup"><span data-stu-id="d1daa-102">Structure of a Visual Basic Program</span></span>
<span data-ttu-id="d1daa-103">Visual Basic プログラムは、標準の構成要素から構築します。</span><span class="sxs-lookup"><span data-stu-id="d1daa-103">A Visual Basic program is built up from standard building blocks.</span></span> <span data-ttu-id="d1daa-104">"*ソリューション*" は、1 つ以上のプロジェクトで構成します。</span><span class="sxs-lookup"><span data-stu-id="d1daa-104">A *solution* comprises one or more projects.</span></span> <span data-ttu-id="d1daa-105">"*プロジェクト*" には、1 つ以上のアセンブリを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d1daa-105">A *project* in turn can contain one or more assemblies.</span></span> <span data-ttu-id="d1daa-106">各 "*アセンブリ*" は、1 つ以上のソース ファイルからコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="d1daa-106">Each *assembly* is compiled from one or more source files.</span></span> <span data-ttu-id="d1daa-107">"*ソース ファイル*" では、クラス、構造体、モジュール、インターフェイスの定義と実装が提供され、最終的にはすべてのコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d1daa-107">A *source file* provides the definition and implementation of classes, structures, modules, and interfaces, which ultimately contain all your code.</span></span>  
  
 <span data-ttu-id="d1daa-108">Visual Basic プログラムのこれらの構成要素の詳細については、[ソリューションとプロジェクト](/visualstudio/ide/solutions-and-projects-in-visual-studio)および [.NET のアセンブリ](../../../standard/assembly/index.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d1daa-108">For more information about these building blocks of a Visual Basic program, see [Solutions and Projects](/visualstudio/ide/solutions-and-projects-in-visual-studio) and [Assemblies in .NET](../../../standard/assembly/index.md).</span></span>  
  
## <a name="file-level-programming-elements"></a><span data-ttu-id="d1daa-109">ファイルレベルのプログラミング要素</span><span class="sxs-lookup"><span data-stu-id="d1daa-109">File-Level Programming Elements</span></span>  
 <span data-ttu-id="d1daa-110">プロジェクトまたはファイルを起動してコード エディターを開くと、いくつかのコードが既に配置され、正しい順序で表示されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="d1daa-110">When you start a project or file and open the code editor, you see some code already in place and in the correct order.</span></span> <span data-ttu-id="d1daa-111">記述するすべてのコードで、次のシーケンスに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1daa-111">Any code that you write should follow the following sequence:</span></span>  
  
1. <span data-ttu-id="d1daa-112">`Option` ステートメント</span><span class="sxs-lookup"><span data-stu-id="d1daa-112">`Option` statements</span></span>  
  
2. <span data-ttu-id="d1daa-113">`Imports` ステートメント</span><span class="sxs-lookup"><span data-stu-id="d1daa-113">`Imports` statements</span></span>  
  
3. <span data-ttu-id="d1daa-114">`Namespace` ステートメントと名前空間レベルの要素</span><span class="sxs-lookup"><span data-stu-id="d1daa-114">`Namespace` statements and namespace-level elements</span></span>  
  
 <span data-ttu-id="d1daa-115">ステートメントを異なる順序で入力すると、コンパイル エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d1daa-115">If you enter statements in a different order, compilation errors can result.</span></span>  
  
 <span data-ttu-id="d1daa-116">プログラムには、条件付きコンパイル ステートメントを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="d1daa-116">A program can also contain conditional compilation statements.</span></span> <span data-ttu-id="d1daa-117">ソース ファイル内で、前のシーケンスのステートメントの間にこれらを挿入することができます。</span><span class="sxs-lookup"><span data-stu-id="d1daa-117">You can intersperse these in the source file among the statements of the preceding sequence.</span></span>  
  
### <a name="option-statements"></a><span data-ttu-id="d1daa-118">Option ステートメント</span><span class="sxs-lookup"><span data-stu-id="d1daa-118">Option Statements</span></span>  
 <span data-ttu-id="d1daa-119">`Option` ステートメントを使用すると、後続のコードに対して基本ルールを確立し、構文エラーと論理エラーを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="d1daa-119">`Option` statements establish ground rules for subsequent code, helping prevent syntax and logic errors.</span></span> <span data-ttu-id="d1daa-120">[Option Explicit ステートメント](../../language-reference/statements/option-explicit-statement.md)を使用すると、すべての変数の宣言とスペルが正しいことを保証できるため、デバッグ時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="d1daa-120">The [Option Explicit Statement](../../language-reference/statements/option-explicit-statement.md) ensures that all variables are declared and spelled correctly, which reduces debugging time.</span></span> <span data-ttu-id="d1daa-121">[Option Strict ステートメント](../../language-reference/statements/option-strict-statement.md)を使用すると、データ型が異なる変数間の処理で発生する可能性がある論理エラーとデータ損失を最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="d1daa-121">The [Option Strict Statement](../../language-reference/statements/option-strict-statement.md) helps to minimize logic errors and data loss that can occur when you work between variables of different data types.</span></span> <span data-ttu-id="d1daa-122">[Option Compare ステートメント](../../language-reference/statements/option-compare-statement.md)では、文字列を `Binary` または `Text` の値に基づいて相互比較する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1daa-122">The [Option Compare Statement](../../language-reference/statements/option-compare-statement.md) specifies the way strings are compared to each other, based on either their `Binary` or `Text` values.</span></span>  
  
### <a name="imports-statements"></a><span data-ttu-id="d1daa-123">Imports ステートメント</span><span class="sxs-lookup"><span data-stu-id="d1daa-123">Imports Statements</span></span>  
 <span data-ttu-id="d1daa-124">[Imports ステートメント (.NET 名前空間および型)](../../language-reference/statements/imports-statement-net-namespace-and-type.md) を含めて、プロジェクトの外部で定義されている名前をインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="d1daa-124">You can include an [Imports Statement (.NET Namespace and Type)](../../language-reference/statements/imports-statement-net-namespace-and-type.md) to import names defined outside your project.</span></span> <span data-ttu-id="d1daa-125">`Imports` ステートメントを使用すると、インポートする名前空間内で定義されているクラスやその他の型を、修飾することなくコード内で参照できます。</span><span class="sxs-lookup"><span data-stu-id="d1daa-125">An `Imports` statement allows your code to refer to classes and other types defined within the imported namespace, without having to qualify them.</span></span> <span data-ttu-id="d1daa-126">`Imports` ステートメントは必要な数だけ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1daa-126">You can use as many `Imports` statements as appropriate.</span></span> <span data-ttu-id="d1daa-127">詳細については、「[参照と Imports ステートメント](references-and-the-imports-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1daa-127">For more information, see [References and the Imports Statement](references-and-the-imports-statement.md).</span></span>  
  
### <a name="namespace-statements"></a><span data-ttu-id="d1daa-128">Namespace ステートメント</span><span class="sxs-lookup"><span data-stu-id="d1daa-128">Namespace Statements</span></span>  
 <span data-ttu-id="d1daa-129">名前空間を使用すると、プログラミング要素を編成、分類でき、グループ化とアクセスが容易になります。</span><span class="sxs-lookup"><span data-stu-id="d1daa-129">Namespaces help you organize and classify your programming elements for ease of grouping and accessing.</span></span> <span data-ttu-id="d1daa-130">[Namespace ステートメント](../../language-reference/statements/namespace-statement.md)を使用すると、特定の名前空間内の後続のステートメントを分類できます。</span><span class="sxs-lookup"><span data-stu-id="d1daa-130">You use the [Namespace Statement](../../language-reference/statements/namespace-statement.md) to classify the following statements within a particular namespace.</span></span> <span data-ttu-id="d1daa-131">詳細については、「[Visual Basic における名前空間](namespaces.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1daa-131">For more information, see [Namespaces in Visual Basic](namespaces.md).</span></span>  
  
### <a name="conditional-compilation-statements"></a><span data-ttu-id="d1daa-132">条件付きコンパイル ステートメント</span><span class="sxs-lookup"><span data-stu-id="d1daa-132">Conditional Compilation Statements</span></span>  
 <span data-ttu-id="d1daa-133">条件付きコンパイル ステートメントは、ソース ファイル内のほぼどこにでも記述できます。</span><span class="sxs-lookup"><span data-stu-id="d1daa-133">Conditional compilation statements can appear almost anywhere in your source file.</span></span> <span data-ttu-id="d1daa-134">コンパイル時に、特定の条件に応じて、コードの一部を含める、または除外することができます。</span><span class="sxs-lookup"><span data-stu-id="d1daa-134">They cause parts of your code to be included or excluded at compile time depending on certain conditions.</span></span> <span data-ttu-id="d1daa-135">条件付きコードはデバッグ モードでのみ実行されるため、アプリケーションのデバッグにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1daa-135">You can also use them for debugging your application, because conditional code runs in debugging mode only.</span></span> <span data-ttu-id="d1daa-136">詳細については、[条件付きコンパイル](conditional-compilation.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1daa-136">For more information, see [Conditional Compilation](conditional-compilation.md).</span></span>  
  
## <a name="namespace-level-programming-elements"></a><span data-ttu-id="d1daa-137">名前空間レベルのプログラミング要素</span><span class="sxs-lookup"><span data-stu-id="d1daa-137">Namespace-Level Programming Elements</span></span>  
 <span data-ttu-id="d1daa-138">ソース ファイル内のすべてのコードは、クラス、構造体、モジュールに含まれます。</span><span class="sxs-lookup"><span data-stu-id="d1daa-138">Classes, structures, and modules contain all the code in your source file.</span></span> <span data-ttu-id="d1daa-139">これらは "*名前空間レベル*" の要素であり、名前空間内またはソース ファイル レベルで記述することができます。</span><span class="sxs-lookup"><span data-stu-id="d1daa-139">They are *namespace-level* elements, which can appear within a namespace or at the source file level.</span></span> <span data-ttu-id="d1daa-140">他のすべてのプログラミング要素の宣言が保持されます。</span><span class="sxs-lookup"><span data-stu-id="d1daa-140">They hold the declarations of all other programming elements.</span></span> <span data-ttu-id="d1daa-141">また、要素シグネチャを定義するが実装を提供しないインターフェイスは、モジュール レベルで記述します。</span><span class="sxs-lookup"><span data-stu-id="d1daa-141">Interfaces, which define element signatures but provide no implementation, also appear at module level.</span></span> <span data-ttu-id="d1daa-142">モジュールレベルの要素の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1daa-142">For more information on the module-level elements, see the following:</span></span>  
  
- [<span data-ttu-id="d1daa-143">Class ステートメント</span><span class="sxs-lookup"><span data-stu-id="d1daa-143">Class Statement</span></span>](../../language-reference/statements/class-statement.md)  
  
- [<span data-ttu-id="d1daa-144">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="d1daa-144">Structure Statement</span></span>](../../language-reference/statements/structure-statement.md)  
  
- [<span data-ttu-id="d1daa-145">Module ステートメント</span><span class="sxs-lookup"><span data-stu-id="d1daa-145">Module Statement</span></span>](../../language-reference/statements/module-statement.md)  
  
- [<span data-ttu-id="d1daa-146">Interface ステートメント</span><span class="sxs-lookup"><span data-stu-id="d1daa-146">Interface Statement</span></span>](../../language-reference/statements/interface-statement.md)  
  
 <span data-ttu-id="d1daa-147">名前空間レベルのデータ要素は、列挙型とデリゲートです。</span><span class="sxs-lookup"><span data-stu-id="d1daa-147">Data elements at namespace level are enumerations and delegates.</span></span>  
  
## <a name="module-level-programming-elements"></a><span data-ttu-id="d1daa-148">モジュールレベルのプログラミング要素</span><span class="sxs-lookup"><span data-stu-id="d1daa-148">Module-Level Programming Elements</span></span>  
 <span data-ttu-id="d1daa-149">プロシージャ、演算子、プロパティ、イベントは、実行可能コード (実行時にアクションを実行するステートメント) を保持できる唯一のプログラミング要素です。</span><span class="sxs-lookup"><span data-stu-id="d1daa-149">Procedures, operators, properties, and events are the only programming elements that can hold executable code (statements that perform actions at run time).</span></span> <span data-ttu-id="d1daa-150">これらは、プログラムの "*モジュールレベル*" の要素です。</span><span class="sxs-lookup"><span data-stu-id="d1daa-150">They are the *module-level* elements of your program.</span></span> <span data-ttu-id="d1daa-151">プロシージャレベルの要素の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1daa-151">For more information on the procedure-level elements, see the following:</span></span>  
  
- [<span data-ttu-id="d1daa-152">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="d1daa-152">Function Statement</span></span>](../../language-reference/statements/function-statement.md)  
  
- [<span data-ttu-id="d1daa-153">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="d1daa-153">Sub Statement</span></span>](../../language-reference/statements/sub-statement.md)  
  
- [<span data-ttu-id="d1daa-154">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="d1daa-154">Declare Statement</span></span>](../../language-reference/statements/declare-statement.md)  
  
- [<span data-ttu-id="d1daa-155">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="d1daa-155">Operator Statement</span></span>](../../language-reference/statements/operator-statement.md)  
  
- [<span data-ttu-id="d1daa-156">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="d1daa-156">Property Statement</span></span>](../../language-reference/statements/property-statement.md)  
  
- [<span data-ttu-id="d1daa-157">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="d1daa-157">Event Statement</span></span>](../../language-reference/statements/event-statement.md)  
  
 <span data-ttu-id="d1daa-158">モジュール レベルのデータ要素は、変数、定数、列挙型、デリゲートです。</span><span class="sxs-lookup"><span data-stu-id="d1daa-158">Data elements at module level are variables, constants, enumerations, and delegates.</span></span>  
  
## <a name="procedure-level-programming-elements"></a><span data-ttu-id="d1daa-159">プロシージャレベルのプログラミング要素</span><span class="sxs-lookup"><span data-stu-id="d1daa-159">Procedure-Level Programming Elements</span></span>  
 <span data-ttu-id="d1daa-160">"*プロシージャレベル*" の要素の内容の大部分は実行可能なステートメントであり、プログラムの実行時コードを構成します。</span><span class="sxs-lookup"><span data-stu-id="d1daa-160">Most of the contents of *procedure-level* elements are executable statements, which constitute the run-time code of your program.</span></span> <span data-ttu-id="d1daa-161">すべての実行可能コードは、何らかのプロシージャ (`Function`、`Sub`、`Operator`、`Get`、`Set`、`AddHandler`、`RemoveHandler`、`RaiseEvent`) 内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1daa-161">All executable code must be in some procedure (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`).</span></span> <span data-ttu-id="d1daa-162">詳細については、「[ステートメント](../language-features/statements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1daa-162">For more information, see [Statements](../language-features/statements.md).</span></span>  
  
 <span data-ttu-id="d1daa-163">プロシージャ レベルのデータ要素は、ローカル変数と定数に制限されます。</span><span class="sxs-lookup"><span data-stu-id="d1daa-163">Data elements at procedure level are limited to local variables and constants.</span></span>  
  
## <a name="the-main-procedure"></a><span data-ttu-id="d1daa-164">Main プロシージャ</span><span class="sxs-lookup"><span data-stu-id="d1daa-164">The Main Procedure</span></span>  
 <span data-ttu-id="d1daa-165">`Main` プロシージャは、アプリケーションが読み込まれたときに実行される最初のコードです。</span><span class="sxs-lookup"><span data-stu-id="d1daa-165">The `Main` procedure is the first code to run when your application has been loaded.</span></span> <span data-ttu-id="d1daa-166">`Main` は、アプリケーションの開始点および全体的な制御として機能します。</span><span class="sxs-lookup"><span data-stu-id="d1daa-166">`Main` serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="d1daa-167">`Main` には、次の 4 種類があります。</span><span class="sxs-lookup"><span data-stu-id="d1daa-167">There are four varieties of `Main`:</span></span>  
  
- `Sub Main()`  
  
- `Sub Main(ByVal cmdArgs() As String)`  
  
- `Function Main() As Integer`  
  
- `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 <span data-ttu-id="d1daa-168">このプロシージャの中で最も一般的なものは `Sub Main()` です。</span><span class="sxs-lookup"><span data-stu-id="d1daa-168">The most common variety of this procedure is `Sub Main()`.</span></span> <span data-ttu-id="d1daa-169">詳細については、「[Visual Basic の Main プロシージャ](main-procedure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1daa-169">For more information, see [Main Procedure in Visual Basic](main-procedure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1daa-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1daa-170">See also</span></span>

- [<span data-ttu-id="d1daa-171">Visual Basic の Main プロシージャ</span><span class="sxs-lookup"><span data-stu-id="d1daa-171">Main Procedure in Visual Basic</span></span>](main-procedure.md)
- [<span data-ttu-id="d1daa-172">Visual Basic の名前付け規則</span><span class="sxs-lookup"><span data-stu-id="d1daa-172">Visual Basic Naming Conventions</span></span>](naming-conventions.md)
- [<span data-ttu-id="d1daa-173">Visual Basic の制限事項</span><span class="sxs-lookup"><span data-stu-id="d1daa-173">Visual Basic Limitations</span></span>](limitations.md)
