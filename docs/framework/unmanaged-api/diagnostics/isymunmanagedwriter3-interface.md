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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e26d79a5b597b8585f2fffd7f3945f00832ca134
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650714"
---
# <a name="isymunmanagedwriter3-interface"></a><span data-ttu-id="cdb28-102">ISymUnmanagedWriter3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cdb28-102">ISymUnmanagedWriter3 Interface</span></span>
<span data-ttu-id="cdb28-103">シンボル ライターを表し、ドキュメント、シーケンス ポイント、構文のスコープ、および変数を定義するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="cdb28-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="cdb28-104">このインターフェイスは、拡張、 [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="cdb28-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cdb28-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="cdb28-105">Methods</span></span>  
  
|<span data-ttu-id="cdb28-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="cdb28-106">Method</span></span>|<span data-ttu-id="cdb28-107">説明</span><span class="sxs-lookup"><span data-stu-id="cdb28-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cdb28-108">Commit メソッド</span><span class="sxs-lookup"><span data-stu-id="cdb28-108">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-commit-method.md)|<span data-ttu-id="cdb28-109">ストリームにこれまでに書き込まれた変更をコミットします。</span><span class="sxs-lookup"><span data-stu-id="cdb28-109">Commits the changes written so far to the stream.</span></span>|  
|[<span data-ttu-id="cdb28-110">OpenMethod2 メソッド</span><span class="sxs-lookup"><span data-stu-id="cdb28-110">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)|<span data-ttu-id="cdb28-111">メソッドが開き、イメージで実際のセクションのオフセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="cdb28-111">Opens a method and provides its real section offset in the image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cdb28-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="cdb28-112">Requirements</span></span>  
 <span data-ttu-id="cdb28-113">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cdb28-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdb28-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="cdb28-114">See also</span></span>

- [<span data-ttu-id="cdb28-115">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cdb28-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="cdb28-116">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cdb28-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="cdb28-117">ISymUnmanagedWriter2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cdb28-117">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
