---
title: ISymUnmanagedDispose インターフェイス
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose
helpviewer_keywords:
- ISymUnmanagedDispose interface [.NET Framework debugging]
ms.assetid: b1d74e83-a200-4d00-8fbd-27918808616d
topic_type:
- apiref
ms.openlocfilehash: 08d9ba8f8c9a251bd0db0ffe256af7db0164ba2f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449231"
---
# <a name="isymunmanageddispose-interface"></a><span data-ttu-id="9c557-102">ISymUnmanagedDispose インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9c557-102">ISymUnmanagedDispose Interface</span></span>
<span data-ttu-id="9c557-103">アンマネージリソースを破棄します。</span><span class="sxs-lookup"><span data-stu-id="9c557-103">Disposes of unmanaged resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9c557-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="9c557-104">Methods</span></span>  
  
|<span data-ttu-id="9c557-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="9c557-105">Method</span></span>|<span data-ttu-id="9c557-106">説明</span><span class="sxs-lookup"><span data-stu-id="9c557-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9c557-107">destroy メソッド</span><span class="sxs-lookup"><span data-stu-id="9c557-107">Destroy Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-destroy-method.md)|<span data-ttu-id="9c557-108">基になるオブジェクトがすべての内部参照を解放し、後続のメソッド呼び出しの失敗を返します。</span><span class="sxs-lookup"><span data-stu-id="9c557-108">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9c557-109">要件</span><span class="sxs-lookup"><span data-stu-id="9c557-109">Requirements</span></span>  
 <span data-ttu-id="9c557-110">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="9c557-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c557-111">参照</span><span class="sxs-lookup"><span data-stu-id="9c557-111">See also</span></span>

- [<span data-ttu-id="9c557-112">シンボル ストア診断インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9c557-112">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
