---
title: ISymUnmanagedScope2 インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2
helpviewer_keywords:
- ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type:
- apiref
ms.openlocfilehash: 3374097c8d343fed6badf046742ca556d2a92f3e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446220"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="79253-102">ISymUnmanagedScope2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="79253-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="79253-103">メソッド内の構文のスコープを表します。</span><span class="sxs-lookup"><span data-stu-id="79253-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="79253-104">このインターフェイスは、スコープ内で定義された定数に関する情報を取得するメソッドを使用して、 [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="79253-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="79253-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="79253-105">Methods</span></span>  
  
|<span data-ttu-id="79253-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="79253-106">Method</span></span>|<span data-ttu-id="79253-107">説明</span><span class="sxs-lookup"><span data-stu-id="79253-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="79253-108">GetConstantCount メソッド</span><span class="sxs-lookup"><span data-stu-id="79253-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="79253-109">このスコープ内で定義されている定数の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="79253-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="79253-110">GetConstants メソッド</span><span class="sxs-lookup"><span data-stu-id="79253-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="79253-111">このスコープ内で定義されているローカル定数を取得します。</span><span class="sxs-lookup"><span data-stu-id="79253-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="79253-112">要件</span><span class="sxs-lookup"><span data-stu-id="79253-112">Requirements</span></span>  
 <span data-ttu-id="79253-113">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="79253-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79253-114">参照</span><span class="sxs-lookup"><span data-stu-id="79253-114">See also</span></span>

- [<span data-ttu-id="79253-115">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="79253-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="79253-116">ISymUnmanagedScope インターフェイス</span><span class="sxs-lookup"><span data-stu-id="79253-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
