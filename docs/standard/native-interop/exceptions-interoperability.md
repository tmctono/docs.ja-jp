---
title: 例外の相互運用性
ms.date: 01/16/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: 90774b5d1b64feb34e01f48708d94f8f841a7c9d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550873"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a><span data-ttu-id="e159a-102">アンマネージド コードでの相互運用例外の処理</span><span class="sxs-lookup"><span data-stu-id="e159a-102">Working with Interop Exceptions in Unmanaged Code</span></span>

<span data-ttu-id="e159a-103">アンマネージド コードの例外の相互運用は、Windows プラットフォームでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e159a-103">Unmanaged code exception interop is supported on Windows platforms only.</span></span> <span data-ttu-id="e159a-104">Windows 以外のプラットフォームでは移植性の問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="e159a-104">Portability issues arise on non-Windows platforms.</span></span> <span data-ttu-id="e159a-105">Unix ABI には例外処理の定義がないため、マネージド コードでは、内部での例外メカニズムのしくみが認識されません。</span><span class="sxs-lookup"><span data-stu-id="e159a-105">Since the Unix ABI has no definition for exception handling, managed code can't know how exception mechanisms work under the covers.</span></span> <span data-ttu-id="e159a-106">そのため、例外が発生すると、予期しない動作やクラッシュが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e159a-106">Therefore, exceptions can end up resulting in unpredictable behaviors and crashes.</span></span>

## <a name="setjmplongjmp-behaviors"></a><span data-ttu-id="e159a-107">Setjmp と Longjmp の動作</span><span class="sxs-lookup"><span data-stu-id="e159a-107">Setjmp/Longjmp Behaviors</span></span>

<span data-ttu-id="e159a-108">`setjmp` および `longjmp` C 関数との相互運用はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e159a-108">Interop with `setjmp` and `longjmp` C functions is not supported.</span></span> <span data-ttu-id="e159a-109">`longjmp` を使用して、マネージド フレームをスキップすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e159a-109">You can't use `longjmp` to skip over managed frames.</span></span>

<span data-ttu-id="e159a-110">詳しくは、[longjmp のドキュメント](/cpp/c-runtime-library/reference/longjmp)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e159a-110">For more information, see [longjmp documentation](/cpp/c-runtime-library/reference/longjmp).</span></span>

## <a name="see-also"></a><span data-ttu-id="e159a-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="e159a-111">See also</span></span>

- [<span data-ttu-id="e159a-112">例外</span><span class="sxs-lookup"><span data-stu-id="e159a-112">Exceptions</span></span>](index.md)
- [<span data-ttu-id="e159a-113">ネイティブ ライブラリとの相互運用</span><span class="sxs-lookup"><span data-stu-id="e159a-113">Interop with Native Libraries</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
