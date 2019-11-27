---
title: ISymUnmanagedWriter3 インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3
helpviewer_keywords:
- ISymUnmanagedWriter3 interface [.NET Framework debugging]
ms.assetid: a034c21e-e371-4360-b470-29e88288948f
topic_type:
- apiref
ms.openlocfilehash: 115d4b58b01606c29719fb88ab7dbf5a858b1251
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438171"
---
# <a name="isymunmanagedwriter3-interface"></a><span data-ttu-id="57a27-102">ISymUnmanagedWriter3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="57a27-102">ISymUnmanagedWriter3 Interface</span></span>
<span data-ttu-id="57a27-103">シンボルライターを表し、ドキュメント、シーケンスポイント、構文スコープ、および変数を定義するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="57a27-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="57a27-104">このインターフェイスは、 [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="57a27-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="57a27-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="57a27-105">Methods</span></span>  
  
|<span data-ttu-id="57a27-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="57a27-106">Method</span></span>|<span data-ttu-id="57a27-107">説明</span><span class="sxs-lookup"><span data-stu-id="57a27-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="57a27-108">Commit メソッド</span><span class="sxs-lookup"><span data-stu-id="57a27-108">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-commit-method.md)|<span data-ttu-id="57a27-109">これまでに書き込まれた変更をストリームにコミットします。</span><span class="sxs-lookup"><span data-stu-id="57a27-109">Commits the changes written so far to the stream.</span></span>|  
|[<span data-ttu-id="57a27-110">OpenMethod2 メソッド</span><span class="sxs-lookup"><span data-stu-id="57a27-110">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)|<span data-ttu-id="57a27-111">メソッドを開き、イメージ内の実際のセクションオフセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="57a27-111">Opens a method and provides its real section offset in the image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="57a27-112">要件</span><span class="sxs-lookup"><span data-stu-id="57a27-112">Requirements</span></span>  
 <span data-ttu-id="57a27-113">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="57a27-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57a27-114">参照</span><span class="sxs-lookup"><span data-stu-id="57a27-114">See also</span></span>

- [<span data-ttu-id="57a27-115">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="57a27-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="57a27-116">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="57a27-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="57a27-117">ISymUnmanagedWriter2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="57a27-117">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
