---
title: 例外の作成とスロー - C# プログラミング ガイド
description: 例外の作成とスローについて説明します。 例外は、プログラムの実行中にエラーが発生したことを示すために使われます。
ms.date: 07/20/2015
helpviewer_keywords:
- catching exceptions [C#]
- throwing exceptions [C#]
- exceptions [C#], creating
- exceptions [C#], throwing
ms.assetid: 6bbba495-a115-4c6d-90cc-1f4d7b5f39e2
ms.openlocfilehash: 77a1e8eb4d442e66f8b9ed17a5881661a5990a35
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195494"
---
# <a name="creating-and-throwing-exceptions-c-programming-guide"></a><span data-ttu-id="28be3-104">例外の作成とスロー (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="28be3-104">Creating and Throwing Exceptions (C# Programming Guide)</span></span>

<span data-ttu-id="28be3-105">例外は、プログラムの実行中にエラーが発生したことを示すために使われます。</span><span class="sxs-lookup"><span data-stu-id="28be3-105">Exceptions are used to indicate that an error has occurred while running the program.</span></span> <span data-ttu-id="28be3-106">エラーを説明する例外オブジェクトが作成された後、[throw](../../language-reference/keywords/throw.md) キーワードで "*スロー*" されます。</span><span class="sxs-lookup"><span data-stu-id="28be3-106">Exception objects that describe an error are created and then *thrown* with the [throw](../../language-reference/keywords/throw.md) keyword.</span></span> <span data-ttu-id="28be3-107">そのとき、ランタイムは最も互換性のある例外ハンドラーを検索します。</span><span class="sxs-lookup"><span data-stu-id="28be3-107">The runtime then searches for the most compatible exception handler.</span></span>  
  
 <span data-ttu-id="28be3-108">プログラマは、以下の条件が 1 つでも該当するときは、例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="28be3-108">Programmers should throw exceptions when one or more of the following conditions are true:</span></span>  
  
- <span data-ttu-id="28be3-109">メソッドは、定義されている機能を完了できません。</span><span class="sxs-lookup"><span data-stu-id="28be3-109">The method cannot complete its defined functionality.</span></span>  
  
     <span data-ttu-id="28be3-110">たとえば、メソッドへのパラメーターに無効な値が設定されている場合などです。</span><span class="sxs-lookup"><span data-stu-id="28be3-110">For example, if a parameter to a method has an invalid value:</span></span>  
  
     [!code-csharp[csProgGuideExceptions#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#12)]  
  
- <span data-ttu-id="28be3-111">オブジェクトの状態に基づくと、オブジェクトに対して行われた呼び出しが不適切です。</span><span class="sxs-lookup"><span data-stu-id="28be3-111">An inappropriate call to an object is made, based on the object state.</span></span>  
  
     <span data-ttu-id="28be3-112">たとえば、読み取り専用ファイルに書き込もうとしたような場合です。</span><span class="sxs-lookup"><span data-stu-id="28be3-112">One example might be trying to write to a read-only file.</span></span> <span data-ttu-id="28be3-113">オブジェクトの状態により操作が許可されない場合は、<xref:System.InvalidOperationException> のインスタンスまたはこのクラスの派生に基づくオブジェクトをスローします。</span><span class="sxs-lookup"><span data-stu-id="28be3-113">In cases where an object state does not allow an operation, throw an instance of <xref:System.InvalidOperationException> or an object based on a derivation of this class.</span></span> <span data-ttu-id="28be3-114"><xref:System.InvalidOperationException> オブジェクトをスローするメソッドの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="28be3-114">This is an example of a method that throws an <xref:System.InvalidOperationException> object:</span></span>  
  
     [!code-csharp[csProgGuideExceptions#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#13)]  
  
- <span data-ttu-id="28be3-115">メソッドへの引数が原因で例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="28be3-115">When an argument to a method causes an exception.</span></span>  
  
     <span data-ttu-id="28be3-116">この場合は、元の例外をキャッチして、<xref:System.ArgumentException> のインスタンスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28be3-116">In this case, the original exception should be caught and an <xref:System.ArgumentException> instance should be created.</span></span> <span data-ttu-id="28be3-117">元の例外は、<xref:System.Exception.InnerException%2A> パラメーターとして <xref:System.ArgumentException> のコンストラクターに渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="28be3-117">The original exception should be passed to the constructor of the <xref:System.ArgumentException> as the <xref:System.Exception.InnerException%2A> parameter:</span></span>  
  
     [!code-csharp[csProgGuideExceptions#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#14)]  
  
 <span data-ttu-id="28be3-118">例外には、<xref:System.Exception.StackTrace%2A> というプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="28be3-118">Exceptions contain a property named <xref:System.Exception.StackTrace%2A>.</span></span> <span data-ttu-id="28be3-119">この文字列には、現在の呼び出し履歴でのメソッドの名前と、各メソッドの例外がスローされたファイル名と行番号が含まれます。</span><span class="sxs-lookup"><span data-stu-id="28be3-119">This string contains the name of the methods on the current call stack, together with the file name and line number where the exception was thrown for each method.</span></span> <span data-ttu-id="28be3-120">スタック トレースを開始するポイントから例外をスローする必要があるため、共通言語ランタイム (CLR) によって `throw` ステートメントのポイントから <xref:System.Exception.StackTrace%2A> オブジェクトが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="28be3-120">A <xref:System.Exception.StackTrace%2A> object is created automatically by the common language runtime (CLR) from the point of the `throw` statement, so that exceptions must be thrown from the point where the stack trace should begin.</span></span>  
  
 <span data-ttu-id="28be3-121">すべての例外には、<xref:System.Exception.Message%2A> というプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="28be3-121">All exceptions contain a property named <xref:System.Exception.Message%2A>.</span></span> <span data-ttu-id="28be3-122">例外の原因を説明するには、この文字列を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28be3-122">This string should be set to explain the reason for the exception.</span></span> <span data-ttu-id="28be3-123">機密性の高い情報はメッセージ テキストに入れないようにする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="28be3-123">Note that information that is sensitive to security should not be put in the message text.</span></span> <span data-ttu-id="28be3-124"><xref:System.ArgumentException> には、<xref:System.Exception.Message%2A> に加え、例外がスローされる原因となる引数の名前に設定される <xref:System.ArgumentException.ParamName%2A> というプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="28be3-124">In addition to <xref:System.Exception.Message%2A>, <xref:System.ArgumentException> contains a property named <xref:System.ArgumentException.ParamName%2A> that should be set to the name of the argument that caused the exception to be thrown.</span></span> <span data-ttu-id="28be3-125">プロパティ セッターの場合、<xref:System.ArgumentException.ParamName%2A> は `value` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28be3-125">In the case of a property setter, <xref:System.ArgumentException.ParamName%2A> should be set to `value`.</span></span>  
  
 <span data-ttu-id="28be3-126">パブリックのプロテクト メンバーは、意図された機能を完了できない場合は常に例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="28be3-126">Public and protected methods should throw exceptions whenever they cannot complete their intended functions.</span></span> <span data-ttu-id="28be3-127">スローされる例外クラスは、エラー状態に適合する使用可能な例外の中で最も具体的なものである必要があります。</span><span class="sxs-lookup"><span data-stu-id="28be3-127">The exception class that is thrown should be the most specific exception available that fits the error conditions.</span></span> <span data-ttu-id="28be3-128">これらの例外はクラスの機能の一部として文書化する必要があり、派生クラスまたは元のクラスの更新では、旧バージョンとの互換性のために同じ動作を維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28be3-128">These exceptions should be documented as part of the class functionality, and derived classes or updates to the original class should retain the same behavior for backward compatibility.</span></span>  
  
## <a name="things-to-avoid-when-throwing-exceptions"></a><span data-ttu-id="28be3-129">例外をスローするときに避ける必要があること</span><span class="sxs-lookup"><span data-stu-id="28be3-129">Things to Avoid When Throwing Exceptions</span></span>  

 <span data-ttu-id="28be3-130">次の一覧は、例外をスローするときに避ける必要があることです。</span><span class="sxs-lookup"><span data-stu-id="28be3-130">The following list identifies practices to avoid when throwing exceptions:</span></span>  
  
- <span data-ttu-id="28be3-131">通常の実行の一部として、例外を使ってプログラムのフローを変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="28be3-131">Exceptions should not be used to change the flow of a program as part of ordinary execution.</span></span> <span data-ttu-id="28be3-132">例外は、エラー状態の報告と処理のためだけに使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="28be3-132">Exceptions should only be used to report and handle error conditions.</span></span>  
  
- <span data-ttu-id="28be3-133">スローする代わりに、戻り値またはパラメーターとして例外を返さないでください。</span><span class="sxs-lookup"><span data-stu-id="28be3-133">Exceptions should not be returned as a return value or parameter instead of being thrown.</span></span>  
  
- <span data-ttu-id="28be3-134">自作のソース コードからは、意図的に <xref:System.Exception?displayProperty=nameWithType>、<xref:System.SystemException?displayProperty=nameWithType>、<xref:System.NullReferenceException?displayProperty=nameWithType>、または <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> をスローしないでください。</span><span class="sxs-lookup"><span data-stu-id="28be3-134">Do not throw <xref:System.Exception?displayProperty=nameWithType>, <xref:System.SystemException?displayProperty=nameWithType>, <xref:System.NullReferenceException?displayProperty=nameWithType>, or <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> intentionally from your own source code.</span></span>  
  
- <span data-ttu-id="28be3-135">デバッグ モードではスローでき、リリース モードではスローできない例外は、作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="28be3-135">Do not create exceptions that can be thrown in debug mode but not release mode.</span></span> <span data-ttu-id="28be3-136">開発フェーズ中に実行時エラーを識別するには、代わりにデバッグ アサートを使ってください。</span><span class="sxs-lookup"><span data-stu-id="28be3-136">To identify run-time errors during the development phase, use Debug Assert instead.</span></span>  
  
## <a name="defining-exception-classes"></a><span data-ttu-id="28be3-137">例外クラスの定義</span><span class="sxs-lookup"><span data-stu-id="28be3-137">Defining Exception Classes</span></span>  

 <span data-ttu-id="28be3-138">プログラムでは、<xref:System> 名前空間で事前定義された例外クラスをスローするか (上記の場合を除きます)、<xref:System.Exception> から派生することで独自の例外クラスを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="28be3-138">Programs can throw a predefined exception class in the <xref:System> namespace (except where previously noted), or create their own exception classes by deriving from <xref:System.Exception>.</span></span> <span data-ttu-id="28be3-139">派生クラスでは、少なくとも 4 つのコンストラクターを必ず定義します。パラメータ―なしのコンストラクター、メッセージ プロパティを設定するコンストラクター、<xref:System.Exception.Message%2A> プロパティと <xref:System.Exception.InnerException%2A> プロパティの両方を設定するコンストラクター、</span><span class="sxs-lookup"><span data-stu-id="28be3-139">The derived classes should define at least four constructors: one parameterless constructor, one that sets the message property, and one that sets both the <xref:System.Exception.Message%2A> and <xref:System.Exception.InnerException%2A> properties.</span></span> <span data-ttu-id="28be3-140">そして 4 番目は例外のシリアル化に使われるコンストラクターです。</span><span class="sxs-lookup"><span data-stu-id="28be3-140">The fourth constructor is used to serialize the exception.</span></span> <span data-ttu-id="28be3-141">新しい例外クラスは、シリアル化可能にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="28be3-141">New exception classes should be serializable.</span></span> <span data-ttu-id="28be3-142">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="28be3-142">For example:</span></span>  
  
 [!code-csharp[csProgGuideExceptions#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#15)]  
  
 <span data-ttu-id="28be3-143">例外クラスへの新しいプロパティの追加は、プロパティによって提供されるデータが例外の解決に役立つ場合にのみ行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="28be3-143">New properties should only be added to the exception class when the data they provide is useful to resolving the exception.</span></span> <span data-ttu-id="28be3-144">派生例外クラスに新しいプロパティを追加する場合は、`ToString()` をオーバーライドして追加情報を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="28be3-144">If new properties are added to the derived exception class, `ToString()` should be overridden to return the added information.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="28be3-145">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="28be3-145">C# Language Specification</span></span>  

<span data-ttu-id="28be3-146">詳細については、「[C# 言語仕様](/dotnet/csharp/language-reference/language-specification/introduction)」の[例外](~/_csharplang/spec/exceptions.md)と [throw ステートメント](~/_csharplang/spec/statements.md#the-throw-statement)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="28be3-146">For more information, see [Exceptions](~/_csharplang/spec/exceptions.md) and [The throw statement](~/_csharplang/spec/statements.md#the-throw-statement) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="28be3-147">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="28be3-147">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="28be3-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="28be3-148">See also</span></span>

- [<span data-ttu-id="28be3-149">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="28be3-149">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="28be3-150">例外と例外処理</span><span class="sxs-lookup"><span data-stu-id="28be3-150">Exceptions and Exception Handling</span></span>](./index.md)
- [<span data-ttu-id="28be3-151">例外階層</span><span class="sxs-lookup"><span data-stu-id="28be3-151">Exception Hierarchy</span></span>](../../../standard/exceptions/index.md)
- [<span data-ttu-id="28be3-152">例外処理</span><span class="sxs-lookup"><span data-stu-id="28be3-152">Exception Handling</span></span>](./exception-handling.md)
