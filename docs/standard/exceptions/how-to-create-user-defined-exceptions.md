---
title: '方法: ユーザー定義の例外を作成する'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- user-defined exceptions
- exceptions, examples
- exceptions, user-defined
ms.assetid: 25819a5a-f915-4fc8-b924-a76915674e04
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 42860f549877436f43bfdc20fb3abde91d36101d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783187"
---
# <a name="how-to-create-user-defined-exceptions"></a><span data-ttu-id="c93a3-102">ユーザー定義の例外を作成する方法</span><span class="sxs-lookup"><span data-stu-id="c93a3-102">How to create user-defined exceptions</span></span>

<span data-ttu-id="c93a3-103">.NET では、基底クラス <xref:System.Exception> から最終的に派生した例外クラスの階層構造を提供します。</span><span class="sxs-lookup"><span data-stu-id="c93a3-103">.NET provides a hierarchy of exception classes ultimately derived from the base class <xref:System.Exception>.</span></span> <span data-ttu-id="c93a3-104">ただし、定義済みの例外のいずれも要件を満たさない場合は、<xref:System.Exception> クラスから派生することによって、独自の例外クラスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c93a3-104">However, if none of the predefined exceptions meets your needs, you can create your own exception classes by deriving from the <xref:System.Exception> class.</span></span>

<span data-ttu-id="c93a3-105">独自の例外を作成するときに、ユーザー定義の例外のクラス名の末尾に "Exception" という単語を付加し、次の例で示すように、3 つの共通コンストラクターを実装します。</span><span class="sxs-lookup"><span data-stu-id="c93a3-105">When creating your own exceptions, end the class name of the user-defined exception with the word "Exception", and implement the three common constructors, as shown in the following example.</span></span> <span data-ttu-id="c93a3-106">例では、`EmployeeListNotFoundException` という名前の新しい例外クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="c93a3-106">The example defines a new exception class named `EmployeeListNotFoundException`.</span></span> <span data-ttu-id="c93a3-107">このクラスは <xref:System.Exception> から派生し、次の 3 つのコンストラクターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c93a3-107">The class is derived from <xref:System.Exception> and includes three constructors.</span></span>

[!code-cpp[dg_exceptionDesign#14](../../../samples/snippets/cpp/VS_Snippets_CLR/dg_exceptionDesign/cpp/example2.cpp#14)]
[!code-csharp[dg_exceptionDesign#14](../../../samples/snippets/csharp/VS_Snippets_CLR/dg_exceptionDesign/cs/example2.cs#14)]
[!code-vb[dg_exceptionDesign#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/dg_exceptionDesign/vb/example2.vb#14)]  

> [!NOTE]
> <span data-ttu-id="c93a3-108">リモート処理を使用している場合は、任意のユーザー定義の例外のメタデータがサーバー側 (呼び出し先) とクライアント (プロキシ オブジェクトまたは呼び出し元) で使用できることを保証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c93a3-108">In situations where you are using remoting, you must ensure that the metadata for any user-defined exceptions is available at the server (callee) and to the client (the proxy object or caller).</span></span> <span data-ttu-id="c93a3-109">詳細については、「[例外の推奨事項](best-practices-for-exceptions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c93a3-109">For more information, see [Best practices for exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c93a3-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="c93a3-110">See also</span></span>

- [<span data-ttu-id="c93a3-111">例外</span><span class="sxs-lookup"><span data-stu-id="c93a3-111">Exceptions</span></span>](index.md)
