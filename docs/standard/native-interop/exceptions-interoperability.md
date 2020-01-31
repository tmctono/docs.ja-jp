---
title: 例外の相互運用性
ms.date: 01/16/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: 2aff71e97e1be0dbb584f4fe43c322cea86d2480
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794618"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a><span data-ttu-id="1c089-102">アンマネージコードでの相互運用例外の使用</span><span class="sxs-lookup"><span data-stu-id="1c089-102">Working with Interop Exceptions in Unmanaged Code</span></span>

<span data-ttu-id="1c089-103">アンマネージコード例外相互運用は、Windows プラットフォームでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1c089-103">Unmanaged code exception interop is supported on Windows platforms only.</span></span> <span data-ttu-id="1c089-104">Windows 以外のプラットフォームで移植性の問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="1c089-104">Portability issues arise on non-Windows platforms.</span></span> <span data-ttu-id="1c089-105">Unix ABI には例外処理の定義がないため、マネージコードでは、内部で例外メカニズムがどのように機能するかを知ることができません。</span><span class="sxs-lookup"><span data-stu-id="1c089-105">Since the Unix ABI has no definition for exception handling, managed code can't know how exception mechanisms work under the covers.</span></span> <span data-ttu-id="1c089-106">そのため、例外が発生し、予期しない動作やクラッシュが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1c089-106">Therefore, exceptions can end up resulting in unpredictable behaviors and crashes.</span></span>

## <a name="setjmplongjmp-behaviors"></a><span data-ttu-id="1c089-107">Setjmp/Longjmp 動作</span><span class="sxs-lookup"><span data-stu-id="1c089-107">Setjmp/Longjmp Behaviors</span></span>

<span data-ttu-id="1c089-108">`setjmp` および `longjmp` C 関数との相互運用はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1c089-108">Interop with `setjmp` and `longjmp` C functions is not supported.</span></span> <span data-ttu-id="1c089-109">`longjmp` を使用して、マネージフレームをスキップすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1c089-109">You can't use `longjmp` to skip over managed frames.</span></span>

<span data-ttu-id="1c089-110">詳細については、「 [longjmp documentation](https://docs.microsoft.com/cpp/c-runtime-library/reference/longjmp)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c089-110">For more information, see [longjmp documentation](https://docs.microsoft.com/cpp/c-runtime-library/reference/longjmp).</span></span>

## <a name="see-also"></a><span data-ttu-id="1c089-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c089-111">See also</span></span>

- [<span data-ttu-id="1c089-112">例外</span><span class="sxs-lookup"><span data-stu-id="1c089-112">Exceptions</span></span>](index.md)
- [<span data-ttu-id="1c089-113">ネイティブライブラリとの相互運用</span><span class="sxs-lookup"><span data-stu-id="1c089-113">Interop with Native Libraries</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
