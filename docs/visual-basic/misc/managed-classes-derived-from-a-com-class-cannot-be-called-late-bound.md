---
title: COM クラスから派生したマネージド クラスは、遅延バインディングされた呼び出しはできません。
ms.date: 07/20/2015
f1_keywords:
- vbrLateboundCallToInheritedComClass
ms.assetid: 7bc16e84-8d29-4f8e-bc4f-002c65c71099
ms.openlocfilehash: 401cb5d7194cbef616c87d59e5b1ed7f923fe6f9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402123"
---
# <a name="managed-classes-derived-from-a-com-class-cannot-be-called-late-bound"></a><span data-ttu-id="acf29-102">COM クラスから派生したマネージド クラスは、遅延バインディングされた呼び出しはできません。</span><span class="sxs-lookup"><span data-stu-id="acf29-102">Managed classes derived from a COM class cannot be called late-bound.</span></span>

<span data-ttu-id="acf29-103">COM クラスから派生したマネージド クラスに対して遅延バインディング呼び出しを実施しようとしましたが、このような呼び出しはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="acf29-103">You attempted to make a late-bound call to a managed class derived from a COM Class; such calls are not supported.</span></span>

## <a name="to-correct-the-problem"></a><span data-ttu-id="acf29-104">この問題を解決するには</span><span class="sxs-lookup"><span data-stu-id="acf29-104">To correct the problem</span></span>

<span data-ttu-id="acf29-105">呼び出しを事前バインディングにします。</span><span class="sxs-lookup"><span data-stu-id="acf29-105">Make the call early bound.</span></span>

## <a name="see-also"></a><span data-ttu-id="acf29-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="acf29-106">See also</span></span>

- [<span data-ttu-id="acf29-107">エラーの種類</span><span class="sxs-lookup"><span data-stu-id="acf29-107">Error Types</span></span>](../programming-guide/language-features/error-types.md)
