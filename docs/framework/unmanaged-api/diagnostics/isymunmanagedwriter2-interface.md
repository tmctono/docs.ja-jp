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
ms.openlocfilehash: 1fe6055d930c6d30e947d6bc774d0520a9e175ae
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614683"
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="efce2-102">ISymUnmanagedWriter2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="efce2-102">ISymUnmanagedWriter2 Interface</span></span>
<span data-ttu-id="efce2-103">シンボルライターを表し、ドキュメント、シーケンスポイント、構文スコープ、および変数を定義するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="efce2-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="efce2-104">このインターフェイスは、 [ISymUnmanagedWriter](isymunmanagedwriter-interface.md)インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="efce2-104">This interface extends the [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="efce2-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="efce2-105">Methods</span></span>  
  
|<span data-ttu-id="efce2-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="efce2-106">Method</span></span>|<span data-ttu-id="efce2-107">説明</span><span class="sxs-lookup"><span data-stu-id="efce2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="efce2-108">DefineConstant2 メソッド</span><span class="sxs-lookup"><span data-stu-id="efce2-108">DefineConstant2 Method</span></span>](isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="efce2-109">定数値の名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="efce2-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="efce2-110">DefineGlobalVariable2 メソッド</span><span class="sxs-lookup"><span data-stu-id="efce2-110">DefineGlobalVariable2 Method</span></span>](isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="efce2-111">グローバル変数を 1 つ定義します。</span><span class="sxs-lookup"><span data-stu-id="efce2-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="efce2-112">DefineLocalVariable2 メソッド</span><span class="sxs-lookup"><span data-stu-id="efce2-112">DefineLocalVariable2 Method</span></span>](isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="efce2-113">現在の構文のスコープの変数を 1 つ定義します。</span><span class="sxs-lookup"><span data-stu-id="efce2-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="efce2-114">要件</span><span class="sxs-lookup"><span data-stu-id="efce2-114">Requirements</span></span>  
 <span data-ttu-id="efce2-115">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="efce2-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efce2-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="efce2-116">See also</span></span>

- [<span data-ttu-id="efce2-117">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="efce2-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="efce2-118">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="efce2-118">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="efce2-119">ISymUnmanagedWriter3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="efce2-119">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
