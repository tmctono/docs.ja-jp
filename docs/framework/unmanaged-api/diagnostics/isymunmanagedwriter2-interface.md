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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 97df6d6ec9a446e89eef8a9f8a5e5e8ddc85c0f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970197"
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="3852b-102">ISymUnmanagedWriter2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3852b-102">ISymUnmanagedWriter2 Interface</span></span>
<span data-ttu-id="3852b-103">シンボル ライターを表し、ドキュメント、シーケンス ポイント、構文のスコープ、および変数を定義するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="3852b-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="3852b-104">このインターフェイスは、拡張、 [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="3852b-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3852b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3852b-105">Methods</span></span>  
  
|<span data-ttu-id="3852b-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="3852b-106">Method</span></span>|<span data-ttu-id="3852b-107">説明</span><span class="sxs-lookup"><span data-stu-id="3852b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3852b-108">DefineConstant2 メソッド</span><span class="sxs-lookup"><span data-stu-id="3852b-108">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="3852b-109">定数値の名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="3852b-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="3852b-110">DefineGlobalVariable2 メソッド</span><span class="sxs-lookup"><span data-stu-id="3852b-110">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="3852b-111">1 つのグローバル変数を定義します。</span><span class="sxs-lookup"><span data-stu-id="3852b-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="3852b-112">DefineLocalVariable2 メソッド</span><span class="sxs-lookup"><span data-stu-id="3852b-112">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="3852b-113">現在の構文のスコープの変数を 1 つ定義します。</span><span class="sxs-lookup"><span data-stu-id="3852b-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3852b-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="3852b-114">Requirements</span></span>  
 <span data-ttu-id="3852b-115">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3852b-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3852b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3852b-116">See also</span></span>

- [<span data-ttu-id="3852b-117">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3852b-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="3852b-118">ISymUnmanagedWriter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3852b-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="3852b-119">ISymUnmanagedWriter3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3852b-119">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
