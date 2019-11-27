---
title: ISymUnmanagedWriter2 インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2
helpviewer_keywords:
- ISymUnmanagedWriter2 interface [.NET Framework debugging]
ms.assetid: 8e78faa4-cf43-44fb-a91d-94d6df692a25
topic_type:
- apiref
ms.openlocfilehash: c7f0235aa7096a790a0fd956081e330c8fdad9fe
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438257"
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="e61c6-102">ISymUnmanagedWriter2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e61c6-102">ISymUnmanagedWriter2 Interface</span></span>
<span data-ttu-id="e61c6-103">シンボルライターを表し、ドキュメント、シーケンスポイント、構文スコープ、および変数を定義するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e61c6-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="e61c6-104">このインターフェイスは、 [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="e61c6-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e61c6-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e61c6-105">Methods</span></span>  
  
|<span data-ttu-id="e61c6-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="e61c6-106">Method</span></span>|<span data-ttu-id="e61c6-107">説明</span><span class="sxs-lookup"><span data-stu-id="e61c6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e61c6-108">DefineConstant2 メソッド</span><span class="sxs-lookup"><span data-stu-id="e61c6-108">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="e61c6-109">定数値の名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="e61c6-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="e61c6-110">DefineGlobalVariable2 メソッド</span><span class="sxs-lookup"><span data-stu-id="e61c6-110">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="e61c6-111">1つのグローバル変数を定義します。</span><span class="sxs-lookup"><span data-stu-id="e61c6-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="e61c6-112">DefineLocalVariable2 メソッド</span><span class="sxs-lookup"><span data-stu-id="e61c6-112">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="e61c6-113">現在の構文のスコープの変数を 1 つ定義します。</span><span class="sxs-lookup"><span data-stu-id="e61c6-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e61c6-114">要件</span><span class="sxs-lookup"><span data-stu-id="e61c6-114">Requirements</span></span>  
 <span data-ttu-id="e61c6-115">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="e61c6-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e61c6-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="e61c6-116">See also</span></span>

- [<span data-ttu-id="e61c6-117">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e61c6-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="e61c6-118">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e61c6-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="e61c6-119">ISymUnmanagedWriter3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e61c6-119">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
